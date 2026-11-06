# Week 11: Web Services (Core)

Course: BS Information Technology – Web Technologies

Topics:
- Introduction to Web Services
- SOAP vs REST
- WSDL (Conceptual)
- API Fundamentals
- HTTP Methods and Status Codes

## 1. Learning Outcomes

By the end of this lecture, students should be able to:

1. Explain the concept and importance of Web Services.
2. Understand how applications communicate over the Internet.
3. Differentiate between SOAP and REST.
4. Explain the purpose of WSDL.
5. Understand APIs and API endpoints.
6. Identify common HTTP methods and response codes.
7. Understand how modern web applications consume APIs.

# Part 1: Introduction to Web Services

## 2. What are Web Services?

Consider the following situations:

- A university website displays examination results retrieved from a university database.
- A weather application displays current weather information.
- An online shopping website retrieves product information from another server.
- A banking application communicates with a payment gateway to process transactions.

In these situations, two different software applications communicate with each other over a network.

A Web Service is a software component that allows two applications to communicate and exchange data over a network, typically using web technologies.

In simple words:

A Web Service allows one software application to use the functionality or data provided by another software application.

### 2.1 Traditional Web Application vs Web Service

Consider a traditional website.

A user opens a university website:

1. The browser sends a request to the web server.
2. The server retrieves information from its database.
3. The server generates an HTML page.
4. The browser displays the page.

Now consider a university application that needs examination results from another university system.

Instead of requesting a complete HTML page, the application requests only the required data.

The server might respond with:

{
    "roll_no": "BSCS-101",
    "name": "Ali",
    "marks": 85,
    "grade": "A"
}

The receiving application can process this data and display it in its own interface.

This is one of the common applications of Web Services.

### 2.2 Basic Architecture of a Web Service

A typical Web Service involves three components:

| Component | Description |
|---|---|
| Service Provider | Application that provides data or functionality. |
| Service Consumer | Application that requests the service. |
| Network | Communication medium connecting both applications. |

Example:

       Service Consumer
       (University Website)
               |
          HTTP Request
               |
               v
        Service Provider
        (Result Server)
               |
          Database Query
               |
               v
            Database
               |
          JSON Response
               |
               v
       Service Consumer

The consumer does not need direct access to the provider's database.

It communicates through an agreed interface.

### 2.3 Why Do We Need Web Services?

Web Services provide several benefits:

1. Interoperability: Applications developed using different programming languages can communicate.
2. Reusability: A service can be used by multiple applications.
3. Integration: Different software systems can exchange information.
4. Separation of concerns: The service provider manages its internal implementation, while consumers use its exposed functionality.
5. Scalability: Services can be developed, maintained and deployed independently.

For example, a university might develop its examination system in Java, its student portal in PHP and its mobile application in Kotlin.

All three applications can retrieve examination results through the same Web Service.

# Part 2: SOAP vs REST

## 3. Understanding SOAP

SOAP stands for Simple Object Access Protocol (historically).

SOAP is a messaging protocol used for exchanging structured information between applications.

It uses XML to represent messages.

SOAP defines a standard structure for messages and rules for processing them.

### 3.1 How SOAP Works

Suppose a banking application wants to retrieve the balance of a particular account.

It sends a SOAP message to the banking server.

A simplified SOAP request looks like this:

<?xml version="1.0"?>

<soap:Envelope
    xmlns:soap="http://www.w3.org/2003/05/soap-envelope">

    <soap:Body>

        <GetAccountBalance>
            <AccountNumber>123456</AccountNumber>
        </GetAccountBalance>

    </soap:Body>

</soap:Envelope>

The server processes the request and returns another SOAP message.

Simplified response:

<soap:Envelope
    xmlns:soap="http://www.w3.org/2003/05/soap-envelope">

    <soap:Body>

        <GetAccountBalanceResponse>
            <Balance>50000</Balance>
        </GetAccountBalanceResponse>

    </soap:Body>

</soap:Envelope>

Notice that SOAP messages have a defined XML structure.

### 3.2 Important Characteristics of SOAP

- SOAP is a protocol.
- It uses XML-based message structures.
- It defines an envelope and message-processing rules.
- It can work over different underlying transport protocols.
- It is commonly used with HTTP.
- It supports extensions for enterprise requirements, including security and reliable messaging.

SOAP is frequently encountered in enterprise systems, banking integrations and legacy software environments.

## 4. Understanding REST

REST stands for Representational State Transfer.

REST is an architectural style for designing network-based applications.

Unlike SOAP, REST is not a messaging protocol.

REST commonly uses HTTP methods to perform operations on resources.

### 4.1 Understanding Resources

In REST, information is represented as resources.

For example, consider a university management system.

Its resources might include:

- Students
- Teachers
- Courses
- Departments
- Examination Results

Each resource can be identified using a URL.

For example:

https://university.edu/api/students

This URL represents the collection of students.

Similarly:

https://university.edu/api/students/101

This URL represents a particular student.

These URLs are called API Endpoints.

### 4.2 HTTP Methods in REST

REST commonly uses HTTP methods to perform operations on resources.

| HTTP Method | Purpose | Example |
|---|---|---|
| GET | Retrieve information | Get student details |
| POST | Create a new resource | Add a student |
| PUT | Replace/update a resource | Update student record |
| PATCH | Partially update a resource | Change student email |
| DELETE | Remove a resource | Delete student record |

Consider the following API endpoints:

| Request | Operation |
|---|---|
| GET /students | Retrieve all students |
| GET /students/101 | Retrieve student 101 |
| POST /students | Add a new student |
| PUT /students/101 | Replace student 101 |
| DELETE /students/101 | Delete student 101 |

The same endpoint can support different operations depending on the HTTP method.

### 4.3 Data Formats in REST

REST does not require JSON.

It can work with different representations, including:

- JSON
- XML
- HTML
- Plain text

However, JSON is particularly common in modern Web APIs.

Example JSON response:

{
    "id": 101,
    "name": "Ali Ahmed",
    "department": "Computer Science",
    "semester": 5
}

JSON is relatively lightweight and can easily be processed using JavaScript.

### 4.4 Important Characteristics of REST

1. Client-Server Architecture: Client and server have separate responsibilities.
2. Statelessness: Each request contains the information necessary for the server to process it. The server does not rely on stored client-request context between requests.
3. Resource-Based: Resources are identified through URLs.
4. Uniform Interface: Standard methods and conventions are used for interaction.
5. Representations: Resources can be represented in formats such as JSON and XML.
6. Cacheability: Responses can be designed to support caching.

## 5. SOAP vs REST: Comparison

| Feature | SOAP | REST |
|---|---|---|
| Nature | Messaging protocol | Architectural style |
| Data format | XML-based messages | JSON, XML and others |
| Communication | Uses defined SOAP messaging rules | Commonly uses HTTP methods |
| Message structure | Standardized envelope | No mandatory envelope |
| Complexity | Generally more complex | Generally simpler |
| Performance | XML messages can introduce overhead | Often lightweight, especially with JSON |
| Security | Supports WS-Security extensions | Commonly uses HTTPS, tokens and other security mechanisms |
| Operations | Defined through message and service contracts | Commonly represented through HTTP methods |
| Typical applications | Enterprise and legacy integrations | Web and mobile application APIs |

### An Important Concept

SOAP and REST are not exactly equivalent alternatives.

SOAP is a protocol, whereas REST is an architectural style.

Also, REST does not mean JSON, and SOAP does not mean HTTP.

A RESTful API can return XML, while SOAP can use transport protocols other than HTTP.

### 5.1 Which One Is More Popular Today?

REST-based APIs are widely used in modern web and mobile application development.

For example:

- Mobile applications retrieve information through REST APIs.
- E-commerce websites communicate with payment services.
- Front-end applications retrieve data from back-end servers.
- Cloud platforms expose APIs for developers.

SOAP is still relevant in some enterprise environments, especially where existing systems depend on established SOAP-based integrations.

Teaching point:

SOAP has not disappeared. REST is widely adopted in modern web development, but both technologies continue to serve different requirements.

# Part 3: WSDL

## 6. What is WSDL?

WSDL stands for Web Services Description Language.

It is an XML-based language used to describe a Web Service.

Think of WSDL as a technical description or contract between a service provider and its consumer.

Suppose a bank provides a SOAP Web Service.

Before using it, a software developer needs to know:

- What operations are available?
- What parameters must be supplied?
- What data types are expected?
- What responses will be returned?
- Where is the service located?
- How should the application communicate with it?

WSDL provides this information in a machine-readable format.

### 6.1 Real-World Analogy

Imagine visiting a restaurant.

Before ordering, you need to know:

- What dishes are available?
- What ingredients or options can be selected?
- What are their prices?
- How do you place an order?

A restaurant menu provides this information.

Similarly, WSDL describes the available operations and communication requirements of a Web Service.

### 6.2 Main Components of WSDL

Conceptually, WSDL describes:

| Component | Purpose |
|---|---|
| Types | Defines data types used by the service |
| Messages | Defines the information exchanged |
| Operations | Defines available functions |
| Interface/PortType | Groups related operations |
| Binding | Defines communication details |
| Service | Identifies the service and its endpoint |

For example, a university service might expose the following operations:

University Service

Operations:

1. GetStudentDetails
2. GetExaminationResult
3. GetCourseInformation
4. GetDepartmentDetails

A WSDL document describes these operations and the rules for communicating with them.

### 6.3 Relationship Between SOAP and WSDL

SOAP and WSDL are often used together.

- SOAP defines how messages are structured and exchanged.
- WSDL describes the available service operations and how to communicate with them.

SOAP Web Service
       |
       |
   WSDL Description
       |
       |
   Service Consumer

Important:

WSDL is not compulsory for SOAP. However, it is commonly used to describe SOAP-based services.

WSDL can also describe services using other bindings.

# Part 4: Understanding APIs

## 7. What is an API?

API stands for Application Programming Interface.

An API is an interface that allows one software component to interact with another software component through a defined set of rules.

In simple words:

An API acts as a communication interface between two software applications.

### 7.1 Everyday Example

Consider a mobile weather application.

The application needs weather information for Quetta.

Instead of maintaining its own weather database, it communicates with a weather service.

       Weather Application
                |
           API Request
                |
                v
          Weather Service
                |
          Weather Database
                |
           API Response
                |
                v
       Weather Application

The weather application receives the response and displays the temperature, humidity and other information.

### 7.2 Types of APIs

APIs can be classified in different ways.

Some common categories include:

| API Type | Description |
|---|---|
| Web APIs | Allow applications to communicate over a network |
| Library APIs | Provide functions and classes for software developers |
| Operating System APIs | Allow applications to interact with operating system services |
| Database APIs | Allow applications to communicate with databases |

For this course, our primary focus is Web APIs.

### 7.3 Common API Terminology

| Term | Meaning |
|---|---|
| API | Interface for software communication |
| Endpoint | Specific URL through which an API operation is accessed |
| Request | Message sent by the client |
| Response | Message returned by the server |
| API Key | Credential used to identify or authorize an application |
| JSON | Common data format used by APIs |
| Authentication | Verifying the identity of a user or application |
| Authorization | Determining what an authenticated user or application can access |

### 7.4 HTTP Status Codes

When an API receives a request, it returns an HTTP status code.

Some important status codes are:

| Status Code | Meaning |
|---|---|
| 200 | OK - Request successful |
| 201 | Created - Resource created successfully |
| 400 | Bad Request |
| 401 | Unauthorized - Authentication required or invalid |
| 403 | Forbidden - Access not permitted |
| 404 | Not Found |
| 500 | Internal Server Error |

For example:

If a client requests:

GET /api/students/101

The server might respond with:

200 OK

If student 101 does not exist, the server might respond with:

404 Not Found

# Part 5: Important Concepts and Discussion

## 8. What Happens When We Use an API?

Consider the following example:

A student opens a university webpage that displays examination results.

The webpage contains HTML, CSS and JavaScript.

JavaScript sends a request to the university's result API.

The API communicates with the university's back-end system and retrieves the result.

The server returns JSON data.

JavaScript processes the response and updates the webpage.

The entire process takes place without necessarily reloading the complete webpage.

This is one of the fundamental concepts behind modern interactive web applications.

## 9. Are Web Services and APIs the Same?

These terms are related but not identical.

An API is a general interface through which software components communicate.

A Web Service is a service made available over a network, typically using web technologies.

Most Web Services expose APIs, but not every API is a Web Service.

For example, a programming language's built-in library API does not necessarily communicate over a network.

## 10. Are REST APIs Replacing Traditional Web Development?

No.

REST APIs complement traditional web development.

Modern web applications frequently separate their architecture into two major components:

Front End:
- HTML
- CSS
- JavaScript
- User Interface

Back End:
- Application logic
- Database operations
- Authentication
- API endpoints

The front end communicates with the back end through APIs.

          FRONT END
        HTML, CSS, JS
               |
               |
            REST API
               |
               |
           BACK END
        Business Logic
               |
               |
            DATABASE

This architecture also allows the same back end to serve different clients, such as:

- Desktop browsers
- Mobile applications
- Third-party applications

# 11. Summary

| Concept | Key Point |
|---|---|
| Web Service | Allows applications to communicate over a network |
| SOAP | XML-based messaging protocol |
| REST | Architectural style for network-based applications |
| WSDL | XML-based description of Web Services |
| API | Interface for software communication |
| Endpoint | URL identifying an API resource or operation |
| HTTP GET | Retrieves information |
| HTTP POST | Creates or submits information |
| JSON | Common data exchange format |
| Fetch API | JavaScript interface for making network requests |
| Promise | Represents an asynchronous operation |

# 12. Review Questions

1. What is a Web Service? Explain with an example.
2. Differentiate between a traditional web application and a Web Service.
3. What is SOAP? Explain its important characteristics.
4. What is REST? Why is it widely used in modern web development?
5. Differentiate between SOAP and REST.
6. What is WSDL? Why is it important?
7. What is an API? Explain the concept of an API endpoint.
8. Differentiate between HTTP GET and POST.
9. What is JSON? Why is it commonly used in REST APIs?
10. What is the purpose of HTTP status code 404?
11. Are Web Services and APIs exactly the same?
12. How do REST APIs support modern web application development?

# 13. Suggested Learning Resources

1. MDN – Fetch API:
   https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API

2. MDN – Using the Fetch API:
   https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch

3. MDN – HTTP Overview:
   https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview

4. W3C – SOAP 1.2 Specification:
   https://www.w3.org/TR/soap12/

5. W3C – WSDL 2.0 Specification:
   https://www.w3.org/TR/wsdl20/

6. JSONPlaceholder – Practice REST API:
   https://jsonplaceholder.typicode.com/

# Instructor's Teaching Note

Give particular attention to three distinctions:

1. SOAP is a protocol; REST is an architectural style.
2. WSDL describes a service; SOAP defines a messaging framework.
3. An API is an interface, whereas a Web Service is a network-accessible service.

For the practical session, spend more time on Fetch API, JSON, HTTP requests and responses than on writing SOAP XML messages.

Students should leave the lecture understanding that applications can retrieve information from external servers and dynamically incorporate it into their own webpages.

This is an important foundation for their subsequent study of full-stack development, mobile application development and distributed systems.
