# 📖 Minimalist Book Manager API

## Introduction
This is the starter repository for the Further APIs session. It provides a start to creating a Minimalist Book Manager API
using a Test-Driven Development approach.

### Pre-Requisites
- Java SE Development Kit 17
- Maven

### Technologies & Dependencies
- Spring Boot
- Spring Web
- H2 Database
- Lombok
- Spring Data JPA

### How to Get Started
- Fork this repo to your Github and then clone the forked version of this repo

### Main Entry Point
- The Main Entry Point for the application is: [BookmanagerApplication.java](src/main/java/com/techreturners/bookmanager/BookmanagerApplication.java)

### Running the Unit Tests
- You can run the unit tests in IntelliJ, or you can go to your terminal and inside the root of this directory, run:

`mvn test`

### Tasks

Here are some tasks for you to work on:

📘 Discussion Task

Explore the code and make notes on the following features and how it is being implemented in the code. We'd like you to note down what classes and methods are used and how the objects interact.

The features are:
- Get All Books : When User makes a GET request to /api/v1/book, the BookManagerController.getAllBooks() is called.
 FRom this method, bookManagerService.getAllBooks() is called. From this method,  bookManagerRepository.findAll() is called
 bookManagerRepository then call the Model Book to query the DB. DataBase returns the book information back to BookManagerRepository.
 bookManagerRepository returns the data to BookManagerService.
 BookManagerService then returns the information to BookManagerController.
 From BookManagerController, it then returns the response to the User.
- 
- Get a Book by ID : When User makes a GET request to /api/v1/book/id, the BookManagerController.getBookById(@PathVariable Long bookId)is called.
  FRom this method, bookManagerService.getBookById(Long id) is called. From this method, bookManagerRepository.findById(id) is called
  bookManagerRepository then call the Model Book to query the DB. DataBase returns the book information back to BookManagerRepository.
  bookManagerRepository returns the data to BookManagerService.
  BookManagerService then returns the information to BookManagerController.
  From BookManagerController, it then returns the response to the User.

  - Add a Book  : When User makes a POST request to /api/v1/book  with RequestBody book, BookManagerController.addBook(@RequestBody Book book) is called.
  From this method, bookManagerService.insertBook(Book book) is called. From this method, bookManagerRepository.save() is called,
  BookManagerRepository then calls the model Book to save the Book table.
 
  Database then returns the information to BookManagerRepository, From BookManagerRepository the response is given to BookManagerService.
  BookManagerService then returns the response to BookManagerController.
  From BookManagerController then returns the response to the User.

- Update a Book : When User makes a POST request to /api/v1/book with RequestBody book, 
 BookManagerController.updateBookById(@PathVariable("bookId") Long bookId, @RequestBody Book book) is called.
    From this method,BookManagerService.updateBookById(Long id, Book book) is called.
    from this method, bookManagerRepository.findbyId is called,BookManagerRepository then calls the

📘 Task 1: Implement the following User Story with tests.

`User Story: As a user, I want to use the Book Manager API to delete a book using its ID`


📘 Extension Task: Oh no! 😭 We've only covered the happy paths in the solution, can you figure out a way
to add in exception handling to the project? 

- Clue 1: What if someone wants to add a book with an ID for a book that already exists? How do we handle this gracefully?


- Clue 2: What if someone wants to find a book by an ID that doesn't yet exist? 
  How can we improve the API by handling errors gracefully and show a helpful message to the client?
  
