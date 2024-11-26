# **Go Fiber CRM**
A lightweight CRM system built using the Go Fiber framework. This project provides a simple RESTful API to manage leads, leveraging SQLite for data storage and offering a practical demonstration of the Go Fiber framework's features.

![Review](https://github.com/MikeOnBoard/go-fiber-crm/blob/master/image-source/go-fiber-crm-preview.JPG)

## **Project Structure**
````graphql
go-fiber-crm/
├── database/
│   └── database.go      # Manages database connection and initialization
├── image-source/
│   └── preview.png      # Preview image for the project UI in Bruno REST client
├── lead/
│   └── lead.go          # Lead struct and CRUD operations
├── README.md            # Project documentation
├── go.mod               # Go module definition
├── go.sum               # Dependency checksums
├── leads.db             # SQLite database file
└── main.go              # Entry point of the application
````
## **Requirements**
- Go 1.18+
- SQLite (no external installation needed, bundled with Go)
- Fiber v2 framework
## **Installation and Setup**
1. Clone the repository:

````bash
git clone https://github.com/MikeOnBoard/go-fiber-crm.git
cd go-fiber-crm
````
2. Install dependencies:

````bash
go mod tidy
````
3. Run the application:

````bash
go run main.go
````
API will be accessible at: http://localhost:3000

## **API Endpoints**
The application provides the following endpoints for managing leads:

````
Method	    Endpoint	        Description
GET	        /api/leads	        Get all leads
GET	        /api/leads/:id	    Get a specific lead by ID
POST	    /api/leads	        Create a new lead
DELETE	    /api/leads/:id	    Delete a lead
````
## **Files Overview**
### ``main.go``
The entry point of the application. It initializes the Fiber app, sets up routes, and starts the server.

### ``database/database.go``
Handles the SQLite database connection and schema initialization. It ensures that the leads.db file is created and ready for CRUD operations.

### ``lead/lead.go``
Defines the Lead struct and contains logic for interacting with the database, including creating, retrieving, and deleting leads.

### ``image-source/preview.png``
A visual preview of the API responses rendered in the Bruno REST client.

### ``leads.db``
The SQLite database file used for storing lead information.

## **Example Usage**
### **Creating a New Lead**
Request:

````http
POST /api/leads
Content-Type: application/json

{
  "name": "John Doe",
  "email": "john.doe@example.com",
  "phone": "+123456789"
}
````
Response:

````json
{
  "id": 1,
  "name": "John Doe",
  "email": "john.doe@example.com",
  "phone": "+123456789"
}
````
### **Getting All Leads**
Request:

````http
GET /api/leads
````
Response:

````json
[
  {
    "id": 1,
    "name": "John Doe",
    "email": "john.doe@example.com",
    "phone": "+123456789"
  }
]
````
### **Deleting a Lead**
Request:

````http
DELETE /api/leads/1
````
Response:

````json
{
  "message": "Lead deleted successfully"
}
````
## **Preview**
Check the image-source/preview.png file for a visual representation of how the API is interacted with in the Bruno REST client.

## **Conclusion**
This project demonstrates a simple and effective way to build RESTful APIs using the Go Fiber framework. It includes database integration, routing, and CRUD operations, making it a great starting point for learning or building small-scale projects. The modular structure ensures the code is clean and maintainable. Contributions are welcome!