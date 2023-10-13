# Understanding Asynchronous Code, and API's
01. What is the difference between `asynchronous` code and `synchronous` code?

  > | asynchronous code waits for a promise to be resolved or rejected before continuing to run, synchronous code runs even if a promise is pending |

02. What is an event listener?

  > | a event listener is set up to watch when a event occurs or a value gets reassigned on the thing its watching, and when this occurs it runs whatever function you set it to run  |

03. What does *REST* stand for, and in simple terms what does it mean??

  > |rest stands for representational state transfer. It means when an api is called you have to request a specific resource and the api will give you the state of that resource which is just the information on it. An example is requesting a specific user and the api returning all the information on that user that it has stored on it.  |

04. What is a callback / higher order function?

  > | a callback function is a function that takes time to produce a result instead of immediately returning something  |

05. What is a `promise`? How do you capture an error from a `promise`?

  > | similar to a promise in real life, our code saying it will do something in the future with two outcomes its either resolved or rejected. You can catch an error from a promise using a try catch, if the promise gets rejected the catch will go off |

06. Name three processes used to make requests over `HTTP`?

  > | post, get, put, delete (crud) |

07. What does the `API` acronym stand for?

  > | application programming interface  |

08. What must you do in order to `await` a promise inside of a function?

  > | async the function |

09. What is the purpose of encapsulation in programming?

  > | encapsulation is important because it restricts user access to important variables or functions, such as a banking app wouldnt want a user to be able to call the function that adds money to their account if they dont have money to add |

10. What is `HTTP` response code for a successful request?

  > | 200 |

11. What is a 400 error?

  > | bad request, server cant process a request because something on the client side is wrong  |
