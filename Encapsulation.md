# Encapsulation

- Encapsulation means hiding information or data. 

- It refers to the ability of the object to execute its functionality without revealing any execution details to the caller. 

- In other words, the private variable is only visible to the current function and is not accessible to the global scope or other functions.

```
const Book = function(t, a) {
   let title = t; 
   let author = a; 
   
   return {
      summary : function() { 
        console.log(`${title} written by ${author}.`);
      } 
   }
}
const book1 = new Book('Hippie', 'Paulo Coelho');
book1.summary();
> Hippie written by Paulo Coelho.

```
- In the above code the title and the author are only visible inside the scope of the function Book and 
the method summary is visible to the caller of Book. So the title and the author are encapsulated inside Book.
