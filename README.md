# FlowBoard — Single Page Application

FlowBoard is a responsive project-management dashboard built with plain HTML, CSS and JavaScript. It demonstrates client-side navigation, dynamic DOM rendering, local application state, task management and responsive layouts.

## Run locally
1. Download and extract `flowboard-spa.zip`.
2. Open `index.html` in a modern browser.
3. No build step, package manager or server is required.

For the most consistent local development experience, use VS Code Live Server or another static HTTP server.

## Features
- Four client-side views: Overview, Projects, My tasks and Team.
- Hash-based routing using the browser URL and `hashchange` event.
- Browser back/forward navigation.
- Dynamic project and task rendering from JavaScript data.
- Add task and project interactions.
- Task completion and reopening with live state updates.
- Search and status filtering for tasks and projects.
- Responsive sidebar navigation for mobile screens.
- Accessible labels, live status messages and semantic page regions.

## Project structure
```
flowboard-spa/
├── index.html
├── styles.css
├── app.js
├── README.md
└── TECHNICAL_REPORT.md
```

## Architecture
`index.html` provides the persistent application shell. `styles.css` controls layout, visual design, responsive breakpoints and interaction states. `app.js` contains the data model, rendering functions, event delegation and hash router. The application uses a single root content region, replacing its contents when the route changes rather than reloading the document.

## Routing
Routes are represented by URL hashes: `#/dashboard`, `#/projects`, `#/tasks` and `#/team`. The `navigate` helper updates the hash; `hashchange` calls `render()`. This makes routes bookmarkable and allows browser history navigation without a full page refresh.

## State and limitations
The sample data is held in the in-memory `state` object. Changes are reflected immediately while the page remains open, but are not persisted after a full reload. The invite action is a demonstration and does not send email. Authentication, server APIs and database storage are outside this simulation's scope.

## Testing checklist
- [ ] Open the app and confirm the Overview renders.
- [ ] Navigate through all four sections.
- [ ] Use browser Back and Forward.
- [ ] Search and filter projects and tasks.
- [ ] Add a task and a project.
- [ ] Mark a task complete and reopen it.
- [ ] Test at desktop and mobile viewport widths.
- [ ] Confirm there are no missing local assets or console errors.
