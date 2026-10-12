# Theophany Bandure — Profile / Mini-Portfolio

A one-page semantic HTML5 profile and mini-portfolio site, built for
Practical Assignment 1 (Web Technologies, CIS2103, Africa University).

## Files

- `index.html` — the page markup
- `style.css` — the stylesheet
- `PROMPT_LOG.md` — the AI prompt, raw output, edited version, and reflection for the About-section copy (Part C)

## Accessibility: peer review issue & fix

**Issue found by peer reviewer (Thursday's practical session):** [Replace
this line with the actual issue your reviewer flagged — for example: "My
contact form inputs only had placeholder text instead of real `<label>`
elements, so a screen reader announced them as unlabelled."]

**Fix applied:** [Replace this line with what you changed — for example:
"Added a `<label for="...">` linked by `id` to every form input, and moved
the example text into a `placeholder` attribute only, so the label is
always announced."]

## Notes

- Contact form validation is handled entirely with native HTML5 attributes
  (`required`, `type="email"`, `pattern`, `minlength`) — no JavaScript.
- Fonts are loaded from Google Fonts (Fraunces for display, Source Sans 3
  for body text); the page degrades to system serif/sans-serif fonts if the
  fonts fail to load.
- Built on top of the file started in the Unit II practical session, per
  the assignment brief; extended with responsive CSS3 and Tailwind styling
  for Practical Assignment 2 (Unit III).

## Responsive Notes

### 1. Breakpoints Tested
The page was tested across three standard device viewports using the browser developer tools device toolbar:
- **Mobile (~375px):** Checked on iPhone SE / iPhone 12/13 profiles. Single-column stacked layout, touch-friendly tap targets, no horizontal scrolling, form controls span comfortable width with padding.
- **Tablet (~768px):** Checked on iPad Mini / standard tablet widths. Header shifts to horizontal layout (`md:flex-row`), About section splits into 1.6fr / 1fr columns, skills grid reflows cleanly, and contact form restricts to `max-w-lg`.
- **Desktop (~1280px):** Checked at standard desktop monitor resolution. Page container centers cleanly with max-width boundaries (`960px`), typography scales harmoniously via `clamp()`, and spacing expands appropriately.

### 2. Flexbox vs. CSS Grid Decisions
- **Flexbox (One-Dimensional Layouts):**
  - **Header & Navigation (`<header>`, `.site-nav ul`):** Used for linear distribution of elements across a horizontal axis, enabling links to wrap smoothly on narrow viewports and align cleanly to the right on tablet/desktop (`md:flex-row`, `md:justify-between`, `gap`).
  - **Site Footer (`.site-footer`):** Mobile-first `flex-direction: column` aligns copyright and links centrally, switching to `flex-direction: row` with `justify-content: space-between` on tablet screens.
  - **Form Rows (`form > div`):** Column flex groups organize `<label>` and `<input>` pairings with consistent internal gaps (`gap-1`).
- **CSS Grid (Two-Dimensional / Matrix Layouts):**
  - **About Section (`.about-grid`):** Two-dimensional relationship between the primary bio article and the complementary `quick-facts` sidebar. Structured mobile-first as `grid-template-columns: 1fr`, expanding to `grid-template-columns: 1.6fr 1fr` with `gap: 2.5rem` above `768px`.
  - **Skills Section (`.skills-list`):** Uses an auto-adapting grid formula: `grid-template-columns: repeat(auto-fit, minmax(8rem, 1fr))` with `gap: 0.75rem`. This automatically calculates the ideal column count based on available space without rigid breakpoint overrides.

### 3. Tailwind Utilities vs. Custom CSS Architecture
- **Tailwind Utility Classes (CDN):**
  - **Header & Navigation:** Implemented with utilities (`bg-gray-900 text-gray-50 py-8 md:py-10 flex flex-col md:flex-row md:items-end md:justify-between`) including responsive variants (`md:`) to handle layout and spacing changes.
  - **Contact Form:** Converted to utility classes (`flex flex-col gap-4 md:max-w-lg`, input styling, focus rings, and button hover states) demonstrating utility-first styling for interactive components.
- **Custom Stylesheet (`style.css`):**
  - Defines global CSS custom properties (`--paper`, `--ink`, `--panel`, `--accent`, font families) for unified brand tokens.
  - Contains mobile-first CSS reset, responsive typography clamps, and custom grid rules for the About and Skills sections.
  - Governs accessibility preferences such as `prefers-reduced-motion`.
- **Integration Rationale:** Core structural layouts and branding tokens reside in the external stylesheet, while repetitive component styling and responsive variants for the header and form leverage Tailwind utilities, ensuring intentionality without accidental style collisions.
