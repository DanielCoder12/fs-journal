# Vue

vue starter

vue files all have html, javascript and css in each file
each individual vue file now has a controller in it
bcw serve doesn't work anymore you have to use debug thing to spin it 😢

homepage.vue is usually where you start
double {{}} interpolates javascript in your html

scoped on style sheet makes your css only affect the html in your vue sheet

inside setup is where you declare your values, if you want them to be accessible by html you have to put them in the return
inside setup is private stuff, inside return is public stuff

@click replaces onclick for view
@submit.prevent automatically prevents default on form submit

import logger to use the console without breaking application
let cheese= ref(0)
cheese.value++
cheese automatically redraws when the number gets updated

reactives can only do objects, refs can use any data type   
appstate is reactive 

cheese: computed(()=> {return Appstate.cheese}) automatically wraps in a ref to make it reactive
cheese: computed (() => Appstate.cheese) shorter way of writing it

v-for="upgrade in upgrades" :key="upgrade.name"
key should be something unique on the object like the id
{{ upgrade.name }}
for each loop written in html awesome

<div v-if="upgrade.quantity > 0 ">Qty : {{upgrade.Quantity}}</div> if statement for conditional rendering in html so hype

:disabled="upgrade.price > cheese" if true automatically adds disabled property more conditional rendering in html hype
:class="{'bg-primary': cheese >= upgrade.price, 'bg-danger': cheese < upgrade.price}" even more hype conditional rendering


you can pass through the entire object when you use a v-for
v-if and v-else have to be direct siblings to work, v-else doesn't provide a condition
v-else-if you can provide a condition

kinda like a constructor
onMounted (() =>{

})
like a constructor that only runs when you leave a page
onUnMounted (() =>{

})

App.vue is where you go to write global styles for css


const route = useRoute()
lets you pull stuff out of the url

const router = useRouter()
this lets you change what the current route is

{...Appstate.activeCar}
spread operator creates a new object with the properties of the one your spreading


