# Reusability/Inheritance

- JavaScript inheritance is a mechanism allows us to create a new class using the existing class. 
- It means the child class inherits all the properties and behaviors of the parent class.
Generally, JavaScript is not a class-based language. 
- The keyword class was introduced in ES6 but is syntactical sugar, JavaScript remains prototype-based. 
- In JavaScript inheritance is achieved by using the prototype. This pattern is called Behavior Delegation Pattern or prototypal inheritance.
Let’s consider our book example:
```
function Book(title, author, year) { 
   this.title = title; 
   this.author = author; 
   this.year = year;
   this.summary = function() { 
      console.log(`${this.title} is written by ${this.author}.`)
   }
}
const book1 = new Book ('Hippie', 'Paulo Coelho', '2018');
const book2 = new Book ('The Alchemist', 'Paulo Coelho', '1988');
Prototypal inheritance
For each instance of Book, we’re recreating the memory for the methods from the base class. These methods must be shared across all instances — they should not be specific to the instance. Here the prototype comes into the picture:
let Corebook = function(title) {
  this.title = title
}
Corebook.prototype.title = function() {
  console.log(`name of the book is ${this.title}`);
}
Corebook.prototype.summary = function(author) {
  console.log(`${this.title} is written by ${this.author}`);
}
let Book = function(title, author) {
  Corebook.call(this, title, author)
}
Book.prototype = Object.create(Corebook.prototype);
let book1 = new Book('The Alchemist', 'Paulo Coelho');
book1.title();
> name of the book is The Alchemist
book1.summary();
> The Alchemist is written by Paulo Coelho

```
- In the above code, the instance of Book has a copy of the prototype, which is linked to the prototype of Book, which in turn links to the prototype of Corebook.
