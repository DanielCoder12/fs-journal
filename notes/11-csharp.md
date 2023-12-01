# CSharp

Console.WriteLine() is console log
every line of code has to end with a semi colon;
'' are reserved for strings with single characters

when declaring a variable you have to declare what datatype that variable is
ex:
 string name = "Jeremy"; Explicit type
var weird = "Miles"; Implicit type

char declaration lets you store a single letter as a variable
char character = 'J';

string interpolation
Console.WriteLine ($"Hello my name is {name}, and my name starts with {character}");
`` not valid character in csharp

Console.Clear(); clears your console

string multilineString = @"
multi-line string
use @ sign 
";

string? otherName = null; lets you create null variable



Booleans

bool likesCats = true;
bool likesTomatoes = false;

if(likesCats)
{ <- curlies start on the next line down
Console.WriteLine("example"); <- this still needs semicolons
} <- no semicolon needed for code blocks 
else
{

}

doesn't work, theres no truthy falsy in csharp
if(name)
{

}
have to do this instead
if(name == "miles")
{

}
undefined also doesn't exist in csharp
=== doesn't exist in csharp


Numbers


int num = 7;
int num = 7.7; doesn't work
integers have to be whole numbers
double numWithDecimals = 7.7; use for decimals

int sum = num + 11;
Console.WriteLine(sum); logs 18

int weirdInt = 7 / 2;
Console.WriteLine(weirdNum); returns 3 
because its defined as an integer it just removes the .5 

double weirdDouble = 7.0 / 2.0;
numbers in a double declaration have to be a double
Console.WriteLine(weirdNum); returns 3.5

int multiplied = 7 * 3 
Console.WriteLine(multiplied * 2 ); returns 42
Console.WriteLine(multiplied); returns 21 

multiplied += 100
Console.WriteLine(multiplied); returns 121



for loop

for(int i = 0; i < 10; i++)
{
    Console.WriteLine($"i: {i}");
}


arrays

int[] numbers = [1, 2, 3, 4, 5];

for(int i = 0; i < nums.Length; i++)
{
    int number = numbers[i];
    Console.WriteLine($"number: {number}");
}

arrays suck in csharp
you cant change array length
arrays arent really used in csharp
lists are used instead


lists


List<string> fruits = new List<string>();

fruits.Add("Apple"); <- arr.push('Apple')
fruits.Add("Banana");
fruits.Add("Pear");


foreach(string fruit in fruits)
{
    Console.WriteLine(fruit); returns Apple Banana Pear
}

fruits.forEach(fruit => Console.WriteLine(fruit));



csharp projects should be named camel case or with _ so it doesn't break don't use dashes -

appsettings.Development.json acts as .env file

namespace acts as export
using acts as import
namespace csharp_cats_api.Models;
exports all of your files in the models folder
using csharp_cats_api.Models;
global.cs has multiple using calls so most things are exported automatically

access modifier
public class Cat
{
    public int Id {get; set;}
    public string Name {get; set;}
    public int Age { get; set; }
    public bool LikesCheese { get; set; }
    public string Color { get; set; }
    public DateTime Birthday { get; set } = DateTime.Now
    public int NumberOfLegs { get; set; }
}

constructor
public Cat(int id, string name, int age, bool likesCheese, string color, int numberOfLegs, DateTime birthday)
{
    Id = id;
Name = name;
Age = age;
LikesCheese = likesCheese;
Color = color;
NumberOfLegs = numberOfLegs;
Birthday = birthday;
}

Cat cat = new Cat("Gopher", 17)

use the new c# apicontroller extension to make controller
[ApiController]
[Route("api/[controller]")]
public class CatsController : ControllerBase
{

private readonly CatsService _catsService;

CatsController(CatsService catsService)
{
_catsService = catsService;
}

    [HttpGet]
    public method that returns a list of cats
    public ActionResult<List<Cat>> GetCats()
    {
        try
        {
            List<Cat> cats = _catsService.GetCats()
            return Ok(cats);
        }
        catch(Exception error)
        {
            return BadRequest(error.Message);
        }
    }

    [HttpGet("{catId}")]
    public ActionResult<Cat> GetCatById(int catId)
    {
        try
        {
            Cat cat = _catsService.GetCatById(catId);
            return Ok(cat);
        }
        catch (Exception error)
        {
            return BadRequest(error.Message);
        }
    }

    [HttpPost]
    public ActionResult<Cat> CreateCat([FromBody] Cat catData)
    {
        try
        {
            Cat cat = _catsService.CreateCat(catData);
            return Ok(cat)
        }
        catch (Exception e)
        {
        return BadRequest(e.Message)
        }
    }
}

services.AddScoped<CatsService>(); <-in startup file

public class CatsService
{

    private readonly CatsRepository _catsRepository; <-control period to make constructor

    public CatsService(CatsRepository catsRepository)
        {
        _catsRepository = catsRepository;
        }

    internal List<Cat> GetCats()
        {
        List<Cat> cats = _catsRepository.GetCats();
        return cats;
        }

    internal Cat GetCatById(int catId)
        {
        Cat cat = _catsRepository.GetCatById(catId);
        if(cat == null)
            {
                throw new Exception($"Invalid id: {catId}");
            }
        return cat;
    }   

    internal Cat CreateCat(Cat catData)
    {
        Cat cat = _catsRepository.CreateCat(catData);
        return cat;
    }
}

public class CatsRepository
{
    private List<Cat> _cats;

    public CatsRepository()
        {
            _cats = [
                new Cat(1, "Gopher", 3, true, "Black", 4),
                new Cat(2, "Squishy", 5, true, "Gray", 4),
                new Cat(3, "Blake", 34, false, "Green", 2)
            ];
        }
        internal List<Cat> GetCats()
        {
            return _cats;
        }
        internal Cat GetCatById(int catId)
        {
            Cat foundCat = _cats.Find(cat => cat.Id == catId);
            return foundCat;
        }
        internal Cat CreateCat(Cat catData)
        {
            Cat lastCat = _cats[_cats.Count - 1];
            if(lastCat == null)
            {
                catData.Id = i;
            }
            else
            {
                catData.Id = lastCat.Id + 1;
            }
            _cats.Add(catData);
            return catData;
        }
}



