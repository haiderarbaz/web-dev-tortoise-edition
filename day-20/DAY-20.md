# Day 20 - Hands-On CSS Challenges

A collection of 2 beginner-friendly CSS challenges focusing on Box-Shadow to and element and position in CSS.

- Challenge - 07: Add a Box Shadow to an Element

- Challenge - 08: Positions In CSS

---

## Project Structure

```
day-20/
├── Challenge-07/
|    └── challenge-07.html
|
├── Challenge-08/
│   └── challenge-08.html
|
├── navigation.html          # Navigation Page
|
└── DAY-20.md           # Completed Documentation (This File)

```

---

## Table of Contents

- [Challenge - 07: Add a Box Shadow to an Element](#challenge---07-add-a-box-shadow-to-an-element)
- [Challenge - 08: Positions In CSS](#challenge---08-positions-in-css)

---

## Challenge - 07: Add a Box Shadow to an Element

**Task:**

- Create a div element and apply a shadow effect using the `box-shadow` property.

**Instructions:**

- Create a `div` element with the class name `shadow-box`.

- Apply the following styles to the div:

  - Set a `width` and `height` of `200px`.

  - Use the `box-shadow` property to add a shadow effect to the box.

  - The shadow should have the following properties:

  - Horizontal offset of 10px.

  - Vertical offset of 10px.

  - Blur radius of 15px.

  - Shadow color should be gray.

[Code File](./challenge-07/challenge-07.html)

---

## Challenge - 08: Positions In CSS

**Task:**

- Create a layout where three elements are positioned using `static`, `relative`, and `absolute` positioning. Each element should be clearly distinguishable with different background colors.

**Instructions:**

- Create a container `div` with the class name `parent-container`.

- Inside the container, create three `div` elements:

  - The first element should have the class name `static-box` and be positioned normally in the document flow without any top/bottom/left/right.

  - The second element should have the class name `relative-box` and be positioned 50px to the right and 50px down from its normal position.

  - The third element should have the class name `absolute-box` and be positioned 30px from the top and 30px from the left of the container.

- Apply background colors to each element to make their positions clear.

[Code File](./challenge-08/challenge-08.html)

## Concepts Practice

- **Box-Shadow:** Learned how to create depth and elevation effects using the `box-shadow` property with horizontal offset, vertical offset, blur radius, and color values.

- **Position:** Practiced CSS positioning with `static` (default flow), `relative` (offset from normal position), and `absolute` (positioned relative to nearest positioned ancestor).
