# Intro to JavaScript
01. Which keywords are used to declare a variable in JavaScript?

    > | let const var |

02. What is the definition of a function?

    > | a subprogram designed to perform a particular task |

03. What are the `SOLID` principles?

    > |Single Responsibility a class should only have one job
    open-closed principle things should be open for extension but not modification
    liskov substitution principle objects in a superclass should be replaceable with objects of subclasses without breaking anything
    interface segregation principle clients shouldnt be forced to depend on methods they dont use 
    dependancy inversion principle high level modules should not depend on low level modules, both should depend on abstractions |

04. Given this array: How could you remove the `pineapple`?

    ```js
    let fruit = ['apple', 'banana', 'pineapple', 'orange', 'strawberry']
    ```

    > | fruit = fruit.filter(fru => fru !== 'pineapple')
    you filter through the fruit array for every string that is not equal to pineapple, you set fruit equal to this new string so it no longer includes pineapple|

05. Given these two objects: How could you add each to the others friends arrays?

    ```js
    let you = {
        name: "You",
        hair: true,
        friends: []
    }
    let them = {
        name: "Them",
        hair: false,
        friends: []
    }
    ```

    > | you.friends.push(them) this will insert the them object into the you friends array
    them.friends.push(you) this will insert the you object into the them friends array|

06. Give an example of a JavaScript `Conditional`:

    > | if() |

07. What is the main difference between `parameters` and `arguments`?

    > | parameters are the names that represent the given argument. arguments are the values that the functions receive |

08. Instead of writing everything to the console, what is a better way to debug your code?

    > | using breakpoints and the javascript debugging pane in the chrome developer tools  |

09. What is the difference between a `primitive` value and a `reference` value?

    > | primitive value is a value thats stored directly in a variable such as a boolean a reference value is a value that you have to reference something to access such as an object, array and functionx` |

10. Demonstrate a loop that prints the numbers between -100 and 100?

    > |  for (let i = -100; i <= 100; i++) {
        console.log('console.log', i)
    }|
