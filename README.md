# Color Generator
Color generator app built using VueJS in NUXT

![Color Generator](https://github.com/ancastro/color_generator/blob/master/color_generator.png?raw=true)

## Usage
Hit `spacebar` to generate a random color palette

`Click` a color hex value (***ex. #5AB1BB***) to copy the value to your clipboard. Its that easy 😊

inspired by [coolors.co](https://coolors.co/)

## How its built
#### Generating Colors
Using an array of all possible hex values `['0','1','2','3','4','5','6','7','8','9','a','b','c','d','e','f']`

we have a ***generate_color()*** function that takes a random character from the array and builds a string ***6*** characters long creating the hex value (***ex. #5AB1BB***)

We then bind that hex value to the `background-color` of their respective color containers

To change the color we add an event listener on the window to check for `keydown` of the `spacebar` inside the Vue lifecycle hook `mounted()`. If so then run ***generate_color()*** again and generate new colors for the color containers

#### Copying to Clipboard
When we click on a hex value we have a `@click` event handler that takes the color value and uses the Clipboard Api to save it to the clipboard `navigator.clipboard.writeText(color)`
