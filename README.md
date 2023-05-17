# MongoDB CRUD Operations

This README provides an overview of the MongoDB CRUD operations performed by the given HTML code. The code demonstrates a basic web application interface for creating, reading, updating, and deleting records in a MongoDB database. The application allows users to manage books, including their name, registration number (RegNo), and class.

## Prerequisites

Before running the application, ensure that you have the following:

- MongoDB installed and running.
- A MongoDB database and collection set up for storing book records.
- A server environment capable of running the HTML code (e.g., Node.js with Express.js).

## Getting Started

To use the application, follow these steps:

1. Clone or download the HTML code provided.
2. Set up your server environment with the necessary dependencies and configurations.
3. Make sure you have established a connection with your MongoDB database.

## HTML Structure

The HTML code is a basic web interface for the CRUD operations on the book records. It consists of the following sections:

### Create

This section allows users to create new book records. It contains an HTML form that captures the book's name, registration number (RegNo), and class. Upon submitting the form, the data is sent to the `/store_values` endpoint for processing.

### Edit

When editing a book record, this section is displayed. It populates an HTML form with the existing values of the book to be edited. The form fields include the book's name, registration number (RegNo), and class. When the user submits the form, the updated data is sent to the `/update_values/{{edit_id}}` endpoint for processing.

### List

The list section displays all existing book records in an unordered list (ul) format. Each book entry includes the book's name, registration number (RegNo), class, and two hyperlinks: "Edit" and "Delete." The "Edit" link directs the user to the `/` endpoint with the `edit_id` query parameter, allowing them to edit the corresponding book record. The "Delete" link triggers a confirmation prompt before redirecting to the `/` endpoint with the `delete_id` query parameter to delete the book record.

## MongoDB CRUD Operations

The HTML code interacts with MongoDB through the following routes/endpoints:

- `/store_values`: Handles the creation of a new book record. It receives the data from the "Create" form and inserts a new document into the MongoDB collection.

- `/update_values/{{edit_id}}`: Updates an existing book record. It receives the updated data from the "Edit" form and modifies the corresponding document in the MongoDB collection based on the `edit_id` parameter.

- `/?edit_id={{this._id}}`: Triggers the display of the "Edit" section with pre-filled form fields for the selected book record. The `edit_id` query parameter identifies the specific book to be edited.

- `/?delete_id={{this._id}}`: Initiates the deletion of a book record. It prompts for confirmation and, if accepted, removes the corresponding document from the MongoDB collection. The `delete_id` query parameter specifies the book to be deleted.

## Conclusion

This README provides an overview of the HTML code's structure and its connection to MongoDB for CRUD operations on book records. To use this code, you will need to integrate it with a server environment capable of processing the endpoints and establish a connection with a MongoDB database. You can further customize and enhance the application based on your specific requirements and design preferences.
