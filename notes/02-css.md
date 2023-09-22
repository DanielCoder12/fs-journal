# CSS
padding: _px _px _px _px will add space to selected element
top right bottom left
fine tune on the websites console
🛢️windows . to get emojis
. class tag will select class, no . will look for regular tags with that name
em is a font size based on screen size
example: font-size: 2em;
border adds a border, look at mdn reference to see examples of borders
adding -bottom targets only the bottom
example: padding-bottom, border-top, margin-right
margin puts space around the outside of elements, padding puts spacing inside elements
vh stands for view height, % of current height of viewport
example: margin-top 10vh
vw means view width
example: margin-right 2vw
img lets you select image tags
max-height: _vh lets you set size of an image
display <--changes display property
display: flex; will make display of the element flex
flex will put elements side by side

will only change the element that is selected, not the div's inside the element
justify-content can be used with flex display, use website elements to try different styles
hero section of a website is the main section, generally main
% takes up the percentage of parent tag
example 

body tag is always set up with a little margin
body{
    margin: 0;
} will fix that
4.5 is the minimum contrast ratio standard
background-color changes background color
color: white; will change the text color
children inherit changes you make to parent tags

footer > div lets you select all of the div in the footer
text-shadow _px(x) _px _px(blur) color; will let you add a shadow and offset it on different axis and add blur
box-shadow will let you add shadow to element holding the text, images also
border-radius: _px; will let you round images or borders
!important will increase specificity 
importance goes in the order element, class, id
nothing selects by element
. selects by class
# selects by id

day 4
background-image: url() can let you set a background image
if nothings in the row height: #vh (view height) will let the image show
min-height will allow height to grow when screen size changes

background-size: cover; will stretch the image to the row
background-position: bottom/center/etc; will change the focal point of the image
backdrop-filter: blur(#px); will add blur to your background-color
add opacity to your background-color to make blur work
-webkit-backdrop-filter: blur(10px); will allow websites that don't support blur to have it
webkit's for specific things help had support

position: ; will allow you to set your position of your objects such as a button, image, text etc
position: absolute; will position relative to the element its nested in i think
top: #; left: #; bottom: #; right: #; will let you move in in those directions
position: relative; will do something else, maybe ask what it does

utility classes are classes that only do a single thing
example: class="justify-center" if you make that class only justify center you can add it to multiple div classes instead of each individually

box-shadow: x_px y_px blur _px color
use google fonts to get custom fonts, on the website copy and past the link html tag and put in the head
make a font utility class and paste the other command from the website in there

@media(max-height #px /max-width: #px){
.hero-image{ 
background-image: url()}

.shopbutton{
 text-align: center;
}
}

this will change the background image depending on if the screen size changes to the parameters you set
media rules should be defined at the bottom of your style sheet so it isn't overridden by your other code
try to write media rules in tandem with bootstrap so they apply at the same breakpoints

this will also center the button when it goes to mobile view at the same time it changes the background image

lighthouse can help with fixing accessability issues (on google console thing)


