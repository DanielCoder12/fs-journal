# Bootstrap
make sure style.css is the last link tag in the head

containers hold grid system
container->row->column
rows divide the website vertically
columns divide the rows horizontally 
12 columns to divide the row into
once 12 columns is reached new columns will stack underneath
2 col-6 will divide it in half, 3 col-4 will make it thirds etc

make header container, main container, footer container
link: bs5 will link bootstrap to html

div class="container" 
container class will have a little padding/margin by default 
container-fluid class will get rid of padding/margins on the side
adding a class bg-danger will make the background red, other colors can be picked with different names
text-primary will make the text color blue
fw-bold (font weight) fs-# (font size) in the class 
mdi icons count as text ^ these font things will work for it

<!-- SECTION use section anchors to make code easier to look through -->
<section> tag, use for rows, give it class="row"
section.row will make a section tag with a row class automatically

div class="col-6" will add a column, interchange number to change amount of columns present
ctrl d does multi select


breaking bootstrap grid will add a little bit of horizontal scroll, scroll means something broke (check spelling)
.col-# will automatically make a column div for you
p-1-5 in the class will add padding to your column
m-1-5 in the class will add margin to your column
mt margin top mb margin bottom ms margin start (left) me margin end (right) same for padding
my will put margin on the y axis 
margin on the x axis can break bootstrap

align-items-center in the class will adjust flex behavior
justify-content-center in class will center it 
text-center will align text/images/buttons center text-right will do right etc
text-light in the class will make text white
img-fluid will make an image not exceed the boundaries of a column
rounded class will add rounding to image

with a column 12 row, aligning the row with flex wont do anything because the columns take up the entire space, it will move if you col-1-11
flexing a row will only flex the column not the stuff inside it

col-md-# will change the columns depending on screen size
sm (small) md (medium) lg (large) xl (extra large) xxl (extra extra large)
p-md-1-5 will add padding just to medium screen sizes

btn (button class) btn btn-color will change buttons color
btn btn-outline-light (in class) will add a light outlined button
(buttons at top)
d-none (display none) will stop displaying the thing
d-md-block will display it again as block (can be changed to stuff like flex for example) once the screen size is met

sticky-top will make it stick to its parent element (how to make headers always show)

use bootstrap pre made code for nav bars or stuff like that

.col-12.col-md-3*3 will make 3 div's with col-12 col-md-3
don't put padding on x axis of rows

target="_blank" after the link on an a tag will open the website in a different tab
order-# will set an order on different columns
order-md-# will let the order change depending on screen size

day 4

you can put rows in columns to make positioning inside the column easier
d-none d-md-block will hide display of object on mobile but show it on everything else


class"h-100" will make the thing you put it on 100% of its parent class 