# Single Page Applications with Vue
01. What is the entrypoint of an application?

  > | main.js |

02. What is the difference between a vue `component` and `page`?

  > | Pages get injected through the router and are not reusable, components get injected into pages and can be used through multiple pages multiple time |

03. What is ***Component-Based Architecture***?

  > | encapsulating individual pieces of a larger ui into self sustaining micro systems. since these systems are independent one can refresh without affecting other components and the ui as a whole. |

04. What are the three tags that make up a Vue component?

  > | template, script, style  |

05. What are ***lifecycle hooks***? What are lifecycle hooks used for?

  > | code that will run given functions when a new stage of a components lifecycle is reached. An example is a onMounted get from api function only runs when the component is created like a constructor in a controller. A onUnMounted will run when a component stops being used etc |

06. Which component in Vue does the vue-router use to mount pages onto?

  > | router-view in the app.vue file  |

07. What is the difference between the `AppState` and the state object within a component?

  > | the AppState is globally accessible, the state object is only accessible within that component |

08. What is the responsibility of `Services` in our Vue projects?

  > | the service does all the business logic like changing variables in the AppState |

09. What are ***props*** and how are they used? Provide an example

  > | props are used to pass variables and other information between different components. An example is in gregslist making a car card component with a car prop and passing that to the car view so you can v-for and display every car |

10. What is the Vue method used to create watchable objects such as `state` or `AppState`?

  > | computed and watchEffect |
