# Node

bcw create node-server-auth0
you don't use html while using node 😢

env stands for environment variables, has urls that lets us access the database
gitignore file makes it so any file you put in it doesn't get pushed up to github

click the bug button and then start server to use localhost 3000
when you make changes and want to test them you have to restart 
mvc design pattern is still used in apis

reference values controller, service and model if confused about writing your own

extends command inherits members from whatever you connect

ex: export class ValuesController extends BaseController
values controller is inheriting everything from the base controller

super() calls the constructor from the inherited controller


putting /something in the empty string will add it to the end of your url and they will have to look up that url to get a response
this.router.get('', this.getCats).get('', this.test) you can chain methods

can call request response next whatever but they have to be in that order
getCats(request, response, next) {
try{

response.send('response')

}
catch(error){
    next(error)
}
}

controllers never directly interact with a database

controller has to tell service to get cats and then give them to the user who called them
async getCats(request, response, next) {
    try{
    const cats = await catsService.getCats()
response.send(cats)

}
}

service has to get cats for the controller and then return them to it
async getCats() {
    const cats = await fakeDb.cats
    return cats
}



they can now put anything after the / and the catId function will call
this.router.get('/:catId', this.getCatById)

async getCats(request, response, next) {
    try{
   const catId = request.params.catId final thing has to match what you put through in the this.router
   const cat = await catsService.getCatById(catId)
   return response.send(cat)
}
}
in service
async getCatById(catId){
const foundCat = await fakeDb.cats.find(cat => cat.id == catId)
if(!foundCat){
    throw new BadRequest(`invalid id ${catId}`)
}
return foundCat
}


post requests
in constructor
.post('', this.createCat)
in controller
async createCat(request, response, next){
    try{
const catData = request.body
const cat = await catService.createCat(catData)

    } catch(error){
        next(error)
    }
}
in service
async createCat(catData){
const newCat = new Cat(catData)
fakeDb.cats.push(newCat)
return newCat
}

when writing in JSON you have to use double quotes and if you have a comma something else has to follow it


delete requests
in constructor
.delete(':/catId', this.destroyCat)
in controller 
async destroyCat(request, response, next){
    try{
const catId = request.params.catId
await catsService.destroyCat(catId)
response.send('cat got deleted 😢')
    } catch(error){
        next(error)
    }
}
in service
async destroyCat(catId){
const catIndex = fakeDb.cats.findIndex(cat => cat.id == catId)
if(catIndex == -1){
    throw new BadRequest(`Invalid Id ${catId}`)
}
fakeDb.cats.splice(catIndex, 1)
}





express mvc

a workspace lets you work on multiple projects in one vscode file
to push a workspace up to github push it in the non workspace view 
client folder you open terminal, bcw serve 
use the bug button to run your server
you now have two things open at once holy crap

put your domain audience and clientid in your front end env file to connect auth0

put your audience, clientid, connection string, domain in your back end env file to connect auth0
on your connection string replace <password> with your password you saved
maybe once it works slack yourself the back end env file so you can copy and paste it later

mongoose is a translater that puts javascript into your database


backend model
remember to import schema
export const CarSchema = new Schema({
    make: {type: String, required: true, maxLength: 20},
    model: {type: String, required: true, maxLength: 50},
    price: {type: Number, required: true, min: 0, max: 1000000},
    year: {type: Number, required: true, min: 1886, max: 2024},
    runs: {type: Boolean, required: true, default: true},
    color: {type: String, required: true, minLength: 4, maxLength: 7, default: '#000000'},
    imgUrl: {type: String, required: true, minLength: 20, maxLength: 500},
    mileage: {type: Number, required true, min: 1, max: 500000},
    description: {type: String, maxLength: 500}
    creatorId: {type: Schema.Types.ObjectId, required: true, ref: 'Account'}
},
{timestamps: true, toJSON: {virtuals: true}}
)

DbContext folder

class DbContext{
Cars = mongoose.model('Car', CarSchema)
}
makes a spot in your mongo database to store your info
you can make different sections in your database if you add the title into your connection string in the env folder


talking to a real database get cars method

mongoose methods are named similar to javascript methods but do different things, .find() mongoose method will give you back everything
in dbContext.Cars
async getCars() {
    const cars = await dbContext.Cars.find()
    return cars
}


talking to a real database to create cars with verification

this.router
.get('', this.getCars) this will still run without authorization because it happens before the .use
.use(auth0Provider.getAuthorizedUserInfo) you have to import auth0Provider
.post('', this.createCar) this wont run without a valid bearer token because of the .use


async createCar(request, response, next){
const carData = request.body
const userInfo = request.userInfo
carData.creatorId = userInfo.id
const car = await carService.createCar(carData)
response.send(car)
}

async createCar(carData){
    const car = await dbContext.Cars.create(carData)
    return car
}

async getCarById(carId){
    const car = await dbContext.Cars.findById(carId)
    if(!car){ throw new BadRequest(`${carId} is not a valid Id`)}
    return car
}

async destroyCar(request, response, next){
    const carId = request.params.carId
    const userId = request.userInfo.id
    const car = await carsService.destroyCar(carId, userId)
}

async destroyCar(carId, userId){
const carToBeDestroyed = await dbContext.Cars.findById(carId)
if(carToBeDestroyed.creatorId != userId){
throw new Forbidden("not your car 😢")
}
await carToBeDestroyed.remove()
}



.put('/:carId', this.updateCar)

async updateCar(request, response, next){
const carId = request.params.carId
const userId = request.userInfo.id
const carData = request.body

const updatedCar = await carsService.updateCar(carId, userId, carData)
return response.send(updatedCar)
}

async updateCar(carId, userId, carData){
    const carToBeUpdated = await this.getCarById(carId)

if(carToBeUpdated.creatorId.toString() != userId){
    throw new Forbidden ("not your car")
}

    carToBeUpdated.make = carData.make || carToBeUpdated.make
    carToBeUpdated.model = carData.model || carToBeUpdated.model
    carToBeUpdated.price = carData.price != undefined ? carData.price : carToBeUpdated.price
    carToBeUpdated.runs = carData.runs != undefined ? carData.runs : carToBeUpdated.runs

    await carToBeUpdated.save()
    return carToBeUpdated
}

mongodb.net/<appname here> <----- connection string thing

database -> browse collections show your databases
