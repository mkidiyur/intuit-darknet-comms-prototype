---
name: create_prototype
description: Create an HTML prototype and Figma spec for a new product feature using the Intuit Security Center design system. Invoke when the user wants to build a screen mockup, prototype, or UI flow for a feature.
---

Create a complete HTML prototype for the following feature. The user will provide:
- **Feature name**
- **PRD / product requirements** (pasted inline)

## What to produce

A single self-contained HTML file named `<feature-name>-prototype.html` that contains:

1. **Multiple prototype screens** — one per key user-facing state or flow step described in the PRD
2. **A Figma spec section** at the bottom of the file

---

## Design system to follow

Match the exact style from the user's existing prototypes:

**Fonts:** `'AvenirNext', 'Avenir Next', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif`

**Colors:**
- Primary blue: `#0077C5` (actions, links, active nav)
- Accent green: `#2ca01c` (logo highlight)
- Warning yellow: `#F5A623` / `#FFF8E7` (background)
- Critical red: `#D0021B` / `#FEF0F0` (background)
- Text: `#2d2d2d`
- Background: `#f4f4f6` (page), `#fafafa` (main content), `#fff` (cards/nav)
- Border: `#e5e5e5`

**Shell components to include on every screen:**

Top nav (52px, white, border-bottom):
- Left: Intuit logo — `intuit` in `#0077C5`, last letter `t` in `#2ca01c`
- Right: search icon + notification bell with badge dot

Sidebar (200px, white, border-right):
- Nav items with active state: left border `#0077C5`, background `#e8f4fb`, blue bold text
- Inactive: `#3d3d3d` text, hover `#f5f5f5`

Main content area (flex: 1, padding 0 40px 60px, background `#fafafa`)

**Prototype screen wrapper:**
```html
<div class="proto-label">
  <strong>Screen N — Screen Name</strong>
  Short description of what state this screen represents
</div>
<div class="browser">
  <!-- top-nav, page-layout with sidebar + main-content -->
</div>
```

**Component patterns:**

Cards (`.card`): white, border `1px solid #e5e5e5`, border-radius 8px, padding 24px, margin-bottom 16px
Card rows (`.card-row`): flex, label in `#6b6b6b` 13px, value in `#2d2d2d` 14px

Banners:
- Warning: yellow bg `#FFF8E7`, border-left 4px `#F5A623`
- Critical: red bg `#FEF0F0`, border-left 4px `#D0021B`
- Include icon + body text + action buttons + × dismiss button

Modals (`.modal-overlay` → `.modal`):
- Full-screen overlay `rgba(0,0,0,0.5)`
- Modal box: white, border-radius 12px, padding 32px, max-width 480px
- Include title, body, `.modal-actions` with button group
- `modalIn` keyframe animation

Buttons:
- `.btn-primary`: solid `#0077C5`, white text
- `.btn-secondary`: outlined `#0077C5`, blue text
- `.btn-danger`: solid `#D0021B`, white text
- `.btn-dismiss`: text-only, `#6b6b6b`

Status badges: `.badge-action-needed` (yellow), `.badge-restricted` (red), inline with text

Notification bell: `.bell-wrap` with `.bell-dot`, click toggles `.notif-dropdown` with unread items

Toast: fixed bottom-center, opacity transition on `.show`

**Animations:**
```css
@keyframes dropIn { from { opacity:0; transform:translateY(-8px); } to { opacity:1; transform:translateY(0); } }
@keyframes modalIn { from { opacity:0; transform:scale(0.95); } to { opacity:1; transform:scale(1); } }
```

---

## Screen structure

Read the PRD carefully and identify:
1. The **happy path** screens (normal user flow)
2. Any **alert / warning states**
3. Any **modal dialogs or confirmation flows**
4. Any **success / confirmation states**

Create one prototype screen per distinct state. Aim for 3–6 screens for a typical feature. Each screen should be a full-page render (not just the changed component), so reviewers can see full context.

---

## Figma spec section

After all screens, add a `<section class="figma-spec">` that documents:
- **Feature overview** — 1-2 sentence summary
- **Screens list** — name + description of each screen
- **User flow** — numbered steps describing the end-to-end journey
- **Components used** — list all UI components with their states
- **Color tokens** — table of colors used with their hex values and usage
- **Copy / content** — key strings, labels, and microcopy used in the prototype
- **Interaction notes** — any click targets, hover states, or transitions

Style the Figma spec section with a dark background (`#1e1e2e`) and light text to visually separate it from the prototypes.

---

## Output

- Write the file to the current working directory as `<feature-name>-prototype.html`
- Use kebab-case for the filename
- Keep all CSS inline in a `<style>` block in `<head>`
- Keep all JS inline in a `<script>` block before `</body>`
- No external dependencies — fully self-contained
- After writing the file, confirm the filename and list the screens created
