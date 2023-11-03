# Managing the Fullstack Application

1. Describe the two ways to bind Data in Vue?

  > | v-model="editable.name" binds whatever input tag your on to your editable
  : <----example ↓
   :disabled="boolean" will bind disabled to the boolean, only showing the button as disabled if the bool is true |

2. The `SPA` acronym stands for what?

  > | single page application |

3. What are some of the advantages/uses of a `SPA` over a traditional one?

  > | it is more responsive, faster to develop and better for smaller applications |

4. What does the `onMounted` method in Vue do?

  > | It runs whatever code you give it when the page its on loads |

5. What is the `v-model` attribute in Vue for, and when might you use it?

  > | the v-model is used to create a two way data binding, i last used it on my forms to make an editable get my form data from an input field  |

6. What is the package.json file used for?

  > | holds information about your project like the version or your dependencies, it also allows your project to be easily sharable cause people can install those dependencies with this file   |

7. Which Vue attributes(directives) could you use to conditionally render elements on a page?

  > | v-if  |

8. What is the purpose of the `key` attribute when using `v-for` on an element?

  > | the v-for uses the key to know which element is on in the array, which is why the key needs to be unique|

9. What is the `<slot>` element and what is it used for?

  > | a slot element allows you to pass content from a parent to a component(and if im understanding this right, this is really cool). Example 
<!-- inside component -->
<div>
<p>this is awesome</p>
<slot></slot>
</div>
<!-- parent code  -->
  <component>
  <p>'text'</p>
</component>

return:
this is awesome
text