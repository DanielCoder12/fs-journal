# JavaScript
app.js

label console logs

script tags to link javascript go in the bottom of the body
<script src="app.js"></script>

let firstName = 'Jeremy' let command stores variable 
firstName becomes stored as Jeremy in this case
console.log(firstName) will log Jeremy in the console

var middleName = 'Bob' will do the same thing, but is outdated used let instead

const lastName = 'Fowler' (constant) another way to declare a variable 

const means its a constant variable, it cant be reassigned, let can be reassigned 
firstName = 'Jerms' will change the name after its been declared
lastName = 'CatDaddy' will not change the name because the previous variable was declared constant

console.log('my name is' firstName, middleName, lastName)
will display my name is Jerms Bob Fowler

console.log('my name is' firstName + middleName + lastName)
will display my name is JermsBobFowler

console.log(`my name is firstName`)
will display my name is firstName

console.log(`My name is ${firstName})
will display my name is Jerms

const catchPhrase = "How you doin'" double quotes have to be used to get a single tick in there
console log will now display How you doin'

const catchPhrase = `How you doin' "darlin"` backticks will let you use two quotes and a single tick
console log will display How you doin' "darlin"


boolean true or false

let jeremyLikesCats = true

let jeremyLikesTomatoes = false

if(jeremyLikesCats == true){
 console.log('cat');
}
if(jeremyLikesCats ){  <----- same thing as one above because its a boolean
 console.log('cat');
}
since its true it will log cat into console

if(jeremyLikesTomatoes){
console.log(tomato)}
else{
    console.log(no tomato)
}
no tomato will be logged because jeremy likes tomatoes is false

one equals sign assigns a value, double equals sign compares values
three equal signs is a strict comparison, the values have to equal and the data types also have to equal
if (2=='2'){
    console.log(two)
}
this will log two because 2 = 2
if (2==='2'){
    console.log(two)
}
this wont log anything because 2 does = 2 but 2 isn't the same as '2'


numbers

const num1 = 5

let num2 = 5

num2 = num1 + num2 <- this will make num2 10 without changing num1's value

num2 += num1 will do the same thing as the code above

num2 + num1 <- this wont work cause no equals means your not changing the values, its just doing math

num2 /= 2 will divide by 2 and reassign the value to the answer

num2 *= 10 will multiply by 10 and reassign the value to the answer

num2 = (num2 + 25) / 2 will add 25 before dividing by 2 because of PEMDAS


console.group('name of group')
will let you collapse any console logs within the group 
console.groupEnd()

camel case: first word starts as lowercase and all following words start uppercase 
example: myCoolCase

kebab case: words have dashes between them (html writing)
example: my-cool-case

pascal case: every word is uppercase
example: MyCoolCase

snake case: every word separated with _
example: my_cool_case


setup javascript sheet in sections
global variables at the top of the sheet
add a section for functions

split editor button can bring up two tabs


const weirdFunction = () => { <--- another weird looking way to create a function

}

function selectCheese(){ <---how to create a function in javascript

}

function selectCheese(){
    console.log ('selected cheese');
} this function will run whenever selectCheese is called upon 

selectCheese() will call upon it and make the function run, it will tell it to run
parenthesis invoke or call the function

onclick="selectCheese()" in html on the button you want will make the select cheese command run in javascript

 

function selectCheese(){
    console.log ('selected cheese');
   let userInput = '' 
    userInput = 'cheese'
}
creates a variable called userInput, sets it to cheese and then forgets about it once the function has run, (doesn't store variable)

   let userInput = '' 

function selectCheese(){
    console.log ('selected cheese');
    userInput = 'cheese'
}
moving userInput = '' out of the function will permanently store it in memory
clicking cheese will now keep track of user input and put cheese in it
userInput = cheese will only make userInput a single cheese
userInput += cheese will make userInput cheese cheese and will add a cheese every time you click it

function selectFoodItem(foodItem){<-parameter takes on argument that gets passed through
    console.log('Selected Food Item!', foodItem);
}

function selectFoodItem(foodItem){
    userInput =+ foodItem   <---will set user input to whatever foodItem variable becomes
    console.log('Selected Food Item!', userInput);
}

in html
<button onclick="selectFoodItem('cheese')></button>

now when you click on this button it will set foodItem to cheese and log cheese into userInput



const userInputElement = document.getElementById('currentUserInput')
userInputElement.innerText = 'userInput'

for this to run, add an id called currentUserInput to the p tag you wish to be written in when clicked



function updateUserInput(){
    const userInputElement = document.getElementById('currentUserInput')
userInputElement.innerText = 'userInput'
}
now if you add updateUserInput() to other functions, it will call upon this function so you don't have to write it out multiple times


function checkUserInputAgainstCode(){
    if(userInput == 'secretMessage'){
        console.log('you got the code')
    }
    else{
        console.log('didn't get the code')
    }
}

this will compare the user input to the secret code, if they are the same you win if they are different you lose


function checkUserInputAgainstCode(){
    if(userInput == 'secretMessage'){
        console.log('you got the code')
        const secretImageElement = document.getElementById('secretImage')
        secretImageElement.src = 'insert image source here'
    }
    else{
        console.log('didn't get the code')
    }
}

if you put the secretImage id on your img tag this function will access that image when its ran and change the source to the image
getElementById will only change the first Id with that same name, it wont do two at once 


javascript day 2

arrays and objects

const person = {
name: 'jeremy'
key     value
} now you can create key value pairs 

const person = {
    name: 'Jeremy',
    age: 32,
    likesCats: true,
    favoriteFoods: ['sushi', 'broccoli', 'croissant sandwich from Winco']
} arrays can also store groups of information 

person.name will say the value stored under name in the array


console.log(`i ${person.likesCats ? 'love' : 'hate'} cats`)
the question mark will return left of the colon if the boolean is true and right of the colon if the boolean is false


const referenceToPerson = person
will make a reference to person
you cant alter data in the data set without changing the original

const copyOfPerson = {...person}
will make a copy of person with the same data
you can alter data in the data set without changing the original

arrays

const arrayOfNums = [1, 2, 3, 4]
const arrayOfStrings = ['hey', 'sup', 'dawg']

const arrayOfWeirdThings = [1, 'sup', person, [1, 2, 3] ,, {}, true]
console.log(arrayOfWeirdThings[3][2]) this will show up as the number 3 because its 4th in the array and 3rd in the array in the array

const arrayOfCats = [
    {
        name: 'Gopher', 
        age: 7,
        hasTail: true,
        numberOfLegs: 4
    },
    {
        name: 'Dudley'
        age: 2,
        hasTail: true
        numberOfLegs: 3.5
    }
    {
        name: 'Frankie',
        age: 10
        hasTail: true,
        numberOfLegs: 4.5
    }
    {
        name: 'Falcon',
        age: 1
        hasTail: false,
        numberOfLegs:4
    }
    
]
where it starts,    how long it runs    what to do next
for (let i = 0; i < arrayOfCats.length; i++){      <---for loop, will look through the entire array
const cat = arrayOfCats[i]
console.log(cat.name)                    this console log will list every name of every cat under the arrayOfCats array
}

function sup() {
    console.log('sup')
}

arrayOfCats.forEach(sup) forEach will run through the sup command for every cat in the array
running this will log sup 4 times
 arrayOfCats.forEach((cat)=> {console.log(cat.name);}) this will log every cat name, forEach does the same as a for loop

 arrayOfCats.forEach((cat)=> {
    console.log(cat.name);
    console.log(cat.age)
    })

    const foundCat = arrayOfCats.find(cat => cat.name == 'Gopher') this will look through the array until it finds a cat named Gopher

    console.log(foundCat) this will log all the information of Gopher not just his name
    find only returns the first object in the array that matches the given variable

    const filteredCats = arrayOfCats.filter(cat => cat.hasTail)
    console.log('filteredcats', filteredCats) this will filter through and only log the cats with tails 

    const filteredCats = arrayOfCats.filter(cat => !cat.hasTail)
    console.log('filteredcats', filteredCats) this will filter through and only log the cats without tails

    const randomIndex = math.floor(Math.random() * arrayOfCats.length)
    console.log( 'random cat', arrayOfCats[randomIndex]) this will make a random cat show up in the console


function accuseAnimalOfMurder() {
    const accusedAnimalEmoji = window.prompt('who did it?')
    console.log ('user input from prompt', accusedAnimalEmoji); this will open a window that lets you type in it and log what you type  const guiltyAnimal = animals.find(animal => animal.isGuilty) this checks if the animal is guilty
    
    if (guiltyAnimal.emoji == accusedAnimalEmoji) { if you guess the right one you win
        window.alert(`good job`)
    }
    else{
        window.alert(`bad job, wrong one`)  if you guess the wrong one you suck
        commitMurder()
        changeAnimalLocations()
    }
}

function commitMurder() {
    const guiltyAnimal = animals.find(animal => animal.isGuilty)

    const potentialVictims = animals.filter( animal => animal.currentArea == guiltyAnimal.currentArea && animal != guiltyAnimal)
filters for animals who are in the same area as the killer and makes sure the animals listed aren't the killer

const randomAnimalIndex = Math.floor(math.random() * potentialVictims.length)

const randomVictim = potentialVictims[randomAnimalIndex]



randomVictim.emoji = 'skull'


}


return command hard stops a function

day 3

objects inside of an array cannot be accessed with dot notation
 
example
const menuItems = [
    {
        name: 'name',
        price: 1,
        quantity: 1
    }
]
menuItems.name cant access the name

const name = menuItems.find(menuItem => menuItem.name == 'name') this will search the array for an object with the name "name" and pull out all the information of that section in the array

const totalPrice = (menuItem.price * menuItem.quantity).tofixed(2) this line will make the total price only ever end to the second decimal like 11.00 .

.tofixed also converts the number into a string

.toString() will turn a number element into a string

every time a destructive action happens you must get user confirmation
example: on a clear cart button make a prompt that asks if they really want to clear the cart
or on a checkout button make a prompt that asks if they're sure they want to check out

const wantsToCheckout = window.confirm ('do you want to check out?')

if (!wantsToCheckout){ asking if the opposite of wantsToCheckout is true
return
} return hard stops the function if they dont want to check out
if they do want to check out return wont run and all the code after it will

sweetalert2 is a javascript website that can bring in better pop ups by linking in script tags
put them above your javascript link


Day whatever's next


const kuzcoElement = document.getElementById('kuzco')
const statsElement = kuzcoElement.querySelector('.stats') will look through your html for the first element with the name stats inside of where your element Id is. how to select classes with javascript instead of id's


console.error() when an error happens you can make a custom error message in the console


if(foundAnimal.hunger >=){
    foundAnimal.hunger = 100
} this is a clamp

setInterval(handler: timeHandler)takes in two arguments 
setInterval(animalsHungerDecreases, 1000) this will run the animalsHungerDecreases function every section. the time is in milliseconds and 1000 milliseconds is equal to one second
put setInterval at the bottom of javascript so it runs in the background

animalPenElement.classList.add('bg-farm') this will add the class bg-farm to whatever animalPenElement is selecting
.remove also exists to remove classes through javascript 

switch statement looks at a single value and runs code based on that value

let money = 0, switch will console log 'no money'
let money = 10 switch will console log 'money is above 1'
let money = 1 switch will console log '1 money'

switch (money) {
    case 0:
    console.log ('no money')
    break;

    case 1:
    console.log ('1 money')
    break;

    default:
    console.log('money is above 1')
    break;
}

outerMarquee = animalElement.querySelector ('marquee') selects the marquee tag in html
innerMarquee = animalElement.querySelector ('marquee>marquee') selects marquee tag inside of marquee tag

.setAttribute can change or assign new attributes to html from javascript
outerMarquee.setAttribute('scrollamount', '1')
innerMarquee.setAttribute('scrollamount', '1')