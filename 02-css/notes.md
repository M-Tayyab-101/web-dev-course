# 02 - CSS Notes

## What is CSS?
CSS controls how your HTML looks — colors, sizes, spacing, layout.
HTML = structure, CSS = appearance. They are separate files linked together.

## How to link CSS to HTML
Put this in your <head> tag:
<link rel="stylesheet" href="style.css">
Without this line, CSS does nothing.

## CSS Rule Structure
selector {
  property: value;
}
Example:
h1 {
  color: blue;
  font-size: 40px;
}

## Selectors
Tag selector  → targets every element of that type
  h1 { }      → styles ALL h1s on the page

Class selector → targets specific elements you name
  .main-title { }  → in HTML: <h1 class="main-title">
  Use for things that repeat (multiple buttons, cards etc)

ID selector → targets ONE unique element only
  #intro { }   → in HTML: <p id="intro">
  Use for things that appear only once on the page

Rule: specific beats general
  ID beats Class beats Tag
  If two rules conflict, the more specific one wins.

## Text Properties
color: red;
font-size: 18px;
font-weight: bold;        /* or 100-900 */
font-style: italic;
text-align: center;       /* left, center, right */
text-decoration: underline;
line-height: 1.5;
letter-spacing: 2px;

## Box Properties
padding: 10px;            /* space INSIDE the element */
margin: 10px;             /* space OUTSIDE the element */
border: 1px solid black;
border-radius: 10px;      /* rounded corners */
width: 200px;
height: 100px;
box-shadow: 2px 2px 5px gray;

## Padding shorthand
padding: 10px;                    /* all 4 sides */
padding: 10px 20px;               /* top/bottom=10px, left/right=20px */
padding: 10px 20px 5px 15px;      /* top right bottom left */
Same rules apply to margin.

## Background
background-color: blue;
background-image: url('image.jpg');

## Display
display: block;     /* full width, starts new line (default for h1, p, div) */
display: inline;    /* sits in line with text (default for a, span) */
display: none;      /* hides element completely */

## Other useful properties
opacity: 0.5;         /* 0=invisible, 1=fully visible */
cursor: pointer;      /* hand cursor, always use on buttons */

## My mistakes to remember
- <!DOCTYPE html> needs the ! — always include it
- <head> is only for title, links, settings — never put visible content there
- All visible content goes inside <body>
- When linking CSS: href="style.css" must match the actual filename exactly

## Flexbox

### What is Flexbox?
Flexbox is a layout tool. By default every div stacks vertically
(one below the other). Flexbox makes them go side by side horizontally.

### The golden rule
display: flex always goes on the PARENT element.
The children automatically arrange themselves.

### Main properties on the parent
display: flex;                  → activates flexbox
flex-direction: row;            → side by side (default)
flex-direction: column;         → back to top to bottom
justify-content: flex-start;    → horizontal: push to left
justify-content: center;        → horizontal: push to center
justify-content: flex-end;      → horizontal: push to right
justify-content: space-between; → horizontal: equal space between items
justify-content: space-around;  → horizontal: equal space around items
align-items: flex-start;        → vertical: push to top
align-items: center;            → vertical: push to middle
align-items: flex-end;          → vertical: push to bottom

### Easy way to remember
justify-content → horizontal (left and right)
align-items     → vertical (up and down)

### Centering something perfectly
.parent {
  display: flex;
  justify-content: center;
  align-items: center;
}
This centers the child both horizontally and vertically.

### margin: auto trick
margin: 0 auto on a child pushes it to the center
while other elements stay in their position.
Useful for centering a group of links in a navbar.

### Flex used twice pattern
Any element can be a flex parent to its own children
while also being a flex child of its parent.
Example: a box that is positioned by parent flex,
but also uses flex itself to center text inside it.

### Descendant selector
.links a { }
This targets the a tag inside .links only.
Not all a tags on the page — only ones inside .links.
Very commonly used pattern.

### Flexbox cheatsheet (bookmark this)
https://flexbox.malven.co

## My mistakes to remember
- display: flex goes on the PARENT not the children
- color on a parent div does not affect <a> tags inside it
  you need to target .parent a { color: white; }
- align-items on the links container is needed for
  vertical centering of the links themselves

## Files I made
- practice1.html + style1.css  → first CSS practice (tag selectors)
- practice2.html + style2.css  → classes and IDs lesson
- challenge2.html + challenge2.css → challenge (classes/IDs only)
- challenge3.html + challenge3.css → flexbox navbar challenge