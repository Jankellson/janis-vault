---
type: dashboard
updated: 2026-05-12
cssclasses:
  - dashboard
obsidianUIMode: preview
tagad_task: ""
inbox_capture: ""
---

```dataviewjs
const now = new Date();
const h = now.getHours();
const greeting = h < 6 ? "🌙 Ar nakti" : h < 11 ? "🌅 Labrīt" : h < 17 ? "☀️ Labdien" : "🌆 Labvakar";

const lvDays = ["svētdiena","pirmdiena","otrdiena","trešdiena","ceturtdiena","piektdiena","sestdiena"];
const dayName = lvDays[now.getDay()];
const pad = n => String(n).padStart(2,"0");
const dateStr = `${now.getFullYear()}-${pad(now.getMonth()+1)}-${pad(now.getDate())}`;

const buildStart = new Date(2026, 4, 11);
const dayNum = Math.min(10, Math.floor((now - buildStart) / 86400000) + 1);

const logDates = new Set(
  dv.pages('"07-logs"').where(p => p.type === "log").file.name.array()
);
let streak = 0;
let chk = new Date(now);
while (logDates.has(`${chk.getFullYear()}-${pad(chk.getMonth()+1)}-${pad(chk.getDate())}`)) {
  streak++;
  chk.setDate(chk.getDate() - 1);
}

dv.el("div", `
<div class="jos-greeting-text">
  ${greeting}, Jāni
  <span class="jos-date">${dateStr} · ${dayName}</span>
  <span class="jos-day-badge">D${dayNum} / 10</span>
  <span class="jos-streak-inline">🔥 ${streak} streak</span>
</div>
`, { cls: "jos-greeting" });
```

```dataviewjs
const now = new Date();
const today = now.getDay() === 0 ? 7 : now.getDay();
const monday = new Date(now);
monday.setDate(now.getDate() - today + 1);

const lvShort = ["P","O","T","C","P","S","S"];
let html = '<div class="jos-week">';
for (let i = 0; i < 7; i++) {
  const d = new Date(monday);
  d.setDate(monday.getDate() + i);
  const isToday = d.toDateString() === now.toDateString();
  const isPast = d < new Date(now.toDateString());
  const cls = isToday ? "today" : isPast ? "done" : "";
  const meta = isToday ? "šodien" : isPast ? "✓" : "—";
  html += `<div class="jos-day-card ${cls}"><div class="jos-day-name">${lvShort[i]}</div><div class="jos-day-num">${d.getDate()}</div><div class="jos-day-meta">${meta}</div></div>`;
}
html += '</div>';
dv.el("div", html);
```

> [!multi-column]
>
> > [!col-active]
> > **🎯 TAGAD**
> > `INPUT[text(placeholder(Ko es daru tieši šobrīd...)):tagad_task]`
> >
> > 📋 [[05-tasks/today|Šodien]] · 📓 [[07-logs/2026/05/2026-05-12|Šodienas log]]
>
> > [!col]
> > **⚡ ĀTRĀ PIEZĪME**
> > `INPUT[text(placeholder(Brain dump — met visu šeit...)):inbox_capture]`
> >
> > *Vakarā 5 min — pārvieto vai izdzēs*

```dataviewjs
const todayPath = "05-tasks/today";
const today = dv.pages(`"${todayPath}"`).file.tasks;
const open = today.where(t => !t.completed).length;
const doneToday = today.where(t => t.completed).length;

const logs = dv.pages('"07-logs"').where(p => p.type === "log");
const weekAgo = new Date(); weekAgo.setDate(weekAgo.getDate() - 7);
const weekLogs = logs.where(p => p.file.cday.toMillis() > weekAgo.getTime()).length;

const projects = dv.pages('"01-projects"').where(p => p.status === "active").length;

dv.el("div", `
<div class="jos-stats">
  <div class="jos-stat"><div class="jos-stat-value">${open}</div><div class="jos-stat-label">Atvērti</div></div>
  <div class="jos-stat"><div class="jos-stat-value">${doneToday}</div><div class="jos-stat-label">Šodien ✓</div></div>
  <div class="jos-stat"><div class="jos-stat-value">${weekLogs}</div><div class="jos-stat-label">Logi nedēļā</div></div>
  <div class="jos-stat"><div class="jos-stat-value">${projects}</div><div class="jos-stat-label">Aktīvi projekti</div></div>
</div>
`);
```

> [!multi-column]
>
> > [!col]
> > **📋 Šodien — top uzdevumi**
> >
> > ```tasks
> > not done
> > path includes 05-tasks/today
> > limit 6
> > short mode
> > ```
>
> > [!col]
> > **🚀 Aktīvie projekti**
> >
> > ```dataviewjs
> > const pages = dv.pages('"01-projects"').where(p => p.type === "project").sort(p => p.file.mtime, "desc").limit(6);
> > const rows = pages.map(p => {
> >   const isReadme = p.file.name === "README";
> >   const folderName = p.file.folder.split("/").pop();
> >   const displayName = p.title || (isReadme ? folderName : p.file.name);
> >   const link = dv.fileLink(p.file.path, false, displayName);
> >   const status = p.status || "";
> >   const icon = status === "active" ? "🟢" : status.includes("paused") ? "⏸️" : status === "done" ? "✅" : "—";
> >   return [link, icon];
> > });
> > dv.table(["", ""], rows);
> > ```

```dataviewjs
const start = new Date(2026, 4, 11);
const now = new Date();
const day = Math.min(10, Math.floor((now - start) / 86400000) + 1);
const pct = Math.round((day / 10) * 100);

const planLink = "01-projects/ai-os-build-plan.md";

let html = `<div class="jos-build-wrap">
  <div class="jos-build-header">
    <span class="jos-build-title">🏗️ AI OS BUILD — 10 dienu sprints</span>
    <span class="jos-build-sub">D${day}/10 · ${pct}% · <a class="internal-link" href="${planLink}">pilns plāns →</a></span>
  </div>
  <div class="jos-build">`;
for (let i = 1; i <= 10; i++) {
  const cls = i < day ? "jos-day-done" : i === day ? "jos-day-active" : "jos-day-todo";
  html += `<a class="jos-day ${cls} internal-link" href="${planLink}">D${i}</a>`;
}
html += `<div class="jos-progress-bar"><div class="jos-progress-fill" style="width:${pct}%"></div></div>`;
html += `<span class="jos-progress-pct">${pct}%</span></div></div>`;
dv.el("div", html);
```

> [!multi-column]
>
> > [!col]
> > **⚙️ Sistēma**
> >
> > | | |
> > |--|--|
> > | Vault + plugins | ✅ |
> > | Meta-Bind + Dataview | ✅ |
> > | Templater + Tasks | ✅ |
> > | Syncthing | ✅ D3 |
> > | Git + GitHub | ⏳ D4 |
> > | Hetzner + Hermes | ⏳ D5–6 |
> > | Telegram bot | ⏳ D7 |
>
> > [!col]
> > **📁 Pēdējās izmaiņas**
> >
> > ```dataview
> > TABLE WITHOUT ID file.link as "", dateformat(file.mtime, "HH:mm") as "Laiks"
> > FROM ""
> > WHERE file.name != "DASHBOARD" AND file.name != "hot"
> >   AND file.name != "index" AND file.name != "CLAUDE"
> >   AND !contains(file.path, ".obsidian")
> >   AND !contains(file.path, "04-archive")
> >   AND !contains(file.path, "99-templates")
> > SORT file.mtime DESC
> > LIMIT 5
> > ```
>
> > [!col]
> > **🛠️ Ātrie rīki**
> >
> > ```meta-bind-button
> > label: "📝 Jauna piezīme"
> > style: default
> > id: btn-new
> > actions:
> >   - type: command
> >     command: "file-explorer:new-file"
> > ```
> >
> > ```meta-bind-button
> > label: "🔍 Meklēt"
> > style: default
> > id: btn-search
> > actions:
> >   - type: command
> >     command: "switcher:open"
> > ```
> >
> > ```meta-bind-button
> > label: "🌐 Graph"
> > style: default
> > id: btn-graph
> > actions:
> >   - type: command
> >     command: "graph:open"
> > ```
> >
> > ```meta-bind-button
> > label: "📓 Šodienas log"
> > style: default
> > id: btn-log
> > actions:
> >   - type: open
> >     link: "[[07-logs/2026/05/2026-05-12]]"
> > ```
