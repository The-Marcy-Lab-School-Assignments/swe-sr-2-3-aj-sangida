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

## Prompt 4

Explain the `min-width` and `max-width` keywords in media queries. How do they help create responsive breakpoints for different screen sizes?

### Response 4

## Prompt 5

Imagine you are teaching a brief lesson on **mobile first design**. Your lesson should include the following information:

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
