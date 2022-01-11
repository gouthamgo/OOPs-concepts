# Abstraction

- Abstraction means implementation hiding.

- It is a way of hiding the implementation details and only showing the essential features to the caller. 


- In other words, it hides irrelevant details and shows only what’s necessary to the outer world. A lack of abstraction will lead to problems of code maintainability.

```
const Book = function(getTitle, getAuthor) { 
   // Private variables / properties  
   let title = getTitle; 
   let author = getAuthor;
// Public method 
   this.giveTitle = function() {
      return title;
   }
   
   // Private method
   const summary = function() {
      return `${title} written by ${author}.`
   }
// Public method that has access to private method.
   this.giveSummary = function() {
      return summary()
   } 
}
const book1 = new Book('Hippie', 'Paulo Coelho');
book1.giveTitle();
> "Hippie"
book1.summary();
> Uncaught TypeError: book1.summary is not a function
book1.giveSummary();
> "Hippie written by Paulo Coelho."
```
