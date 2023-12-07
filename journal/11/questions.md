# A bit more CSharp and SQL
1. What does ***inheritance*** accomplish for us in C#?

  > | It allows you to reuse and repurpose previous classes you have made |

2. How does ***member inheritance*** work in C#? Does a `Class` inherit all members of the base `Class`?

  > | a inheriting class only inherits members that are permitted by the classes accessability type
  ex: a class inheriting another class with a public and private function will only inherit the public function |

3. How does ***accessibility*** affect inheritance?

  > | private means the member is only visable to the class its in, public lets it extend to all other classes that inherit it |

4. What is the difference between a `PRIMARY KEY` and a `FOREIGN KEY`

  > | primary keys are unique identifiers in a table, foreign keys are used to link two tables together |

5. What is an ***alias***?

  > | used to give a sql table a temporary name, ex: accounts acc |

6. Demonstrate how you would query a join statement that would get all of a doctors patients from the following collections:

  ```SQL
  CREATE TABLE doctors (
    id INT NOT NULL AUTO_INCREMENT,
    -- CODE OMITTED
    PRIMARY KEY (id)
  )

  CREATE TABLE patients (
    id INT NOT NULL AUTO_INCREMENT,
    -- CODE OMITTED
    PRIMARY KEY (id)
  )

  CREATE TABLE patient_doctors (
    id INT NOT NULL AUTO_INCREMENT,
    doctorId INT NOT NULL,
    patientId INT NOT NULL,

    FOREIGN KEY (doctorId)
      REFERENCES doctors(id),
    FOREIGN KEY (patientId)
      REFERENCES patients(id),
  )

  ```

  > | 
  SELECT 
  patients.*
  patient_doctors.*,
  doctors.*,
  FROM patients
  LEFT JOIN patient_doctors ON patients.id = patient_doctors.patientId
  JOIN doctors ON doctors.id = patient_doctors.doctorId
  WHERE doctors.id = @doctorId
   |
