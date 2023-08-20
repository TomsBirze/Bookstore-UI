# Bookstore frontend useing Vite

Vue.js Bookstore Application
This is a simple Vue.js application that allows you to view a list of books and add new books to the bookstore. It communicates with a backend server to fetch the list of books and add new books.

Installation
Before running the application, make sure you have the following prerequisites:

Node.js and npm installed on your machine.
A running backend server that exposes the required API endpoints.
Follow these steps to set up and run the application:

1. Clone this repository to your local machine:   ```git@github.com:TomsBirze/Bookstore-UI.git```

2. Navigate to the project directory: ```cd  Bookstore-UI```

3. Install the project dependencies: ```npm install```

4. Configure the Backend API: https://github.com/TomsBirze/Bookstore

5. Start the development server: ```npm run dev```

6. Open your web browser and access the application at [http://localhost:5173](http://localhost:5173/).

#   Usage
# Adding a Book
Navigate to the "Add a Book" section on the application's homepage.

Fill in the title of the book in the input field.

Click the "Add Book" button.

This will send a PUT request to the backend server to add the book to the bookstore.
# Viewing Book List
The list of books is displayed in the "Book List" section on the homepage. Books are fetched from the backend server and displayed as a list.
