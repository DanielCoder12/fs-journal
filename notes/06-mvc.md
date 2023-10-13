# MVC

model view controller

ctrl p lets you look through your files

ctrl . will add an import for you

ctrl . can also add a function into another file for you

view is what they see (index.html)
controller is app.js, will have multiple javascript sheets

controller captures user input, sends it to the service to change data

bcw create in the terminal to start projects now
this week select the mvc option


import is how you bring code in from multiple js files into each other
export makes the code available to be imported 
appstate files stores your global variables
router

name your controller with the piece of information they are affecting
example PingPongPlayersController
a method is a function on an object
good naming convention, your class name should be the name of your controller file

put a constructor inside your controller
constructors run code inside of your controller once they are built, they only run once

your controller should be the only thing users can interact with 

export class ControllerName {}
if you don't export your class no other file can use it
then you must import it at the top of the sheet you want to use it from


name private functions with an underscore before the name

const guy = {
    name: 'guy',
    lastName: 'Dude',
    func: () => { this.name }
}
this command lets you access things that are being defined in the same object
controllers job to update view/update html, make it a private function
appstate houses the information that gets displayed such as html that gets copied when multiple cards are made
service updates the numbers


your controller only deals with one specific type of data in your appstate, if you have multiple types you need multiple controllers
load multiple controllers in your router as an array


AppState.on('coins', ()=>console.log('coins changed'))
any time the value of coins changes in the appstate the console log message will go off
put it in your constructor in the controller so on page load it will register a listener to that variable
 .on only triggers a listener when a new value is assigned aka a equals sign triggers the listener
having .on watch an array and pushing something into it wont trigger the listener since a new value isn't being assigned
appstate.emit('name your listener is watching') this will manually trigger the listener 


 pop is the sweet alert method 
 pop.whatever() to use the sweet alert



local storage stuff is handled only in the service
in the service
function _saveMyGachamon() {
    'key'
    saveState('myGachamon', AppState.myGachamons)
}

loadState('myGachamon',[Gachamon] )
this will let you access your locally stored gachamon array

.splice will take something out of an array
you have to provide it where to start removing and how many things you want to remove


the href inside of an a tag will change the website url

${boolean ? '' : ''} if the boolean is true it will return the string on the left, if false it returns the right one

getters can call other getters using ${this.otherGetterFunctionName}

on a form make your for="" id="" and name="" all what you want your input to be called in javascript
required will make it so that field of your form is required to be filled out for it to be submitted
you can also add minlength and maxlength when
 dealing with text
when dealing with numbers you have to have either a min or a max instead of minlength and maxlength
placeholder="" will let you put grayed out text in your input
type="checkbox" will make a checkbox, required on a checkbox will make it so you have to check it
type="url" will make sure you can only put in urls
type="color" will let you pick a color and it will pull out a hex value
putting value="#hexcode" will make that color the default color that displays

textarea tag will make a text area for forms
use onsubmit instead of onclick for forms
event.preventdefault() will make a form not refresh the page when submitted

getFormData(form) will automatically make an object for you
try {
const form = event.target
const carData = getFormData(form)
} catch(error) {
    pop.error(error.message)
    console.error(error);
}

try will run all the code inside it and if an error happens it will stop running it and switch to running catch
use try catch on creates
throw new Error() will trigger your catch automatically

form.reset() will reset your form for you

saving to local storage happens in the service
the function 

style="" does css styling inside of your html

this.listedAt = data.listedAt || new Date().toLocaleString() make the date display what time it was when your thing was made
looks to see if data.listedAt exists and if it doesn't it creates a new one for it
supposedly turns the date into a string


this.listedAt = data.listedAt ? new Date(data.listedAt).toLocaleString() : new Date().toLocaleString()
pretty much does the same thing but keeps it a date instead of turning it into a string

this.id = generateId() will create a unique id for every object in an array when that object is created

pop.confirm is a confirmation sweet alert
returns something called a promise

add async before your method and put await before pop.confirm if you want the promise to be resolved before continuing to run code 

selectionRange(start, end) can make the users cursor go where you want when a function happens

offcanvases don't go inside your main they go outside of it



API
Application Programming Interface
defines how two applications communicate with eachother using requests and responses



promises take in an executor to either resolve or reject 
use async and await to let a promise resolve before you run code past it
important for api's 

CRUD
Create Read Update Delete

create- http post
read - http get
update - http put
destroy - http delete


use a try catch for any method that will deal with an api
script axios in the html to bring axios into javascript

service handles the getting information from the api

await getMonsters(){
const response = await axios.get('api link')
}
this makes a request to your api to get the information from it

use .map to make new objects from your api

authentication strings are in the codeworks sandbox
put them in the env.js

apt.get('link') is a shortened version of axios.get('link')

in service
async createCar(carFormData){
    const res = await api.post('api/cars', carFormData) adding the data from your form into the api
}

async removeCar(carId){
    const res = api.delete(`api/cars/${carId}`) this will delete the car with that id, you can only delete cars you made or you'll get a 403
}


static means a function now statically exists only on the definition of a class
static get CarFormTemplate
now you can do Car.CarFormTemplate


timeout: 8000 if api response doesn't come back within 8 seconds or time cap you put it'll throw an error

.put('link', payload) updates data in the api

:D



