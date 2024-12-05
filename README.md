# Technical Writing Assignment

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

## Prompt 1

What are the main differences between Flexbox and Grid layouts? Describe scenarios where each layout system would be more suitable.

### Response 1

## Prompt 2

What is the difference between `justify-content` and `align-items` in Flexbox? How does each property control the positioning of flex items within the container?

### Response 2

## Prompt 3

Describe the difference between `grid-template-areas` and `grid-template-columns`/`grid-template-rows`. When might you prefer one approach over the other?

### Response 3

Let’s talk about the difference between `grid-template-areas`
and `grid-template-columns`/`grid-template-rows` in CSS Grid.

Imagine we are designing a house: would you prefer labeled rooms,
or would you rather work with exact measurements? Both methods
can create great layouts. But let's break it down with code examples!

#### Approach 1: `grid-template-areas` (The Blueprint)

This is like sketching a floor plan and labeling the rooms. The example below shows the CSS grid with `grid-template-areas`.

<!-- Example: CSS Grid with grid-template-areas -->
<div class="grid-container">
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="main">Main Content</div>
  <div class="footer">Footer</div>
</div>

<style>
  .grid-container {
    display: grid;

    grid-template-areas:
      "header header header" 
      "sidebar main main"
      "footer footer footer"; 

    grid-template-rows: 50px 1fr 30px;
    grid-template-columns: 150px 1fr 1fr;

    gap: 10px;
  }

  .header {
    grid-area: header; 
    background-color: #4CAF50;
    text-align: center;
    padding: 10px;
    color: white;
  }

  .sidebar {
    grid-area: sidebar; /* Place in the sidebar area */
    background-color: #2196F3;
    text-align: center;
    padding: 10px;
    color: white;
  }

  .main {
    grid-area: main; 
    background-color: #f1f1f1;
    text-align: center;
    padding: 10px;
  }

  .footer {
    grid-area: footer; /* Place in the footer area */
    background-color: #555;
    text-align: center;
    padding: 10px;
    color: white;
  }
</style>
</p>

```js
<!-- ^Code Explanation: CSS Grid with grid-template-areas -->
<div class="grid-container">
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="main">Main Content</div>
  <div class="footer">Footer</div>
</div>

<style>
  /* We define the grid container */
  .grid-container {
    display: grid;

    /* Layout the grid with named areas */
    grid-template-areas:
      "header header header" /* Header spans all columns */
      "sidebar main main" /* Sidebar and main content */
      "footer footer footer"; /* Footer spans all columns */

    /* Set row heights and column widths */
    grid-template-rows: 50px 1fr 30px;
    grid-template-columns: 150px 1fr 1fr;

    /* Add some spacing between grid items */
    gap: 10px;
  }

  /* Style the individual areas */
  .header {
    grid-area: header; /* Place in the header area */
    background-color: #4CAF50;
    text-align: center;
    padding: 10px;
    color: white;
  }

  .sidebar {
    grid-area: sidebar; /* Place in the sidebar area */
    background-color: #2196F3;
    text-align: center;
    padding: 10px;
    color: white;
  }

  .main {
    grid-area: main; /* Place in the main content area */
    background-color: #f1f1f1;
    text-align: center;
    padding: 10px;
  }

  .footer {
    grid-area: footer; /* Place in the footer area */
    background-color: #555;
    text-align: center;
    padding: 10px;
    color: white;
  }
</style>
```

Why should we use `grid-template-areas`?

- Easy to read: We can visualize our layout right in the CSS.
- Great for structured layouts, like dashboards or web pages.

#### Approach 2: `grid-template-columns` and `grid-template-rows` (The Precision Approach)

This method is like measuring each room to the last inch. Example below shows the CSS grid with `grid-template-columns` and `grid-template-rows`.

<!-- Example: CSS Grid with grid-template-columns and grid-template-rows -->
<div class="grid-container-columns-rows">
  <div class="item1">Item 1</div>
  <div class="item2">Item 2</div>
</div>

<style>
  .grid-container-columns-rows {
    display: grid;

    grid-template-rows: 50px 1fr 30px;

    grid-template-columns: 150px 1fr 1fr;

    gap: 10px;
  }

  .item1 {
    grid-row: 1; 
    grid-column: 1 / span 3; 
    background-color: #4CAF50;
    text-align: center;
    padding: 10px;
    color: white;
  }

  .item2 {
    grid-row: 2; 
    grid-column: 1; 
    background-color: #2196F3;
    text-align: center;
    padding: 10px;
    color: white;
  }
</style>

```js
<!-- ^Code Explanation: CSS Grid with grid-template-columns and grid-template-rows -->
<div class="grid-container-columns-rows">
  <div class="item1">Item 1</div>
  <div class="item2">Item 2</div>
</div>

<style>
  /* Define the grid container */
  .grid-container-columns-rows {
    display: grid;

    /* Define the height of each row */
    grid-template-rows: 50px 1fr 30px;

    /* Define the width of each column */
    grid-template-columns: 150px 1fr 1fr;

    /* Add some spacing between items */
    gap: 10px;
  }

  /* Style the first item */
  .item1 {
    grid-row: 1; /* Place in the first row */
    grid-column: 1 / span 3; /* Span across all columns in the first row */
    background-color: #4CAF50;
    text-align: center;
    padding: 10px;
    color: white;
  }

  /* Style the second item */
  .item2 {
    grid-row: 2; /* Place in the second row */
    grid-column: 1; /* Place in the first column */
    background-color: #2196F3;
    text-align: center;
    padding: 10px;
    color: white;
  }
</style>
```

Why use `grid-template-columns`/`rows`?

- Offers pixel-perfect control over sizing and placement.
- Ideal for dynamic layouts or when naming sections isn’t needed.

When to choose each approach:

- We use `grid-template-areas` when we want a clear, labeled layout. It’s like drawing a map of your grid.
- We use `grid-template-columns`/`rows` for precise and flexible layouts. It’s like customizing every detail of your design.

Both approaches is great. Pick the one that suits your project!

## Prompt 4

Explain the `min-width` and `max-width` keywords in media queries. How do they help create responsive breakpoints for different screen sizes?

### Response 4

#### Understanding `min-width` and `max-width` in Media Queries

When you're building a website, you want it to look good on all screen sizes—whether it's a phone, tablet, or desktop. To do this, we use media queries in CSS, and min-width and max-width help us control how the design changes at different screen sizes.

#### What are `min-width` and `max-width`?

`min-width`: This tells the browser to apply certain styles when the screen is at least a certain width.

- Is used to change the layout when the screen is wide enough (like on tablets or desktops).

- For example, if you want the layout to change when the screen is wider than 600px (like on a tablet), you use min-width: 600px.

`max-width`: This applies styles when the screen is smaller than a certain width.

- Is used to change the layout when the screen is too small (like on phones).

- For example, if you want a different design on smaller screens (like phones), you use max-width: 600px.

#### Why Do We Use Them?

We use `min-width` and `max-width` to set breakpoints.

- A breakpoint is a specific width where you want the design to change. This makes your website responsive, meaning it looks good on any screen size.

## Prompt 5

Imagine you are teaching a brief lesson on **mobile first design**. Your lesson should include the following information:

- An explanation of mobile first design and a few of the benefits of this approach
- A CSS code example demonstrating how to use media queries to adjust the layout of a container from mobile to desktop with either Flexbox or Grid (choose one).
- An explanation of the code example.

### Response 5
