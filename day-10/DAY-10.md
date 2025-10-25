# Day 10 - Learn about CSS

- The current state of CSS

- You can write css at 3 places

---

### Project Structure:

```
day-10/
├── Topic-01_Current-State-of-CSS/
│   ├── index.html
│   └── style.css
|
├── Topic-02_Ways-to-Write-CSS/
│   ├── 01-inline-css/
|   |   └── inine-css-example.html
│   ├── 02-internal-css/
|   |   └── internal-css-example.html
|   └── 03-external-css/
|       ├── index.html
|       └── external-css-example.css
|
├── index.html          # Navigation Page
├── style.css
|
└── DAY-10.md           # Complete Documentation(This File)
```

---

## Table of Content

- [Topic - 1: The current state of CSS](#topic---1-the-current-state-of-css)
- [Topic - 2 : You can write css at 3 places](#topic---2-you-can-write-css-at-3-places)

---

## Topic - 1: The current state of CSS

- Code Files

  - **[The current state of CSS](./Topic-01_Current-State-of-CSS/index.html)**

**Introduction**

- CSS is an Art itself.

- CSS stands for **Cascading Style Sheets**.

- CSS has two parts:

  1. Learning the foundation

  2. Making website beautiful(the more you know the foundation, easier it is to make beautiful websites).

- It describes the visual styling and representation of the content written in HTML.

- It consists of countless properties that developer uses to format the content (text, images, links etc)

**The Current State of CSS:**

Modern CSS is powerful and evolving rapidly. Today, CSS supports:

**Layout Systems:**

- **Flexbox & Grid** - Layout systems that replaced float-based layouts

- **Subgrid** - Nested grids that align with parent grid

**Dynamic Styling:**

- **CSS Variables (Custom Properties)** - Reusable values: `--main-color: #3b82f6;`

- **Container Queries** - Style elements based on their parent's size, not just viewport

- **Cascade Layers (@layer)** - Better control over specificity and style organization

**Responsive Design:**

- **Media Queries** - Device-specific styling

- **Modern sizing functions** - `clamp()`, `min()`, `max()`

**Advanced Selectors:**

- **:has() Selector** - The "parent selector" developers always wanted.

- **CSS Nesting** - Write nested selectors natively (not just in preprocessors!)

**Visual Effects:**

- **Animations & Transitions** - Smooth, performant animations

- **View Transitions API** - Seamless page state changes

- **Scroll-driven Animations** - Animations triggered by scroll position

**Color & Design:**

- **New Color Spaces** - `oklch()`, `color-mix()`, wider gamut colors

**Nowadays, you can write CSS using utility-based frameworks and component libraries such as:**

**Utility-First Frameworks:**

- Tailwind CSS

- Bootstrap

**Component Libraries:**

- shadcn/ui

- Chakra UI

- Ant Design

- Daisy UI

**CSS Frameworks:**

- Materialize

- Flowbite

**UI Component Collections:**

- Magic UI

- Aceternity UI

- And many more...

- CSS has become more developer-friendly with better browser support and reduced dependency on external layout hacks (like floats and tables).

## Topic - 2: You can write css at 3 places

- Code Files

  - **[Inline CSS](./Topic-02_Ways-to-Write-CSS/01-inline-css/inline-css-example.html)**

  - **[Internal CSS](./Topic-02_Ways-to-Write-CSS/02-internal-css/internal-css-example.html)**

  - **[External CSS](./Topic-02_Ways-to-Write-CSS/03-external-css/index.html)**

- The whole job of CSS has two core tasks::

  1. Select the Element

  2. Style the Element

- The ability to write CSS and make websites visually appealing depends on three key aspects:

  1. Font (Typography):

     - The more beautiful the fome the more beautiful the website looks, it totally chnages the website look, feel, theme of the entire website because font consume najority of the space on the web-page.

  2. Images:

     - The more beautifully designed and the optimized the images, improve both UI and performance and consistent components improve user experience

  3. Component:

     - How good your buttons, cards, list look like, they define the visual identity and usability.

**You can write CSS in 3 ways or 3 places:**

**1. Inline CSS:**

Inside the HTML tag using style attribute, uses for quick styling for single elements. Inline CSS has highest specificity.

- [Code Example](./Topic-02_Ways-to-Write-CSS/01-inline-css/inline-css-example.html)

**2. Internal CSS:**

CSS inside `<style>` tag in the `<head>` section of HTML, use when styling a single-page projects.

- [Code Example](./Topic-02_Ways-to-Write-CSS/02-internal-css/internal-css-example.html)

**3. External CSS:**

CSS in a separate `.css` file linked using `<link>` tag. Used is production standard

- [Code Example](./Topic-02_Ways-to-Write-CSS/03-external-css/index.html)

## Key Takeaways:

- External CSS is the professional standard for production websites

- Focus on fonts, images, and components to create beautiful designs

- CSS has two core tasks: selecting elements and styling them
