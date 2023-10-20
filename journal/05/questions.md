# Intro to Server side concerns with JavaScript
01. What do the letters of the acronym `CRUD` stand for?

  > | create read update destroy |

02. Each action that `CRUD` represents maps to an HTTP request. What HTTP request does each `CRUD` action correspond to?

  > | post get put delete |

03. What does `ORM` stand for? Which `ORM` do we use when interacting with MongoDB

  > | object related mapping, mongoose  |

04. Which two `HTTP` request types include a body?

  > | post and put |

05. In a/an _______ coding model, when you call a function, it returns only when the action has finished and stops your program for the time the action takes. Likewise in a/an _______ coding model, multiple things are allowed to happen at one time. When you perform an action, your program continues to run.  Fill in the blanks.

  > | asynchronous, synchronous |

06. What are the three types of data relationships? Provide an example of each.

  > | one-to-one: both sides of a relationship only relate to each other and nothing else
  one to many: one side can have more than one relationship but to other side has only one relationship
  many to many: both sides of a relationship have many other relationships    |

07. What is middleware?

  > | something that allows you to interact with your database from your application, ex: mongoose  |

08. The ______ pipeline delivers information from the client while the ______ pipeline returns it. Fill in the blanks. 

  > | request, return |

09. Demonstrate the pattern that is used to include a request query with the client's `HTTP` request providing the property `tag` and the value `winter`.

  > | ?tag=winter  |

10. What is a ***virtual property***?

  > | something you can add to your mongoose schema that isn't stored in mongodb, can be used for things such as attaching data from your data's relationships when sending it back to the user  |
