# Client – Server Architecture

## What is a Client?
A **client** is a device or software application that requests data or services from a server over a network (internet or private network).

In web development, clients are usually applications that users interact with directly.

### Common Client Examples
- Web browsers (Google Chrome, Mozilla Firefox, Microsoft Edge)
- Mobile applications (Android, iOS apps)
- Desktop applications
- Command Line Interface (CLI) tools
- IoT devices

The client is responsible for:
- Sending requests to the server
- Displaying or using the response
- Handling user interactions (UI/UX)

---

## Types of Clients
- Web Browser
- Mobile App
- Desktop Application
- CLI Tools
- Embedded / IoT Clients

---

## What is a Server?
A **server** is a device or software program that receives requests from clients and responds by providing data, resources, or services.

In web development, servers handle:
- Business logic
- Data processing
- Authentication and authorization
- Communication with databases

---

## Types of Servers

### File Server
- Stores and delivers files
- Used for downloads and static assets
- Examples: FTP servers, CDN file servers

Use case:
- Software downloads
- Media file access

---

### Database Server (DBMS)
- Stores, retrieves, and manages data
- Works using queries
- Examples: MySQL, PostgreSQL, MongoDB

Use case:
- User data storage
- Product records
- Transaction data

---

### Web Server
- Handles HTTP requests
- Serves static content or forwards requests
- Examples: Apache, Nginx

Use case:
- Hosting websites
- Serving HTML, CSS, JS
- Handling client requests

---

### Application Server
- Contains business logic
- Processes client requests
- Often communicates directly with a database
- Exposes APIs (REST, GraphQL)

Examples:
- Node.js
- Spring Boot
- Django

Use case:
- User authentication
- Payment processing
- API-based applications

---

## Client vs Server – Responsibilities

### Client Use Cases
- Requesting web pages
- Sending form data
- Displaying UI
- Consuming APIs
- Handling user input

---

### Server Use Cases
- Processing requests
- Managing databases
- Applying business rules
- Authenticating users
- Sending responses to clients

---

## Client–Server Interaction Flow

1. Client sends a request (HTTP/HTTPS)
2. Server receives the request
3. Server processes logic and data
4. Server sends a response
5. Client displays or processes the response

---

## Summary
- Client requests services
- Server provides services
- Clients focus on user interaction
- Servers focus on logic, data, and security
- Together they form the backbone of modern web applications
