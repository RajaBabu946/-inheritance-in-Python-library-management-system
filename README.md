# -inheritance-in-Python-library-management-system
Certainly! Here's another practice question on inheritance in Python:

Practice Question:

You are developing a program for a library management system. Implement a class hierarchy to represent different types of items that can be borrowed from the library.

Your program should have a base class `LibraryItem` with the following attributes and methods:
- Attributes:
  - `title` (string): representing the title of the item.
  - `barcode` (string): representing the unique barcode of the item.
- Methods:
  - `__init__(self, title, barcode)`: constructor to initialize the attributes.
  - `display_info(self)`: method to display the information of the item (title and barcode).

Define two subclasses of `LibraryItem`: `Book` and `DVD`.
- `Book` should have an additional attribute `author` (string) and a method `display_info` that overrides the method from the base class to include the author's name.
- `DVD` should have an additional attribute `director` (string) and a method `display_info` that overrides the method from the base class to include the director's name.

Create instances of `Book` and `DVD`, and demonstrate polymorphism by calling the `display_info` method for each instance.

Solution:

```python
class LibraryItem:
    def __init__(self, title, barcode):
        self.title = title
        self.barcode = barcode
    
    def display_info(self):
        print(f"Title: {self.title}, Barcode: {self.barcode}")

class Book(LibraryItem):
    def __init__(self, title, barcode, author):
        super().__init__(title, barcode)
        self.author = author
    
    def display_info(self):
        super().display_info()
        print(f"Author: {self.author}")

class DVD(LibraryItem):
    def __init__(self, title, barcode, director):
        super().__init__(title, barcode)
        self.director = director
    
    def display_info(self):
        super().display_info()
        print(f"Director: {self.director}")

# Create instances
book1 = Book("The Great Gatsby", "B1234", "F. Scott Fitzgerald")
dvd1 = DVD("Inception", "D5678", "Christopher Nolan")

# Demonstrate polymorphism
book1.display_info()
dvd1.display_info()
```

Explanation:

- The `LibraryItem` class is defined with attributes `title` and `barcode`, along with a method `display_info` to print out the information of the item.
- The `Book` class and `DVD` class inherit from the `LibraryItem` class using the syntax `class Book(LibraryItem)` and `class DVD(LibraryItem)`, respectively.
- Each subclass has its own `__init__` method to initialize additional attributes (`author` for `Book` and `director` for `DVD`), and they call the superclass's `__init__` method using `super().__init__(...)` to initialize inherited attributes.
- Each subclass also overrides the `display_info` method from the base class to include additional information specific to that type of item.
- Instances of `Book` and `DVD` are created (`book1` and `dvd1`), and the `display_info` method is called for each instance to demonstrate polymorphism.
