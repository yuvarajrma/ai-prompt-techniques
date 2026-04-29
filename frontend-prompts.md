# Frontend Prompts (React)

Reusable two-liner prompts for common frontend tasks and features.

---

## Component Creation

**Form Component**

```
Create a reusable, controlled form component with validation using the standard input-label-error pattern.
Follow the container-presentational split — keep logic in a hook and rendering in the component.
```

**Modal / Dialog**

```
Build an accessible modal component with overlay, close-on-escape, and focus trapping.
Use the portal pattern to render it outside the main DOM tree and accept children for flexible content.
```

**Data Table**

```
Create a sortable, paginated table component that accepts column definitions and row data as props.
Follow the compound component pattern — expose Table, Table.Header, Table.Row, and Table.Cell as composable parts.
```

**Card / Tile**

```
Build a reusable card component with slots for image, title, body, and actions using the composition pattern.
Keep it purely presentational — no internal state, all content passed via props or children.
```

---

## State Management

**Global State Setup**

```
Set up a lightweight global state using React Context and useReducer following the flux/reducer pattern.
Separate the state provider, action creators, and selectors into their own files for maintainability.
```

**Form State Hook**

```
Create a custom useForm hook that manages field values, touched state, validation errors, and submission.
Follow the hook-encapsulation pattern — the component should only call the hook and spread returned props.
```

**Async Data Hook**

```
Build a custom useFetch hook that handles loading, error, and data states for any API call.
Follow the status-machine pattern — track idle, loading, success, and error as explicit states, not booleans.
```

---

## Routing & Navigation

**Protected Route**

```
Create a ProtectedRoute wrapper that redirects unauthenticated users to the login page.
Use the higher-order component / guard pattern — wrap route elements and check auth state before rendering.
```

**Breadcrumb Navigation**

```
Build a dynamic breadcrumb component that reads the current route and generates navigation links.
Follow the observer pattern — subscribe to route changes and derive breadcrumb segments from the path.
```

---

## UI Features

**Toast / Notification System**

```
Create a toast notification system with auto-dismiss, stacking, and severity levels (success, error, info, warning).
Use the pub-sub pattern — expose a global notify function that pushes messages to a shared context queue.
```

**Theme Toggle (Dark/Light)**

```
Implement a theme toggle that switches between dark and light mode and persists the preference.
Follow the provider pattern — wrap the app in a ThemeProvider and expose the toggle via context.
```

**Infinite Scroll**

```
Add infinite scroll to a list view that fetches the next page when the user nears the bottom.
Use the intersection observer pattern — attach an observer to a sentinel element and trigger fetch on visibility.
```

**Skeleton Loader**

```
Create a skeleton/placeholder component that mirrors the layout of the real content during loading.
Follow the proxy pattern — render the skeleton in place of the actual component until data arrives.
```

---

## API Integration

**API Service Layer**

```
Set up a centralized API service module with a configured Axios/fetch instance, interceptors, and base URL.
Follow the singleton-service pattern — export one pre-configured instance and use it across all feature modules.
```

**Error Boundary**

```
Build a React error boundary that catches render errors and shows a fallback UI with a retry option.
Follow the decorator pattern — wrap feature sections individually so one crash doesn't take down the whole app.
```

---

## Performance

**Lazy Loading Routes**

```
Split route-level components using React.lazy and Suspense with a loading fallback.
Follow the code-splitting pattern — each route chunk loads on demand to reduce the initial bundle size.
```

**Memoized List Rendering**

```
Optimize a large list by wrapping items in React.memo and stabilizing callbacks with useCallback.
Follow the pure-component pattern — ensure items only re-render when their own props actually change.
```

---

## Testing

**Component Unit Test**

```
Write a unit test for a component using React Testing Library — render, simulate user interaction, and assert output.
Follow the arrange-act-assert pattern and test behavior from the user's perspective, not implementation details.
```

**Hook Unit Test**

```
Write a test for a custom hook using renderHook — call the hook, act on its returned functions, and assert state changes.
Follow the isolation pattern — test the hook independently without mounting a full component tree.
```

---

## Design & Color Scheme

**Design System Tokens**

```
Define a design token file with color palette, spacing scale, font sizes, border radii, and shadows as CSS variables or a JS theme object.
Follow the single-source-of-truth pattern — every component should reference tokens instead of hardcoding values.
```

**Color Palette Generator**

```
Create a cohesive color palette with primary, secondary, accent, neutral, success, warning, and error colors including light/dark shades.
Follow the 60-30-10 rule — assign dominant, secondary, and accent colors proportionally across the UI for visual balance.
```

**Typography Scale**

```
Set up a typography scale with consistent font families, sizes, weights, and line heights for headings, body, captions, and labels.
Follow the modular-scale pattern — derive sizes from a base value and ratio so the hierarchy feels mathematically harmonious.
```

**Consistent Spacing System**

```
Define a spacing system using a base unit (4px or 8px) with a scale (xs, sm, md, lg, xl, xxl) applied to margins, paddings, and gaps.
Follow the grid-unit pattern — all spacing values should be multiples of the base unit to keep layouts visually aligned.
```

**Dark Mode Color Scheme**

```
Create a dark mode color scheme that maps each light-mode token to a dark equivalent with proper contrast ratios.
Follow the semantic-color pattern — use names like background-primary and text-secondary so swapping themes only changes values, not code.
```

**Accessible Color Contrast**

```
Audit and adjust the color palette so all text-background combinations meet WCAG AA contrast ratios (4.5:1 for normal text, 3:1 for large).
Follow the accessibility-first pattern — define colors with contrast compliance as a hard constraint, not an afterthought.
```

**Gradient & Accent Styling**

```
Create a set of reusable gradient and accent styles (buttons, banners, highlights) using the brand color palette.
Follow the utility-class pattern — define gradients as composable CSS classes or styled-component mixins for easy reuse.
```

**Responsive Color Adaptation**

```
Adjust color intensity and contrast for different screen sizes and contexts (e.g., lighter tones on mobile cards, stronger contrast on dense dashboards).
Follow the adaptive-design pattern — use media queries or container queries to tweak color tokens per breakpoint.
```

**Brand-Consistent Icon & Illustration Style**

```
Define a style guide for icons and illustrations — stroke width, corner radius, color usage, and sizing that matches the brand palette.
Follow the design-system pattern — all icons should share the same visual weight and use colors from the token set, not arbitrary values.
```

**Surface & Elevation System**

```
Create a surface/elevation system with layered background colors and shadow depths for cards, modals, dropdowns, and popovers.
Follow the material-elevation pattern — each elevation level has a defined background tint and shadow so depth is visually consistent.
```
