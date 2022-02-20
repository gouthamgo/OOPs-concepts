# OOPs-concepts- JAVASCRIPT

```
Object, property, and methods
Class
Encapsulation
Abstraction
Reusability/inheritance
Polymorphism
Association
Aggregation
Composition

```

## Object, property, and method

Lets create an Object

```
const book={
    title: "Go Getter",    
   author: "Sam",  
   year: "2000"
}
```
- we can get the value of the title with book.title. We can also access the properties with square brackets: book[‘title’]

## Object constructor
- Object constructor is the same as a regular function
- It will be called each time an object is created. We can use them with the new keyword. Object constructor is useful when we want to create multiple objects with the same properties and methods.

```
function Book(title, author, year) { 
   this.title = title; 
   this.author = author; 
   this.year = year;
}
const book1 = new Book ('Hippie', 'Paulo Coelho', '2018');
console.log(book1);
> Book {
     title: "Hippie", 
     author: "Paulo Coelho", 
     year: "2018"
  }
// if we want to create more than one book just we call function book with new keyword.
const book2 = new Book ('The Alchemist', 'Paulo Coelho', '1988');
```


# Class
- Class is not an object — it is the blueprint of an object. Classes are special functions. You can define functions using function expressions and declarations and you can define classes that way as well. We can create the number of objects using the blueprint.
- You can use the class keyword and the name of the class. The syntax is similar to that of Java.
- Class syntax is a nice way to use object-oriented programming and managing prototypes:
```
let Book = function(name) { 
   this.name = name
}
let newBook = function(name) {
   Book.call(this, name)
} 
newBook.prototype = Object.create(Book.prototype);
const book1 = new newBook("The Alchemist");
```

- This is using ES6 class syntax:
```
class Book {
   constructor(name) {
      this.name = name
   }
}
class newBook extends Book { 
   constructor(name) {
      super(name);
   }
}

const book1 = new newBook("The Alchemist");
```

- Class syntax is syntactical sugar — behind the scenes, it still uses a prototype-based model. Classes are functions, and functions are objects in JavaScript.
```
class Book {
   constructor(title, author){ 
      this.title = title;
      this.author = author;
   } 
   summary() {
      console.log(`${this.title} written by ${this.author}`);
   }
}
const book1 = new Book("", "");
console.log(typeof Book); 
> "function"
console.log(typeof book1);
> "object"

```


So for wrting the class

```
class Countries {
constructor(gdp,population){
      this.gdp =gdp;
      this.population =population;
      }
      summary(){
      console.log(`${this.gdp} per${this.population}`);
      }
      }
      
      const country1 = new Countries("", "");
      
      Here---> country1 is object and COuntries is a fucntion
      
      ```
      
      goutham new uodate 
