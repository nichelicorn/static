# Static Comp

This static site re-creates a comp layout. The site contains two pages - a dashboard displaying a card layout, and a profile, the details of an selected card.

## Notes
### MDN lesson : The box model
* HTML elements (boxes) can have either a **block** or **inline** display type
* boxes with an outer display type of `block` will:
    * create a new line for the box
    * extend the inline direction to fill available space in the container; this usually means the box will be as wide as the container and fill 100% of available space
    * respect the `width` and `height` properties
    * padding, margin, and border will cause other elements to be pushed *away* from the box (this is what's causing the strange behavior of the boxes separating further away as padding is added to the cards)
* boxes with an outer display type of `inline` will:
    * not create a new line for the box
    * not apply `width` and `height` properties
    * vertical padding, margins, and border will apply but will *not* cause other inline boxes to move away from the box
    * horizontal padding, margins, and borders will apply and will cause other inline boxes to move *away* from the box
* Inner display type dictates how elements inside the box are laid out; by default, internal elements have a *normal flow* which means they will behave just like a block or inline element
    * using `display` properties allows the inner display values to be updated, and direct child elements will inherit this display property
* The standard box model
    * in the standard box model, adding `width` or `height` attributes will define these for the **content** box; any padding / border is then *added* to that width and height to get the total box dimensions
    * the margin is not counted towards the actual box size; the box's area stops at the border -- margin affects the total space that the box will take up on the page, but only affects the space outside the box
* The alternative CSS box model
    * because it's annoying to think about adding up these element dimensions, an alternate was introduced -- using this model, any width is the width of the visible box on the page
    * browsers use the standard model by default -- to turn *on* the alternative model, you do so by setting `box-sizing: border-box` on the element
    * `box-sizing: border-box` will constrain the element's dimensions to match what was set using `width` or `height` properties
    * To set the alternative model on all elements, set the `box-sizing` property on the `<html>` element, then set all other elements to inherit that value, as shown below
    ```
    html {
        box-sizing: border-box;
    }
    *, *::before, *::after {
        box-sizing: inherit;
    }
    ```
* Margin - the invisible space around the box
    * it pushes other elements away from the box
    * can have positive or negative values -- setting a negative value may cause the box to overlap other elements on the page
    * margin is added after the size of the visible box has been calculated (in either model)
    * Margins will collapse into each other when two elements have touching margins; the margin width will then be inherited from the element whose margin is largest; if one element has a negative margin, it will be subtracted from the larger margin (ex 50px & -10px will result in a margin of 40px)
* Border - drawn between the margin and padding of a box
    * in the standard model, the size of the border is added to the `width` and `height` of the box
    * in the alternative model, the size of the border makes the content box smaller as it takes up some of the available `width` and `height`
* Padding - sits between the border and the content area
    * typically used to push the content away from the border
    * cannot have negative amounts of padding -- must be 0 or a positive value
    * background applied to an element will display behind the padding
* Using `display: inline-block`
    * the middle ground between `inline` and `block` display styles
    * useful when you do not want to break an item into a new line, but do want it to respect `height` and `width` values, and avoid overlapping
    * useful for giving a link a larger hit area, by adding `padding`

### CSS Box Model
* The basic box model: when rendering a document, the browser engine will represent each element as a rectangular box. These boxes have predefined styles and determine size, position, and properties of the box.
* Each box contains the content, padding, border, and margin
* Content area - contains the actual content of an element (ex. text, images, video, etc); its dimensions equal do the dimensions of the content (ex. an image of 700 x 700 px will render a 700 x 700 px content area)
    * If the `box-sizing` property is set to `content-box` and the element is a block element, the content area's size can be explicitly defined with the `width` and `height` properties, with or without the `min-` or `max-` prefixes
* Padding area - bounded by the padding edge; extends the content area to include the element's padding; its dimensions are the `padding-box` width and height
    * thickness of padding is determined using the `padding` properties, with or without a directional suffix (`-top`, `-right`, etc.)
* Border area - bounded by the border edge; extends the padding area to include the element's borders; its dimensions are the `border-box width` and ` height`
    * thickness of borders can be determined using the shorthand `border` or its directional properties (`-bottom`, `-left`, etc.); also accepts `min-` or `max-` properties
    * if a background is set on a box, it will extend to the outer edge of the border (it extends underneath the border in z-ordering); use `background-clip` to alter this behavior
* Margin area - bounded by the margin edge; extends the border area to include an empty area used to separate an elements from its neighbors
    * size of the margin area is determined using `margin` or `margin-` directional properties
    * for non-replaced inline elements, the amount of space taken up is determined by the `line-height` property

### Resources
* [`<hr>` The Thematic Break (Horizontal Rule) element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/hr) on MDN
* [Outline gradient icons by Icongeek26](https://www.flaticon.com/authors/icongeek26/outline-gradient)
* [Pexels API](https://www.pexels.com/api/)
* [Add gradient overlay to background image](https://stackoverflow.com/questions/36679649/how-to-add-a-color-overlay-to-a-background-image)
* [Intro to the basic CSS box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model) on MDN
* [The box model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model) on MDN
* []()
* []()

<!-- # 🗼 static -->
<!-- A solo challenge to re-create a static desktop layout. The challenge allows for some creative licence, though the layout is meant to be replicated exactly. -->

<!-- ## [See the app in action](https://nichelicorn.github.io/static/src/index.html) -->
<!-- ### Mobile dashboard -->
<!-- ![a gif of the mobile layout of the page, scrolling top to bottom](/assets/mobile.gif) -->

<!-- ### Desktop to tablet dashboard -->
<!-- ![a gif of the desktop and tablet layouts, with the page layout shifting with the screen size](/assets/desktop-tablet.gif) -->


<!-- ## The dashboard to be replicated -->
<!-- ![a desktop layout with a header, several buttons, and a table outlining a job description](/assets/static-comp-challenge-3.jpg) -->


<!-- ## Author -->
<!-- <table> -->
    <!-- <tr> -->
        <!-- <td>Nichele D 🦄 <a href="https://github.com/nichelicorn">GitHub</td> -->
    <!-- </tr> -->
    <!-- </tr> -->
        <!-- <td><img src="https://avatars.githubusercontent.com/u/63027000?v=4" alt="Nichele D, aka nichelicorn" width="150" height="auto" /></td> -->
    <!-- </tr> -->
<!-- </table> -->
<!--  -->
<!-- ## Technologies -->
<!-- <table> -->
    <!-- <tr> -->
<!--         <td>Functionality</td> -->
        <!-- <td>Structure</td> -->
        <!-- <td>Styling</td> -->
<!--         <td>Style Maintenance</td> -->
<!--         <td>Bundler</td> -->
    </tr>
    </tr>
<!--         <td><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/99/Unofficial_JavaScript_logo_2.svg/1200px-Unofficial_JavaScript_logo_2.svg.png" alt="The JavaScript logo, a yellow square with the uppercase letters JS in the lower right corner" width="100" height="auto" /></td> -->
         <!-- <td><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/61/HTML5_logo_and_wordmark.svg/240px-HTML5_logo_and_wordmark.svg.png" alt="The HTML5 logo, an orange shield, with the letters HTML above, and the number 5 superimposed over the shield" width="100" height="auto" /></td> -->
        <!-- <td><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/CSS3_logo_and_wordmark.svg/240px-CSS3_logo_and_wordmark.svg.png" alt="The CSS logo, a blue shield, with the letters CSS above, and the number 3 superimposed over the shield" width="100" height="auto" /></td> -->
<!--         <td><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/96/Sass_Logo_Color.svg/220px-Sass_Logo_Color.svg.png" alt="The Sass logo, a cursive rendition of the name Sass in mauve lettering" width="100" height="auto" /></td>         -->
<!--         <td><img src="https://raw.githubusercontent.com/webpack/media/master/logo/icon.png" alt="The webpack logo, a blue three-dimensional box, turned at an agle to the viewer. There is a smaller box inside in a darker shade of blue. Each edge of the box is outlined in white" width="100" height="auto" /></td> -->
    <!-- </tr> -->
<!-- </table> -->
