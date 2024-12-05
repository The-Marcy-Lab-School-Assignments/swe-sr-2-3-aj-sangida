# Technical Writing Assignment

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

## Prompt 1

What are the main differences between Flexbox and Grid layouts? Describe scenarios where each layout system would be more suitable.

### Response 1

-->The main difference between **Flexbox** and **Grid** layouts is that **Flexbox** was designed for layouts in either a row or a column, which is _one-dimensional_. **Grid** was designed for layouts in rows, and columns at the same time, which is _two-dimensional_. **Flexbox** works best when you’re arranging elements in one direction. Think of it as you organizing your shoes into a straight line. When you want to distribute space between items evenly or align-items individually like a navigation bar, a list of cards, or a row of images, **Flexbox** keeps it simple.

-->On the other hand, **Grid** is like arranging pieces on a chess board. It allows you to arrange your content in both rows and columns, making it ideal for more complex layouts rather than a simple line-up. You would use **Grid** when you need to lay out content in both rows and columns like creating a grid of images or designing a full-page layout.

## Prompt 2

What is the difference between `justify-content` and `align-items` in Flexbox? How does each property control the positioning of flex items within the container?

### Response 2

-->The difference between `justify-content` and `align-items` in Flexbox is that `justify-content` arranges items on the **main-axis** and `align-items` arranges items on the **cross-axis**. The **main-axis** is determined by the direction of the flex container, which can be either a row or a column. Imagine you had a box of chocolates, you would use `justify-content` to control how the chocolates are laid out _horizontally_ and `align-items` to control how they are laid out _vertically_. The `align-items` property arranges flex items on the cross-axis. The **cross-axis** runs down the columns _(horizontally)_ if flex-direction is a row and along the rows _(vertically)_ if flex-direction is a column.

## Prompt 3

Describe the difference between `grid-template-areas` and `grid-template-columns`/`grid-template-rows`. When might you prefer one approach over the other?

### Response 3

Let’s talk about the difference between `grid-template-areas`
and `grid-template-columns`/`grid-template-rows` in CSS Grid.

Imagine we are designing a house: would you prefer labeled rooms,
or would you rather work with exact measurements? Both methods
can create great layouts. But let's break it down with code examples!

#### Approach 1: `grid-template-areas` (The Blueprint)

This is like sketching a floor plan and labeling the rooms. The image below shows the CSS grid with `grid-template-areas`.

![Grid-areas-template](/template1.png)

```js
<!-- ^Code for Template Image1: CSS Grid with grid-template-areas -->
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

This method is like measuring each room to the last inch. Image below shows the CSS grid with `grid-template-columns` and `grid-template-rows`.

![Grid-column-row-template](/template2.png)

```js
<!-- ^Code for Template Image2: CSS Grid with grid-template-columns and grid-template-rows -->
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
- An explanation of mobile first design and a few of the benefits of this approach
- A CSS code example demonstrating how to use media queries to adjust the layout of a container from mobile to desktop with either Flexbox or Grid (choose one).
- An explanation of the code example.

### Response 5

--> At first, web designers would build a website that’s optimized for desktop, then take those design elements and shrink them down for mobile. This process is called _graceful degradation_, start big and downsize as needed. However, this made the user experience poor and impacted user engagement because of confusion about why certain features weren't available for the mobile design and the possible bugs that it could create.

-->The **mobile-first design** is called _progressive enhancement_. It is a web-development and design approach that focuses on design and development for mobile screen sizes, over design and development for desktop screen sizes. You start with the small screen and progressively add content to fit the appropriate screen size. This approach makes sure that the website is optimized for the device it's used on.

-->Below is an example of how you would apply the **mobile-first design**. Using it to adjust the layout between mobile and desktop sizes.

```css
/* Base styles for mobile (default) */
body {
  background-color: #ffc636;
  font-size: 14px;
  margin: 0;
  padding: 0;
}

.container {
  display: flex;
  flex-direction: column;
  gap: 1rem; /*Space between*/
}

/* Media query for large tablets and laptop screens */
@media screen and (min-width: 960px) {
  body {
    font-size: 18px;
  }

  .container {
    flex-direction: row; /*Arrange items horizontally on larger screens*/
    justify-content: space-between;
  }
}
```

**Base-styles** = a set of CSS rules that are applied to a website to prioritize a mobile-first design

- `font-size` is set to `14px` for easy readability on a phone screen
- `.container` class has a `flex-direction: column` stacks items vertically

**Media Query** = allows you to apply CSS styles depending on a device's media type (such as print vs. screen) or other features or characteristics.

- `flex-direction: row` arranges items horizontally on larger screens
