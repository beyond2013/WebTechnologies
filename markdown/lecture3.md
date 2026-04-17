# Lecture 3: Web Servers, Hosting & How Content is Delivered

---

## 1. Recap of Previous Lecture

In Lecture 2, we explored:

- DNS resolves domain names into IP addresses  
- TCP establishes a reliable connection  
- HTTP enables request–response communication  
- Browser DevTools can be used to inspect requests  

Now we move to the **server side of the web**.

---

## 2. What is a Web Server?

A **web server** is software (and hardware) that:

> Receives HTTP requests → Processes them → Sends HTTP responses

---

### Examples of Web Servers

- Apache  
- Nginx  
- Microsoft IIS  
- Puma (used by Ruby on Rails)  

---

### Key Idea

> A web server is always **listening** for incoming requests on a specific port (usually 80 or 443).

---

## 3. Static vs Dynamic Content

### Static Content

- Pre-built files  
- Same response for every user  

Examples:
- HTML files  
- CSS  
- Images  

---

### Dynamic Content

- Generated at runtime  
- Response depends on user/request  

Examples:
- Login systems  
- Dashboards  
- Search results  

---

### Conceptual Difference

    Client → Request → Server  
            → Static File → Response  

    Client → Request → Application Code → Database → Response  

---

## 4. Where Does Puma Fit?

When you run:

    rails server  

Puma acts as your **application server**.

---

### Flow in Rails

    Browser → HTTP Request → Puma  
    Puma → Rails Application Code  
    Rails → Generates Response  
    Puma → Sends HTTP Response  

---

### Important Distinction

- **Web Server (Nginx/Apache)** → Handles HTTP, static files  
- **Application Server (Puma)** → Runs your code  

---

## 5. Ports and Localhost

### What is a Port?

> A port is a communication endpoint on a machine

Examples:
- 80 → HTTP  
- 443 → HTTPS  
- 3000 → Development servers (Rails)

---

### Localhost

    localhost = 127.0.0.1  

This refers to:
> Your own machine

---

### Example

When you visit:

    http://localhost:3000  

You are:
- Sending request to your own computer  
- On port 3000  
- Where Puma is running  

---

## 6. Virtual Hosting (Conceptual)

One server can host multiple websites.

---

### How?

Using:
- Domain names  
- Server configuration  

---

### Example

    example.com → Site A  
    myblog.com → Site B  

Both can run on the same physical server.

---

## 7. Caching (Introduction)

Caching improves performance by storing responses.

---

### Types of Caching

- **Browser cache**  
  Stores previously downloaded resources (like CSS, images, JS) on the user’s device to avoid repeated downloads.

- **Server cache**  
  Stores precomputed responses or data on the server to reduce processing time for repeated requests.

- **CDN (Content Delivery Network)**  
  Distributes cached content across geographically distributed servers to deliver data faster to users based on location.
---

### Key Idea

> Instead of regenerating response, server can reuse stored data

---

## 8. Lab 3: Observing Server Behavior

### Task 1: Run Rails Server

    rails server  

Observe terminal output.

---

### Task 2: Access Application

Open browser:

    http://localhost:3000  

Watch terminal:

    Started GET "/" for 127.0.0.1  
    Processing by Controller#action  
    Completed 200 OK  

---

### Task 3: Stop Server

Press:

    Ctrl + C  

Now reload browser → observe error

👉 Explain:
> Server must be running to handle requests

---

### Task 4: Change Port

Run:

    rails server -p 4000  

Visit:

    http://localhost:4000  

---

## 9. Common Misconception

> “The browser loads the website”

Correction:

> The browser **requests** data; the server **provides** it

---

## 10. Summary

- Web server handles HTTP requests  
- Static content is pre-built; dynamic content is generated  
- Puma acts as application server in Rails  
- Ports identify services on a machine  
- Localhost refers to your own system  
- Servers must be running to respond to requests  

---

## 11. Thought Questions

1. What happens if two applications try to use the same port?  
2. Why are dynamic websites more resource-intensive than static ones?  
3. How does caching improve performance?

---

## 💡 Did You Know?

Modern high-performance websites often use a combination of:

- **Nginx** (handling static content and routing)  
- **Application servers** (like Puma or Node.js)  
- **Load balancers**  

This layered architecture allows websites to handle **millions of users efficiently**.

---