# Day 14 - Learn about CSS

- Build a custom coming soon template Project

- Flexbox Masterclass

---

## Project Structure

```
day-14/
├── Flexbox-Practice/
|    ├── 01-holy-grail-layout.html
|    ├── 02-navbar.html
│    ├── 03-card-grid.html
|    ├── 04-centering.html
|    ├── 05-sticky-footer.html
|    ├── 06-equal-height-columns.html
|    ├── 07-auto-margins-tricks.html
│    └── 08-nested-flexbox.html
|
├── Topic-01_Build-a-Custom-Coming-Soon-Template-Project/
|   ├── asstes/
|   |   └──chai-logo.png
│   ├── coming-soon.html
│   └── coming-soon.css
|
├── Topic-02_Flexbox-Masterclass/
│   ├── flexbox.html
│   └── flexbox.css
|
├── index.html          # Navigation Page
├── style.css
|
└── DAY-14.md           # Completed Documentation (This File)

```

---

## Table of Content

- [Topic - 1: Build a Custom Coming Soon Template Project](#topic---1-build-a-custom-coming-soon-template-project)
- [Topic - 2: Flexbox Masterclass](#topic---2-flexbox-masterclass)

---

## Topic - 1: Build a custom coming soon template Project

### Chai Landing Page - Coming Soon

A modern, clean "Coming Soon" landing page with gradient background and wave animation.

#### Project Overview

A responsive landing page designed for product launches or website maintenance periods. Features a centered content card with email notification signup.

#### Features

- **Gradient Background:** Purple to blue gradient (135deg)

- **Centered Layout:** Flexbox for perfect centering

- **Smooth Animations:** Button hover effects with scale and color transitions

- **Wave Footer:** SVG wave design at bottom

- **Custom Font:** Google Fonts (Noto Sans)

#### Technologies Used

- HTML5

- CSS3 (Flexbox, Transitions, Gradients)

- Google Fonts API

- SVG Graphics

#### Key CSS Concepts Applied

**1. Gradient Background**

```css
background: linear-gradient(135deg, #8a2be2, #4169e1);
/* Purple (#8a2be2) to Blue (#4169e1) at 135° angle */
```

**2. Flexbox Centering**

```css
display: flex;
justify-content: center;
align-items: center;
height: 100%;
```

**3. Form Input Focus State**

```css
input:focus {
  outline: none;
  border: 2px solid #7a3ff3;
}
```

**4. Button Hover Effect**

```css
button:hover {
  background-color: #340b5a;
  transform: scale(1.03);
}
```

**5. Absolute Positioning for SVG**

```css
svg {
  position: absolute;
  bottom: 0;
}
```

#### Challenges & Solutions

**Challenge 1: Centering Content**

**Problem:** Content not centered vertically and horizontally

**Solution:** Used Flexbox with `justify-content` and `align-items: center` on parent container with `height: 100vh`

**Challenge 2: SVG Wave Positioning**

**Problem:** Wave appearing in wrong position

**Solution:** Used `position: absolute` with `bottom: 0` to anchor SVG to bottom of page

**Challenge 3: Content Overlap with Wave**

**Problem:** Content card overlapping with SVG wave

**Solution:** Added `z-index: 2` to `.content` and `margin-bottom: 160px` to lift it above the wave

#### Key Features Breakdown

| Feature          | Implementation                                   |
| ---------------- | ------------------------------------------------ |
| **Layout**       | Flexbox centering                                |
| **Background**   | Linear gradient (135deg)                         |
| **Card Design**  | Semi-transparent white (`rgba(255,255,255,0.9)`) |
| **Input Focus**  | Purple border on focus                           |
| **Button Hover** | Color change + scale transform                   |
| **Footer Wave**  | Absolute positioned SVG                          |

#### **Future Improvements**

- [ ] Add form validation with JavaScript

- [ ] Implement email collection backend

- [ ] Add success message after form submission

- [ ] Include social media links

- [ ] Add countdown timer to launch date

- [ ] Make wave animation dynamic

#### Responsive Design

- Uses `max-width: 350px` on content card
- Flexible padding with `rem` units
- SVG wave scales to full viewport width
- Works on mobile, tablet, and desktop

#### Color Palette

| Color        | Hex       | Usage                             |
| ------------ | --------- | --------------------------------- |
| Purple       | `#8a2be2` | Gradient start, button background |
| Blue         | `#4169e1` | Gradient end, SVG wave            |
| Dark Purple  | `#340b5a` | Button hover                      |
| Light Purple | `#7a3ff3` | Input focus border                |
| Text Dark    | `#333`    | Heading                           |
| Text Gray    | `#666`    | Paragraph                         |

#### Learning Outcomes

- Creating gradient backgrounds with `linear-gradient()`
- Centering elements with Flexbox
- Implementing smooth CSS transitions
- Using `transform: scale()` for hover effects
- Positioning SVG graphics with absolute positioning
- Managing z-index for layered elements
- Creating focus states for better UX

---

## Topic - 2: Flexbox Masterclass

A complete visual guide to CSS Flexbox with live examples of every property and practical real-world uses.

This section is an interactive learning resource for mastering CSS Flexbox. It includes 15 visual demonstrations covering every flexbox property, common patterns, and 8 practice examples to help you learn by doing.

### What is Flexbox?

**Flexbox (Flexible Box Layout)** is a CSS layout module designed to:

- Create flexible, responsive layouts easily
- Align and distribute space among items in a container
- Work in any direction (horizontal or vertical)
- Handle dynamic or unknown sizes

**Key Advantage:** Unlike older layout methods (floats, tables), Flexbox is purpose-built for modern responsive layouts and makes previously difficult tasks trivial (like vertical centering, equal-height columns).

### Understanding Flexbox Axes

Flexbox works with two perpendicular axes:

#### **Main Axis**

- Direction set by `flex-direction` property
- **In `row` (default):** Horizontal (left to right)
- **In `column`:** Vertical (top to bottom)
- Controlled by `justify-content`

#### **Cross Axis**

- Always perpendicular to the main axis
- **In `row`:** Vertical (top to bottom)
- **In `column`:** Horizontal (left to right)
- Controlled by `align-items` and `align-content`

**Visual:**

```
flex-direction: row (default)
┌─────────────────────────────────┐
│  ← Main Axis (horizontal) →     │
│  ↑                              │
│  │ Cross Axis (vertical)        │
│  ↓                              │
└─────────────────────────────────┘

flex-direction: column
┌─────────────────────────────────┐
│  ← Cross Axis (horizontal) →    │
│  ↑                              │
│  │ Main Axis (vertical)         │
│  ↓                              │
└─────────────────────────────────┘
```

### Key Flexbox Properties

#### **Container Properties (Applied to Parent)**

Properties you apply to the flex container to control layout of all children.

**1. `display: flex`**

Activates flexbox layout on the container.

```css
.container {
  display: flex;
}
```

**2. `flex-direction`**

Defines the direction of the main axis.

**Values:**

- `row` (default) - Left to right
- `row-reverse` - Right to left
- `column` - Top to bottom
- `column-reverse` - Bottom to top

```css
.container {
  flex-direction: row; /* Items arranged horizontally → */
  flex-direction: column; /* Items arranged vertically ↓ */
}
```

**Use case:** Navigation bars (row), mobile menus (column)

**3. `justify-content`**

Controls alignment along the **main axis** (horizontal in row, vertical in column).

**Values:**

- `flex-start` (default) - Items at start
- `flex-end` - Items at end
- `center` - Items centered
- `space-between` - Even spacing, no space at edges
- `space-around` - Even spacing, half space at edges
- `space-evenly` - Equal spacing everywhere

```css
.container {
  justify-content: space-between; /* Items spread out evenly */
}
```

**Use case:**

- `space-between` - Navbar with logo left, menu right
- `center` - Centered hero content
- `space-evenly` - Feature cards with equal spacing

**4. `align-items`**

Controls alignment along the **cross axis** (vertical in row, horizontal in column).

**Values:**

- `stretch` (default) - Items stretch to fill container
- `flex-start` - Items at start of cross axis
- `flex-end` - Items at end of cross axis
- `center` - Items centered on cross axis
- `baseline` - Items aligned by text baseline

```css
.container {
  align-items: center; /* Vertically center items in row layout */
}
```

**Use case:**

- `center` - Perfect centering (with justify-content: center)
- `stretch` - Equal height cards
- `baseline` - Align text in different sized elements

**5. `flex-wrap`**

Controls whether items wrap to new lines when container is too small.

**Values:**

- `nowrap` (default) - All items on one line (may shrink)
- `wrap` - Items wrap to new lines
- `wrap-reverse` - Items wrap in reverse order

```css
.container {
  flex-wrap: wrap; /* Items move to next line if needed */
}
```

**Use case:** Responsive card grids, image galleries

**6. `align-content`**

Controls spacing between **multiple lines** of flex items (only works with `wrap`).

**Values:**

- `stretch` (default) - Lines stretch to fill space
- `flex-start` - Lines at start
- `flex-end` - Lines at end
- `center` - Lines centered
- `space-between` - Even spacing between lines
- `space-around` - Even spacing with half space at edges
- `space-evenly` - Equal spacing everywhere

```css
.container {
  flex-wrap: wrap;
  align-content: space-around; /* Space between wrapped rows */
}
```

**Note:** Has no effect if items are on a single line.

**7. `gap`**

Sets spacing between flex items (modern property).

```css
.container {
  gap: 20px; /* 20px between all items */
  gap: 20px 40px; /* 20px vertical, 40px horizontal */
  row-gap: 20px; /* Vertical spacing only */
  column-gap: 40px; /* Horizontal spacing only */
}
```

**Use case:** Clean spacing without margins (no margin collapse issues)

#### **Item Properties (Applied to Children)**

Properties you apply to individual flex items.

**1. `flex-grow`**

Controls how much an item grows relative to others when extra space is available.

**Default:** `0` (items don't grow)

```css
.item-1 {
  flex-grow: 1; /* Takes 1 part of available space */
}

.item-2 {
  flex-grow: 2; /* Takes 2 parts (twice as much as item-1) */
}
```

**Use case:** Making one element take up remaining space (main content in sidebar layout)

**2. `flex-shrink`**

Controls how much an item shrinks when space is limited.

**Default:** `1` (items can shrink)

```css
.item {
  flex-shrink: 0; /* Item won't shrink below its size */
  flex-shrink: 2; /* Item shrinks twice as fast as others */
}
```

**Use case:** Preventing logos or icons from shrinking in navigation

**3. `flex-basis`**

Sets the initial size of an item before growing or shrinking.

**Default:** `auto` (uses item's content size)

```css
.item {
  flex-basis: 200px; /* Start at 200px wide */
  flex-basis: 50%; /* Start at 50% of container */
  flex-basis: auto; /* Use content size */
}
```

**Use case:** Setting minimum widths for cards, columns

**4. `flex` (Shorthand)**

Combines `flex-grow`, `flex-shrink`, and `flex-basis`.

**Syntax:** `flex: <grow> <shrink> <basis>`

```css
.item {
  flex: 1; /* Same as: 1 1 0% */
  flex: 1 0 200px; /* Grow, don't shrink, start at 200px */
  flex: 0 0 150px; /* Fixed width, no grow/shrink */
}
```

**Common patterns:**

- `flex: 1` - Equal width items that fill space
- `flex: 0 0 auto` - Item keeps its natural size
- `flex: 2` - Item is 2x wider than siblings with `flex: 1`

**5. `align-self`**

Overrides container's `align-items` for a specific item.

**Values:** Same as `align-items` (flex-start, flex-end, center, baseline, stretch)

```css
.container {
  align-items: flex-start; /* All items at top */
}

.special-item {
  align-self: flex-end; /* This one at bottom */
}
```

**Use case:** Featured card with different alignment, special badge positioning

**6. `order`**

Changes visual order of items without changing HTML.

**Default:** `0` (items appear in source order)

```css
.item-1 {
  order: 3;
} /* Appears third */
.item-2 {
  order: 1;
} /* Appears first */
.item-3 {
  order: 2;
} /* Appears second */
```

**Use case:** Responsive reordering (mobile vs desktop layout order)

### Demonstrations Included

#### **Basic Properties**

1. Default Flex (row)
2. Flex Direction: Column
3. Justify Content: Space Between
4. Align Items: Center
5. Flex Wrap: Wrap
6. Align Content: Space Around
7. Order Property
8. Flex Grow
9. Align Self

#### **Advanced Properties**

10. Flex Shrink
11. Flex Basis
12. Flex Shorthand
13. Gap Property

#### **All Property Values**

14. All Justify-Content Values (6 variations)
15. All Align-Items Values (5 variations)

#### **Practical Real-World Examples**

1.  Holy Grail Layout (header, sidebar, main, ads, footer)
2.  Navigation Bar (logo left, menu right)
3.  Responsive Card Grid (3 columns → 2 → 1)
4.  Perfect Centering (horizontal + vertical)
5.  Sticky Footer (footer always at bottom)
6.  Equal Height Columns
7.  Auto Margins Trick (pushing items to edges)
8.  Nested Flexbox (flexbox inside flexbox)

### Common Flexbox Patterns

#### **Pattern 1: Perfect Centering**

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
```

**Use:** Login forms, hero sections, modals

#### **Pattern 2: Navbar (Space Between)**

```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

**Use:** Logo left, menu right

#### **Pattern 3: Equal Width Columns**

```css
.column {
  flex: 1; /* All columns equal width */
}
```

**Use:** Feature sections, pricing tables

#### **Pattern 4: Sidebar Layout**

```css
.sidebar {
  flex: 0 0 250px; /* Fixed width sidebar */
}

.main {
  flex: 1; /* Main content takes remaining space */
}
```

**Use:** Admin panels, documentation sites

#### **Pattern 5: Responsive Grid**

```css
.container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.card {
  flex: 1 1 calc(33.333% - 20px); /* 3 columns */
  min-width: 250px; /* Wraps on small screens */
}
```

**Use:** Product cards, image galleries

### Key Concepts to Remember

#### **1. Main vs Cross Axis**

- Main axis = direction of `flex-direction`
- `justify-content` controls main axis
- `align-items` controls cross axis

#### **2. Flex Shorthand**

```css
flex: 1; /* Most common: grow, shrink, 0% basis */
flex: 1 0 auto; /* Explicit: grow 1, no shrink, auto basis */
```

#### **3. Gap vs Margin**

- `gap` is cleaner (no margin collapse, no extra space at edges)
- Use `gap` for modern projects
- Use `margin` if you need browser compatibility with IE11

#### **4. When to Use Flexbox vs Grid**

- **Flexbox:** One-dimensional layouts (rows OR columns)
  - Navigation bars
  - Card rows
  - Vertical lists
- **Grid:** Two-dimensional layouts (rows AND columns)
  - Page layouts
  - Image galleries
  - Complex grids

### Challenges Faced & Solutions

#### **Challenge 1: Items Not Centering**

**Problem:** Used only `justify-content: center`, items still at top

**Solution:** Need both properties for perfect centering:

```css
.container {
  display: flex;
  justify-content: center; /* Horizontal */
  align-items: center; /* Vertical */
  height: 100vh; /* Container needs height! */
}
```

#### **Challenge 2: Flex Items Overflowing**

**Problem:** Items shrinking too small or overflowing container

**Solution:** Use `flex-wrap` or set `min-width`:

```css
.container {
  flex-wrap: wrap; /* Allow wrapping */
}

.item {
  flex: 1 1 200px; /* With minimum size */
  min-width: 200px; /* Won't shrink below this */
}
```

#### **Challenge 3: Unequal Heights**

**Problem:** Cards in a row have different heights

**Solution:** Use `align-items: stretch` (default) or set `align-items: flex-start` if you want natural heights:

```css
.container {
  display: flex;
  align-items: stretch; /* All items same height */
}

.item {
  /* Don't set height - let flex handle it */
}
```

#### **Challenge 4: Gap Not Working**

**Problem:** `gap` property not creating space

**Solution:** Check browser support (IE11 doesn't support), or ensure `display: flex` is set:

```css
.container {
  display: flex; /* Required! */
  gap: 20px; /* Now it works */
}
```

---

### Learning Outcomes

- Understand the flexbox mental model (axes, containers, items)
- Use all container properties (`display`, `flex-direction`, `justify-content`, etc.)
- Use all item properties (`flex-grow`, `flex-shrink`, `order`, etc.)
- Create common layouts (navbars, grids, centering)
- Debug flexbox issues
- Build responsive layouts without media queries (flex-wrap)

---

### Additional Resources

- [MDN Flexbox Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout)
- [CSS Tricks Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Flexbox Froggy](https://flexboxfroggy.com/) - Interactive game to learn flexbox
- [Flexbox Defense](http://www.flexboxdefense.com/) - Tower defense game with flexbox

---

**Note:** `gap` property requires newer browsers (Chrome 84+, Firefox 63+, Safari 14.1+)

---

### 🐢Tortoise Learning Tip

**Don't try to memorize everything** Instead:

1. Understand the **two axes** concept
2. Remember `justify-content` = main axis, `align-items` = cross axis
3. Know `flex: 1` makes equal-width items
4. Use this as a reference when building layouts
5. Practice with real projects

The more you use flexbox, the more natural it becomes

---

**Built with the Tortoise approach 🐢, Learn by doing, mastering each fundamental property one step at a time.**
