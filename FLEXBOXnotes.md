# FLEXBOX NOTES
This is a compilation of my notes about the basics of Flexbox.<br>
* Flexbox is very useful to position items around a page
* Remember to put items in `<div>`s / `<div class="container">`
* In CSS, remember to always set the property to 'display: flex;'
* `float`, `clear`, `vertical-align` have no effect on a flex-item

------

There are primarily 2 directions in Flexbox: L/R (horizontal rows) and top/bottom (vertical columns). These directions relate to the axes (which can switch depending on the flex-direction)

<br>

### COMPONENTS OF THE FLEX CONTAINER (Parent)
<u>Flex Container</u> enables the flex context for all direct children

`.container { 
    display: flex; 
}`

<u>Flex Direction</u> establishes the main-axis (and thus defines the direction flex items are placed in a container)

`.container { 
    flex-direction: row | row-reverse | column | column-reverse 
}`

#### Flex-direction & Axes

|                |   Main Axis   |  Cross-Axis   |
|----------------|:-------------:|:-------------:|
| Row            |    L to R     | Top to Bottom |
| Row-reverse    |    R to L     | Top to Bottom |
| Column         | Top to Bottom |    L to R     |
| Column-reverse | Bottom to Top |    L to R     |

<br>

><img src="https://css-tricks.com/wp-content/uploads/2018/10/flex-direction.svg">

#### ROW (DEFAULT)

<img src="https://css-tricks.com/wp-content/uploads/2018/11/00-basic-terminology.svg">

<u>Flex-wrap</u> will allow items to wrap as needed (nowrap by default; wrap-reverse will wrap onto multiple lines from bottom to top)

`.container { 
    flex-wrap: nowrap | wrap | wrap-reverse
}`

<u>Flex-flow</u> is a shorthand for both flex-direction and flex-wrap properties

`.container { 
    flex-flow: row nowrap | column wrap | ...
}`

 <br> 

### ALIGNMENT

#### JUSTIFY-CONTENT defines the alignment along the <em> main-axis</em>. ('safe' ensures that an element cannot be 'pushed' off-screen and become inaccessible to the user)

`.container { 
    justify-content: flex-start | flex-end | center | space-between | space-evenly | start | end | left | right | ... + safe | unsafe 
}`

<img src="https://css-tricks.com/wp-content/uploads/2018/10/justify-content.svg">

<hr>

#### ALIGN-CONTENT aligns a flex-container's lines w/in cross-axis when there is extra space

`.container { 
    align-content: flex-start | flex-end | center | space-between | space-around | space-evenly | stretch | baseline | first baseline | last baseline | ... + safe | unsafe 
}`

<img src="https://css-tricks.com/wp-content/uploads/2018/10/align-content.svg">

<hr>

#### ALIGN-ITEMS defines the default layout/ behavior for items on the <em>cross-axis</em>

`.container { 
    align-items: flex-start | flex-end | center | stretch | baseline | first baseline | last baseline | start | end | ... + safe | unsafe 
}`

<img src="https://css-tricks.com/wp-content/uploads/2018/10/align-items.svg">

<hr>

#### ALIGN-SELF allows the default alignment (or the alignment specified to `align-items` to be overriden for individual flex items)

`.container { 
    align-self: flex-start | flex-end | center | stretch | baseline | auto 
}`

<img src="https://css-tricks.com/wp-content/uploads/2018/10/align-self.svg">

<hr>
<br>

### COMPONENTS OF THE FLEX ITEMS (Children)

#### ORDER controls the order in which items appear in the flex container (default 0)

`.item {
    order: 5;
}`

<img src="https://css-tricks.com/wp-content/uploads/2018/10/order.svg">

<hr>

#### FLEX-GROW defines the ability for flex-items to grow if necessary (default 0)
If all items are set to 1 they will take up remaining space equally. If one item is set to 2 it will (try to) take up 2x as much space as the others. Negative values aren't valid.

`.item {
    flex-grow: 2;
}`

<hr>

#### FLEX-SHRINK defines the ability for a flex-item to shrink if necessary.
If all items are set to 1, they will shrink equally. If an item is set to 2 it will shrink 2x as much as the others. Negative values aren't valid.

`.item {
    flex-shrink: 4;
}`

<hr>

#### FLEX-BASIS defines the default size of an element before the remaining space is distributed. 
This value van be a length (20% or 5rem) or a keyword. `auto` would be based on the width/height property (extra space distributed would be based on it's flex-grow). `content` would be based on the size of the item's content. If set to 0, extra space around content isn't factored in.

`.item {
    flex-basis: auto;
}`

<hr>

#### FLEX is shorthand for `flex-grow`, `flex-shrink`, and `flex-basis` combined. 
The `flex-shrink` and `flex-basis` are optional. This format is recommended instead of setting the individual properties

`.item {
    flex: none | 0 1 auto | ;
}`