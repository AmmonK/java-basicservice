### Getting Started

Check your maven version
```bash
mvn -v
```
Check your java version
```bash
java --version 
```
To run the project
```bash
mvn spring-boot:run
```

**Check the pom.xml for java version**

Url to access application: http://localhost:8080

Use [Postman](https://www.postman.com/downloads/) to easily keep track of requests

[Spring Initializr Settings](https://start.spring.io/#!type=maven-project&language=java&platformVersion=3.0.2&packaging=jar&jvmVersion=17&groupId=com.example&artifactId=basicservice&name=basicservice&description=Demo%20project%20for%20Spring%20Boot&packageName=com.example.basicservice&dependencies=devtools,web)

### Fork this repository to your own Github and create a branch for each exercise

---
## Exercises:

### Fruits API
**Goal**: Create an API that will allow basic crud operations to a list of fruits
* Create a FruitController in package com.example.basicservice.controllers
* Map to the url */fruit*
* Create an ArrayList to hold the fruits
* Create a handler for a **GET** request that will return the array of fruits
* Create a handler for a **POST** request that will take the name of a fruit as a parameter and add to the array
* Create a handler for a **GET** request that will take an index for a fruit in the array and return it
* Create a handler for a **DELETE** request that will take the index of a fruit in the array and remove it

**Bonus** Create a **POST** request that accepts the name of a fruit in the request body instead of the url

<details>
<summary>HINTS</summary>

```java
@RestController
@RequestMapping
@GetMapping
@PostMapping
@DeleteMapping
@PathVariable
```
</details>

### Adventurer API
**Goal** Create an API that will manage a list of adventurers
* Create an Adventurer model with the following characteristics
    * Name
    * Class
      * Example: Wizard, Barbarian, Ranger
    * Health
    * Mana
* Create an AdventurerController in package com.example.basicservice.controllers
* Create a handler for a **GET** request that will return the list of Adventurers
* Create a handler for a **GET** request that will return an Adventurer by index
* Create a handler for a **GET** request that will return an Adventurer by name
* Create a handler for a **POST** request that will accept an Adventurer as a post body and add to the list
* Create a handler for a **PUT** request that will modify the health for an Adventurer by their id

**Bonus** Create an additional handler for a **GET** request that will return all Adventurers with a given class

<details>
<summary>HINTS</summary>

```java
@GetMapping("{id}") int id
@GetMapping("{class}") String class
@PutMapping("{id}") int id, int health from body
```
</details>

### Thought Exercises
> What happens when you make a GET request for an id that does not exist in the Array, how should that be handled?

> Think of error boundaries
> * When finding an item make sure that you can find it first
> * When deleting an item, also make sure you can find it first
> * Shouldn't we do that with everything really?

> What would be the next progression for this?  Think about what it would take to manage the list of data in an external data source or utility.  How would that impact the existing exercises?


---
### References
* [ResponseEntity](https://www.baeldung.com/spring-response-entity)
* [Spring Docs](https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/)
* [Spring Annotations](https://www.baeldung.com/tag/spring-annotations)
* [Spring Guides](https://spring.io/guides#gettingStarted)
