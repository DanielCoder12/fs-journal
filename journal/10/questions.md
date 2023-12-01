# CSharp and SQL Fundamentals
01. What is the purpose of a `namespace`?

  > | namespace acts in the same way export does, allowing other files to use code in that file |

02. What is the difference between a `class` and an `interface`?

  > | a class has definition and implementation and an interface only has implementation.
   |

03. What is the method that returns an instance of a class, yet it has no return type?

  > | void |

05. In the Car example what is the access modifier of the `Start()` method?

  ```c#
  abstract class Car
  {
    public string Start()
    {

      return "Vroooom";

    }
  }
  ```

  > | public |

06. In the Car example what is `string` an indication of?

  > | the start functions return type |

07. In the Car example what is `abstract` preventing?

  > | it makes it so the car class cannot be inherited |

08. In a SQL table, what is the difference between information in a row and information in a column?

  > | a column is all the information that can be on that be on that table, a row is what information a piece of data has on it|

09. Demonstrate the necessary SQL for creating a table called `characters` with the values `name, age, description` as strings, and an `int` id.

  > | CREATE TABLE IF NOT EXISTS characters(
      id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
      name VARCHAR(50) NOT NULL,
      age VARCHAR(50) NOT NULL,
      description VARCHAR(500) NOT NULL
  ) default charset utf8 COMMENT '';
  |

10. In SQL how can you query more than a single table? Provide an example.

  > | sql statement:
  SELECT 
  car.*,
  acc.*
  FROM cars car
  JOIN accounts acc ON acc.id = car.creatorId
  WHERE
  car.id = 1;

  c# datebase query:

  carId = 2
  string sql = @"SELECT 
  car.*,
  acc.*
  FROM cars car
  JOIN accounts acc ON acc.id = car.creatorId
  WHERE
  car.id = @carId;";
  
  Car car = _db.Query<Car, Account, Car>(sql, (car, acc)=>{car.creator = acc; return car;} , new{carId}).FirstOrDefault();
    |
