# Day 12 - Learn about CSS

- Box model, inline and block elements

- Navbar project with Pseudo element

## Box Model:

The Box Model is a fundamental concept that defines how every HTML element is visually structured and takes up space on a webpage.

Every element is treated as a rectangular box composed of four distinct areas that control its size, position, and spacing.

![Box Model](./assets/boxModel.png)

**Four Key Areas:**

1. **Content:**

   - The actual text, image, video, or data inside the box
   - Controlled by `width` and `height` properties

2. **Padding:**

   - Invisible space between content and border (internal spacing)
   - Creates breathing room inside the element
   - Properties: `padding-top`, `padding-right`, `padding-bottom`, `padding-left`

3. **Border:**

   - A visible line around the padding and content (still inside the element)
   - Properties: `border-width`, `border-style`, `border-color`

4. **Margin:**
   - Space outside the border (external spacing between elements)
   - Creates distance from other elements
   - Properties: `margin-top`, `margin-right`, `margin-bottom`, `margin-left`

**Fill Area:**

The area filled with `background color` or `background image` (includes content + padding, but **not** margin).

**Box Sizing Property:**

CSS provides two ways to calculate box dimensions:

**1. Content-box (default):**

```css
box-sizing: content-box;
```

- Width/height applies **only to content**

- Padding and border are **added** to the specified dimensions

- Makes final size larger than specified width/height

**2. Border-box ✅ (recommended):**

```css
box-sizing: border-box;
```

- Width/height includes **content + padding + border**

- No extra expansion beyond specified dimensions

- What you set is what you get

- **Best practice:** Apply to all elements with `* { box-sizing: border-box; }`

**How Box Model calculate size:**

Given these CSS properties:

```css
.box {
  width: 200px;
  padding: 20px;
  border: 5px solid black;
  height: 100px;
}
```

**With content-box (default):**

**Final element width:**

```
Left Border + Left Padding + Content Width + Right Padding + Right Border
5px + 20px + 200px + 20px + 5px = 250px
```

**Final element height:**

```
Top Border + Top Padding + Content Height + Bottom Padding + Bottom Border
5px + 20px + 100px + 20px + 5px = 150px
```

**With border-box:**

```css
* {
  box-sizing: border-box;
}
```

- **Final width:** Exactly 200px (as specified)
- **Final height:** Exactly 100px (as specified)
- Padding and border are included within these dimensions

**Code Example:**

```html
<div class="box">This is a box</div>
```

```css
* {
  /* Apply border-box to all elements (best practice) */
  box-sizing: border-box;
}

.box {
  width: 200px;
  height: 100px;
  padding: 20px;
  border: 5px solid black;
  margin: 15px;
  background-color: lightgray;
}
```

```
With border-box:

- Total width: 200px (including padding + border)
- Total height: 100px (including padding + border)
- Content area adjusts automatically

```

## Inline and Block elements

CSS provides different display types that control how elements behave in the document flow.

**Block-Level Elements:**

Elements that take up the full width available and stack vertically.

**Characteristics:**

- Elements formatted visually as blocks
- Occupy 100% of parent element's width (by default)
- Stack vertically, one after another
- Full box model applies (width, height, padding, margin all work)
- Force new lines before and after

**Default Block Elements:**

```
Structural: body, main, header, footer, section, nav, aside, article
Containers: div, form, fieldset
Headings: h1, h2, h3, h4, h5, h6
Text blocks: p, blockquote, pre, hr
Lists: ul, ol, li, dl, dt, dd
Tables: table, thead, tbody, tr

```

**With CSS:**

```css
display: block;
```

**Inline Elements:**

Elements that only take up as much width as necessary and flow with text.

**Characteristics:**

- Occupy only the space necessary for content
- Do NOT cause line-breaks (flow with text)
- Box model applies differently:
  - Width and height do **not** apply
  - Padding and margins only work horizontally (left/right)
  - Vertical padding is applied but doesn't affect layout
  - Vertical margins are ignored

**Default Inline Elements:**

```
Links:          a
Text styling:   strong, em, span, code, small, sub, sup, mark
Form elements:  label
```

**With CSS:**

```css
display: inline;
```

**Inline-Block Elements:**

The best of both worlds - flows like inline but behaves like block.

**Characteristics:**

- Looks like inline from the outside (sits in line with text)
- Behaves like block on the inside (accepts width/height)
- Occupies only content's space (can set custom width/height)
- Causes NO line-breaks
- Full box model applies (all padding and margins work)

**Default Inline-Block Elements:**

```
Media:         img (inline by default, but behaves like inline-block)
Form elements: button, input, select, textarea
```

**With CSS:**

```css
display: inline-block;
```

**Comparison:**

| Property              | Block                                 | Inline-Block                                                               | Inline                                           |
| --------------------- | ------------------------------------- | -------------------------------------------------------------------------- | ------------------------------------------------ |
| **Element Formation** | Elements formatted visually as blocks | Looks like inline from the outside, behaves like block level on the inside | Occupies only content's space                    |
| **Width & Height**    | Works (default: 100%)                 | Works (shrinks to content)                                                 | Doesn't work                                     |
| **Padding**           | All sides                             | All sides                                                                  | Left/right only (vertical doesn't affect layout) |
| **Margin**            | All sides                             | All sides                                                                  | Left/right only (vertical ignored)               |
| **Line Breaks**       | Creates new lines                     | No line breaks                                                             | No line breaks                                   |
| **Stacking**          | Vertical (one per line)               | Horizontal (if space allows)                                               | Horizontal (flows with text)                     |
| **Use Case**          | Layout sections, containers           | Navigation items, buttons, cards                                           | Text styling, links within paragraphs            |

**Visual Summary:**

```

BLOCK: [████████████████████████] ← Full width
[████████████████████████]

INLINE-BLOCK: [█████] [████████] [██] ← Content width, no breaks

INLINE: text [█] more text [███] ← Flows with text

```

**Key Differences:**

**Block-Level Boxes**

- Elements formatted visually as blocks
- Take 100% of parent width
- Stack vertically, one after another
- Full box model applies
- `display: block`

**Inline-Block Boxes**

- Looks like inline from the outside
- Behaves like block on the inside
- Occupies only content's space
- Causes no line-breaks
- Full box model applies
- `display: inline-block`

**Inline Boxes**

- Occupies only content's space
- Causes no line-breaks
- Box model is different:
  - Height and width do **not** apply
  - Padding and margins only horizontal (left & right)
- `display: inline`

**Practical Example:**

```html
<div class="container">
  <!-- Block: takes full width -->
  <h2>Welcome to CSS</h2>
  <!-- Block: full width, new line -->

  <p>
    <!-- Block: paragraph -->
    This is <strong>bold text</strong>
    <!-- Inline: flows with text -->
    and here's a <a href="#">link</a>.
    <!-- Inline: flows with text -->
  </p>

  <nav>
    <!-- Block: navigation container -->
    <a href="#" class="nav-item">Home</a>
    <!-- Inline-block: sits in row -->
    <a href="#" class="nav-item">About</a>
    <a href="#" class="nav-item">Contact</a>
  </nav>

  <button>Click Me</button>
  <!-- Inline-block by default -->
</div>
```

```css
.container {
  display: block;
  max-width: 1200px;
  margin: 0 auto;
}

.nav-item {
  display: inline-block; /* Converts link to inline-block */
  padding: 10px 20px; /* Now all padding works */
  margin: 0 5px; /* Now all margin works */
  width: 100px; /* Width now applies */
}
```

**Common Use Cases:**

**When to use Block:**

- Page layout sections (header, footer, sidebar)
- Container elements (`<div>`)
- Text blocks and headings
- Elements that should stack vertically
- Forms and form sections

**When to use Inline:**

- Text styling within paragraphs (`<strong>`, `<em>`)
- Links within text
- Small icons or badges
- Elements that should flow naturally with content

**When to use Inline-Block:**

- Navigation menu items (horizontal nav)
- Buttons in a row
- Image galleries
- Cards that should sit side-by-side
- Form elements that need precise sizing
- Icons with specific dimensions

**Common Pitfalls & Solutions:**

**Pitfall 1: Setting width/height on inline elements**

```css
/* This won't work! */
span {
  width: 200px; /* Ignored */
  height: 100px; /* Ignored */
}
```

**Solution:** Convert to inline-block or block

```css
span {
  display: inline-block;
  width: 200px; /* Now it works! */
  height: 100px;
}
```

**Pitfall 2: Vertical spacing on inline elements**

```css
/* Only left/right work, top/bottom ignored */
a {
  margin: 20px 0; /* Top/bottom margins don't work */
}
```

**Solution:** Use inline-block or padding

```css
a {
  display: inline-block;
  margin: 20px 0; /* Now all margins work */
}

/* OR use padding (works on inline) */
a {
  padding: 20px 0; /* Padding is applied but doesn't affect line height */
}
```

**Pitfall 3: Gaps between inline-block elements**

```html
<div class="nav">
  <a href="#">Home</a>
  <a href="#">About</a>
  <a href="#">Contact</a>
</div>
```

```css
a {
  display: inline-block;
  /* Unexpected 4px gaps appear between elements! */
}
```

**Solution:** Remove whitespace in HTML or use flexbox

```html
<!-- Option 1: Remove whitespace -->
<div class="nav">
  <a href="#">Home</a><a href="#">About</a><a href="#">Contact</a>
</div>

<!-- Option 2: Use flexbox (modern approach) -->
<div class="nav">
  <a href="#">Home</a>
  <a href="#">About</a>
  <a href="#">Contact</a>
</div>
```

```css
.nav {
  display: flex;
  gap: 10px; /* Better than inline-block for layouts */
}
```

**Key Takeaways:**

1. **Always use `box-sizing: border-box`** for predictable sizing
2. **Block elements** stack vertically and take full width
3. **Inline elements** flow with text but have limited box model support
4. **Inline-block** combines benefits of both
5. Use **Flexbox or Grid** for modern layouts instead of inline-block
6. Understand which properties work with each display type
7. Choose the right display type based on your layout needs

**[View Code Examples](./code-examples/)**

**Created with the Tortoise approach 🐢 - Slow, steady, and thorough!**
