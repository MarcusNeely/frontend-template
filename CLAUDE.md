# Frontend Template

A React + Vite front end template with a full suite of Claude sub-agents for development assistance. Duplicate this repo when starting a new front end project.

## Tech Stack

| Tool | Purpose |
|------|---------|
| React 18 | UI framework |
| Vite | Build tool & dev server |
| JavaScript (ES2022+) | Language |
| npm | Package manager |
| Font Awesome | Icon library |
| Vitest + RTL | Testing |

> **Component Library:** Not pre-selected. Use the **Component Library Specialist** agent to choose the right library for this project's needs.

> **Fonts/Typefaces:** Not pre-selected. Use the **Component Library Specialist** agent to recommend fonts based on the project's design personality.

---

## Available Agents

Invoke agents by asking Claude: *"Use the [agent name] to..."*

| Agent | File | When to Use |
|-------|------|-------------|
| **Code Reviewer** | `.claude/agents/code-reviewer.md` | Review components or hooks before merging |
| **Animation Expert** | `.claude/agents/animation-expert.md` | Add or improve animations and transitions |
| **Responsive Design Expert** | `.claude/agents/responsive-design-expert.md` | Fix layout issues, mobile support, breakpoints |
| **Component Library Specialist** | `.claude/agents/component-library-specialist.md` | Choose a UI library, select fonts, implement components |
| **Documentation Generator** | `.claude/agents/documentation-generator.md` | Write JSDoc, component docs, README sections |
| **UI Tester** | `.claude/agents/ui-tester.md` | Write and maintain Vitest + RTL tests |
| **Frontend Architect** | `.claude/agents/frontend-architect.md` | Plan project structure, state management, routing |
| **API Assistant** | `.claude/agents/api-assistant.md` | Integrate REST/GraphQL APIs, handle async data |

**Example invocations:**
- *"Use the code reviewer to review `src/components/Header.jsx`"*
- *"Ask the animation expert to add a slide-in transition to the sidebar"*
- *"Have the frontend architect design the state management approach for user authentication"*
- *"Use the API assistant to integrate the products endpoint from our REST API"*

---

## Project Structure

```
src/
├── components/      # Shared, reusable UI components (no business logic)
│   └── ComponentName/
│       ├── ComponentName.jsx
│       ├── ComponentName.test.jsx
│       └── index.js
├── features/        # Feature-specific components and logic
│   └── featureName/
│       ├── components/
│       └── hooks/
├── hooks/           # Shared custom React hooks
├── pages/           # Route-level components (one per route)
├── services/        # API calls and external integrations
├── store/           # Global state (Zustand, if needed)
├── styles/          # Global CSS and design tokens
│   └── global.css
├── test/            # Test setup and shared mocks
├── utils/           # Pure utility functions
├── App.jsx
└── main.jsx
```

---

## Code Conventions

- **Components**: PascalCase, one per file, in their own folder with an `index.js` re-export
- **Hooks**: camelCase, prefixed with `use` (e.g., `useCart`, `useAuth`)
- **Services**: camelCase, suffixed with `Service` (e.g., `userService.js`)
- **Utils**: camelCase, descriptive name (e.g., `formatCurrency.js`)
- **CSS**: Use CSS variables from `src/styles/global.css` for all design tokens — no magic numbers
- **Imports**: Use `@/` alias for `src/` (e.g., `import Button from '@/components/Button'`)
- **No TypeScript**: Use JSDoc for type documentation on public APIs

---

## Environment Variables

All browser-accessible env vars must be prefixed with `VITE_`:

```
VITE_API_URL=https://api.example.com
VITE_APP_NAME=My App
```

- Never commit `.env` or `.env.local`
- Keep `.env.example` updated with all required variables (no real values)

---

## Font Awesome Usage

Font Awesome is pre-installed. Import only what you use (tree-shaken by default):

```jsx
import { FontAwesomeIcon } from '@fortawesome/react-fontawesome'
import { faUser, faSearch } from '@fortawesome/free-solid-svg-icons'
import { faHeart } from '@fortawesome/free-regular-svg-icons'
import { faGithub } from '@fortawesome/free-brands-svg-icons'

<FontAwesomeIcon icon={faUser} />
<FontAwesomeIcon icon={faGithub} size="2x" />
```

**Installed packages:**
- `@fortawesome/free-solid-svg-icons`
- `@fortawesome/free-regular-svg-icons`
- `@fortawesome/free-brands-svg-icons`

---

## Available Scripts

```bash
npm run dev           # Start development server (http://localhost:5173)
npm run build         # Build for production
npm run preview       # Preview production build locally
npm test              # Run tests in watch mode
npm run test:ui       # Run tests with Vitest UI
npm run test:coverage # Generate coverage report
```

---

## Starting a New Project from This Template

1. Click **"Use this template"** on GitHub (or clone and re-init git)
2. `npm install`
3. Copy `.env.example` → `.env` and fill in values
4. Update the `name` field in `package.json`
5. Update the `<title>` in `index.html`
6. Run the **Frontend Architect** agent to plan your feature structure
7. Run the **Component Library Specialist** agent to choose a UI library and fonts
8. Delete the placeholder content from `src/App.jsx`
9. `npm run dev` and start building

---

## Architecture Decisions

> Record decisions here as the project evolves so future developers understand the why.

| Decision | Choice | Reason |
|----------|--------|--------|
| Build tool | Vite | Fast HMR, native ESM, excellent DX |
| Language | JavaScript + JSDoc | Lower barrier, adequate type safety |
| Icons | Font Awesome | Comprehensive, tree-shakeable, familiar |
| Component library | TBD | Use Component Library Specialist agent |
| State management | TBD | Use Frontend Architect agent |
| Routing | TBD | Use Frontend Architect agent |
