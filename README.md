# KarmCharge Project Management

A browser-based project planning workspace for creating, editing, presenting, and exporting multi-project Gantt plans.

## Features

- Multi-project workspaces stored in the browser
- Spreadsheet, board, Gantt, calendar, and dashboard views
- Parent tasks, subtasks, dependencies, priorities, progress, status, owners, and supporters
- Custom spreadsheet columns with text, number, dropdown, date, and checkbox types
- Team profiles with optional uploaded pictures
- Friday and Saturday weekend configuration
- Live read-only manager links with full-screen presentation mode
- Excel import template and Excel, PowerPoint, and current-view PDF exports
- Customizable management dashboard widgets

## Technology

- React 19 and TypeScript
- Next.js-compatible App Router through Vinext
- Tailwind CSS and shadcn/ui components
- Recharts dashboards
- Cloudflare Worker runtime
- Cloudflare D1 for shared manager views
- Cloudflare R2 for uploaded team pictures

## Local development

Requirements:

- Node.js 22.13 or newer
- npm

Install and start the local workspace:

```bash
npm ci
npm run dev
```

Run validation:

```bash
npm run lint
npm test
```

Create a production build:

```bash
npm run build
```

## Publish the source to GitHub

1. Create an empty repository on GitHub. Do not initialize it with a README or `.gitignore`.
2. Extract this source bundle and open a terminal in the extracted directory.
3. Run:

```bash
git init
git add .
git commit -m "Initial KarmCharge Project Management release"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
git push -u origin main
```

Replace `YOUR-USERNAME` and `YOUR-REPOSITORY` with your GitHub details.

## Storage and hosting

GitHub stores the source code but does not run this full-stack application by itself. GitHub Pages is not suitable because the application includes server routes and Cloudflare bindings.

The editable workspace uses browser local storage. Shared manager views use a D1 database, and team pictures use an R2 bucket. The binding names are declared in `.openai/hosting.json`:

- D1: `DB`
- R2: `BUCKET`

When deploying outside ChatGPT Sites, configure equivalent Cloudflare bindings and authentication behavior for the API routes under `app/api/`.

## Main source files

- `app/planner.tsx` — editable project workspace and all views
- `app/manager-view.tsx` — read-only manager presentation
- `app/model.ts` — project, task, team, and dashboard data types
- `app/exporters.ts` — Excel and PowerPoint import/export workflow
- `app/api/shares/` — shared manager-view API
- `app/api/team-images/` — team-picture upload and delivery API
- `db/schema.ts` — D1 schema
- `worker/index.ts` — Cloudflare Worker entry point

## Security notes

- Do not commit `.env` files, credentials, or access tokens.
- Review `.openai/hosting.json` before deploying under another Sites account; its `project_id` belongs to the original Site.
- Choose and add a software license before distributing the repository publicly.
