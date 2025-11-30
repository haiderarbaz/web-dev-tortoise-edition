# Day 15 - Learn about CSS

- Meet grid layout in CSS - You will love it

- Grid Masterclass

---

## Project Structure

```
day-14/
├── Grid-Practice/
|    ├──
│    └──
|
├── Topic-01_Grid-Layout-Basics/
│   ├── grid-layout-basics.html
│   └── grid-layout-basics.css
|
├── Topic-02_Grid-Masterclass/
│   ├── grid.html
│   └── grid.css
|
├── navigation.html          # Navigation Page
|
└── DAY-15.md           # Completed Documentation (This File)

```

---

## Table of Contents

- [Topic - 01: Meet grid layout in CSS - You will love it](#topic---01-meet-grid-layout-in-css---you-will-love-it)
- [Topic - 02: Grid Masterclass](#topic---02-grid-masterclass)

---

## Topic - 01: Meet grid layout in CSS - You will love it

- Code Files

  - **[Grid Layout Basics](./Topic-01_Grid-Layout/grid-layout.html)**

A simple explaination of CSS Grid fundamentals showing how to create a grid container and position items using grid lines.

---

## Topic-01: Overview

- Creating a grid container
- Defining columns and rows
- Using grid gaps for spacing
- Positioning items using grid line numbers
- Spanning items across multiple columns and rows

---

## Concepts Covered:

1. **Grid Container Setup** - `display: grid`
2. **Column Definition** - `grid-template-columns: repeat(3, 1fr)`
3. **Row Definition** - `grid-template-rows: 100px 200px 100px`
4. **Gap/Spacing** - `gap: 4px` between grid items
5. **Item Positioning** - Using `grid-column` and `grid-row`
6. **Item Spanning** - Making items span multiple columns/rows

---

## Grid Structure

### **The Grid Layout:**

```
┌─────────────┬──────────┬──────────┐
│   Item 1    │          │          │
│  (spans 2   │          │          │
│   columns)  │  Item 2  │          │
├─────────────┤  (spans  │          │
│   Item 3    │  2 rows) │          │
├─────────────┼──────────┤          │
│   Item 4    │ Item 5   │          │
├─────────────┴──────────┴──────────┤
│          Item 6 (spans 2 cols)    │
└───────────────────────────────────┘
```

**Grid Configuration:**

- **Columns:** 3 equal columns (each 1 fraction unit)
- **Rows:** 3 rows with heights 100px, 200px, 100px
- **Gap:** 4px between all items

---

## Code Breakdown

### **1. Grid Container**

```css
.grid-container {
  display: grid; /* Activates grid layout */
  grid-template-columns: repeat(3, 1fr); /* 3 equal columns */
  grid-template-rows: 100px 200px 100px; /* 3 rows with fixed heights */
  gap: 4px; /* 4px spacing between items */
}
```

**What it means:**

- `repeat(3, 1fr)` = Create 3 columns, each taking 1 fraction of available space
- `1fr` = "fraction unit" (equal distribution)
- `gap: 4px` = Adds 4px space between grid cells (no gap at edges)

---

### **2. Grid Items - Default Behavior**

```css
.item {
  background-color: orange;
  border: 1px solid black;
}
```

**Default behavior:**

- Items auto-place in grid cells (left to right, top to bottom)
- Each item occupies one cell unless specified otherwise

---

### **3. Custom Item Positioning**

#### **Item 1 - Spans 2 Columns**

```css
.item1 {
  grid-column: 1/3; /* From column line 1 to 3 (spans columns 1-2) */
  grid-row: 1/2; /* From row line 1 to 2 (row 1) */
}
```

**Result:** Item 1 takes up columns 1 and 2 in row 1

---

#### **Item 2 - Spans 2 Rows**

```css
.item2 {
  grid-column: 3/4; /* Column 3 only */
  grid-row: 1/3; /* From row line 1 to 3 (spans rows 1-2) */
}
```

**Result:** Item 2 takes up column 3 and spans rows 1 and 2

---

#### **Item 6 - Spans 2 Columns**

```css
.item6 {
  grid-column: 2/4; /* From column line 2 to 4 (spans columns 2-3) */
  /* grid-row not specified, auto-places in next available row */
}
```

**Result:** Item 6 takes up columns 2 and 3 in row 3

---

## Grid Line Numbers Explained

### **Understanding Grid Lines:**

Grid lines are the dividing lines between columns and rows.

**Column Lines:**

```
  1       2       3       4
  │       │       │       │
  ├───────┼───────┼───────┤
  │ Col 1 │ Col 2 │ Col 3 │
  └───────┴───────┴───────┘
```

**Row Lines:**

```
1 ─────────────────────
2 ─────────────────────
3 ─────────────────────
4 ─────────────────────
```

**Example:**

- `grid-column: 1/3` means "start at line 1, end at line 3" (covers columns 1-2)
- `grid-row: 1/2` means "start at line 1, end at line 2" (covers row 1)

---

## Visual Result

### **What You See:**

```
Grid Container (3 columns × 3 rows):

Row 1 (100px):  [  Item 1 spans 2 cols  ] [    Item 2    ]
                                           [  (spans 2    ]
Row 2 (200px):  [  Item 3  ] [  Item 5  ] [   rows)      ]

Row 3 (100px):  [  Item 4  ] [  Item 6 spans 2 cols     ]
```

**Items that span(Spread out or Stretch):**

- Item 1: Occupies columns 1-2 in row 1
- Item 2: Occupies column 3, spans rows 1-2
- Item 6: Occupies columns 2-3 in row 3

**Items that auto-place:**

- Item 3: Column 1, row 2 (next available space)
- Item 4: Column 1, row 3
- Item 5: Column 2, row 2

---

## Key Concepts Learned

### **1. Grid Template Columns**

```css
grid-template-columns: repeat(3, 1fr);
```

- Creates 3 columns
- Each column is `1fr` (equal width)
- Alternative: `200px 300px 200px` (fixed widths)

### **2. Grid Template Rows**

```css
grid-template-rows: 100px 200px 100px;
```

- Creates 3 rows
- Fixed heights: 100px, 200px, 100px
- Alternative: `auto` (height based on content)

### **3. Gap Property**

```css
gap: 4px;
```

- Shorthand for `row-gap` and `column-gap`
- Creates spacing between cells
- Replaces old `grid-gap` property

### **4. Grid Column (Item Positioning)**

```css
grid-column: 1/3; /* Start line / End line */
grid-column: span 2; /* Alternative: span 2 columns */
```

### **5. Grid Row (Item Positioning)**

```css
grid-row: 1/3; /* Start line / End line */
grid-row: span 2; /* Alternative: span 2 rows */
```

---

## Experiment Ideas

Try modifying the code to learn more:

### **1. Change Column Configuration**

```css
/* 4 equal columns */
grid-template-columns: repeat(4, 1fr);

/* Mixed sizes */
grid-template-columns: 200px 1fr 2fr;

/* Auto columns */
grid-template-columns: auto auto auto;
```

### **2. Change Row Heights**

```css
/* All rows 150px */
grid-template-rows: repeat(3, 150px);

/* Auto height based on content */
grid-template-rows: auto auto auto;
```

### **3. Change Gap Spacing**

```css
gap: 20px; /* Larger gap */
gap: 10px 20px; /* Different row/column gaps */
row-gap: 10px; /* Only vertical spacing */
column-gap: 20px; /* Only horizontal spacing */
```

### **4. Make Different Items Span**

```css
.item3 {
  grid-column: span 2; /* Item 3 spans 2 columns */
}

.item4 {
  grid-row: span 2; /* Item 4 spans 2 rows */
}
```

---

## Common Issues & Solutions

### **Issue 1: Items Not Positioning Correctly**

**Problem:** Grid lines are confusing

**Solution:** Remember grid lines start at 1, not 0

```css
/* Wrong - no line 0 */
grid-column: 0/2;

/* Correct */
grid-column: 1/3;
```

### **Issue 2: Items Overlapping**

**Problem:** Multiple items assigned to same grid area

**Solution:** Grid allows overlapping! Use `z-index` to control stacking:

```css
.item1 {
  grid-column: 1/3;
  grid-row: 1/2;
  z-index: 1; /* Brings item to front */
}
```

### **Issue 3: Gap Not Showing**

**Problem:** Forgot to set `display: grid`

**Solution:**

```css
.grid-container {
  display: grid; /* Required! */
  gap: 4px;
}
```

---

## Grid Properties Reference

### **Container Properties:**

| Property                | What It Does             | Example                  |
| ----------------------- | ------------------------ | ------------------------ |
| `display: grid`         | Activates grid layout    | Required for grid        |
| `grid-template-columns` | Defines column structure | `repeat(3, 1fr)`         |
| `grid-template-rows`    | Defines row structure    | `100px 200px 100px`      |
| `gap`                   | Spacing between cells    | `10px` or `10px 20px`    |
| `grid-auto-flow`        | Controls auto-placement  | `row`, `column`, `dense` |

### **Item Properties:**

| Property       | What It Does             | Example                  |
| -------------- | ------------------------ | ------------------------ |
| `grid-column`  | Column position/span     | `1/3` or `span 2`        |
| `grid-row`     | Row position/span        | `1/2` or `span 2`        |
| `grid-area`    | Shorthand for row/column | `1 / 1 / 2 / 3`          |
| `justify-self` | Horizontal alignment     | `start`, `center`, `end` |
| `align-self`   | Vertical alignment       | `start`, `center`, `end` |

---

## When to Use CSS Grid

**Best For:**

- Two-dimensional layouts (rows AND columns)
- Page layouts (header, sidebar, main, footer)
- Card grids with varying sizes
- Complex, structured layouts
- Magazine-style layouts

**Not Ideal For:**

- Simple one-dimensional layouts → Use Flexbox
- Content that should flow naturally → Use Flexbox
- Browser compatibility with IE10 and below

---

## Next will learn:

1. **Grid Template Areas** - Named grid regions
2. **Auto-Placement** - `grid-auto-flow`, `grid-auto-rows`
3. **Fractional Units** - Advanced use of `fr`
4. **Minmax Function** - Responsive sizing
5. **Grid + Flexbox** - Combining both layouts
6. **Responsive Grids** - Media queries with grid

---

## Additional Resources

- [MDN: CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
- [CSS Tricks: Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Grid Garden](https://cssgridgarden.com/) - Interactive grid learning game
- [Grid by Example](https://gridbyexample.com/) - Real-world examples

## Learning Tip

**Don't try to memorize all grid properties** Instead:

1. Understand the grid line numbering system
2. Remember `display: grid` activates grid
3. Know `grid-template-columns/rows` defines structure
4. Use `grid-column` and `grid-row` for positioning
5. Practice with real layouts

Grid becomes easy with practice.

---

## Topic - 02: Grid Masterclass

- Code Files

  - **[Grid Masterclass](./Topic-02_Grid-Masterclass/grid-masterclass.html)**

---

**Built with the Tortoise approach 🐢 - Understanding fundamentals before complexity**
