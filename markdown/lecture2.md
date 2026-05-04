# 🛠️ Instructor’s Note on AI & Ethics

**Content Origin:** This lecture material was drafted with the assistance of Google AI Studio and has been carefully reviewed and edited by the instructor to ensure technical accuracy and alignment with course goals.

**A Word of Caution:** In the field of Web Technologies, AI is a powerful productivity tool—but it is not a substitute for foundational knowledge.

**Ethics & Accountability:**
You are encouraged to use AI to:
- Clarify concepts
- Debug code

However, you are **fully responsible** for anything you submit. Copying AI-generated material without understanding it is a violation of academic integrity and prevents the development of critical thinking skills required for real-world systems.

> ✅ Always verify — never just copy.

---
# Lecture 2: How the Web Works Internally — DNS & HTTP Deep Dive

---

## 1. Recap of Previous Lecture

In Lecture 1, we established:

- The web follows a **request–response model**
- **HTTP** is the communication protocol
- **TCP/IP** ensures reliable data transfer
- We set up a **Linux-based development environment (WSL2)**

Now we go deeper into *what actually happens* when you open a website.

---

## 2. What Happens When You Type a URL?

Example:  
You type `www.google.com` into your browser.

This triggers a sequence of steps:

1. DNS resolves the domain name into an IP address  
2. Browser establishes a TCP connection  
3. Browser sends an HTTP request  
4. Server sends an HTTP response  
5. Browser renders the content  

---

### Conceptual Flow

    User → Browser → DNS → Server  
    Browser → HTTP Request → Server  
    Browser ← HTTP Response ← Server  
    Browser → Render Page  

---

## 3. Domain Name System (DNS)

Humans prefer names (like google.com), but computers use IP addresses.

### Purpose of DNS

> DNS translates **domain names → IP addresses**

Example:

    google.com → 142.250.190.46  

---

### DNS Resolution Process (Simplified)

1. Browser checks **local cache**  
2. OS checks **DNS cache**  
3. Query sent to **DNS resolver (ISP)**  
4. Resolver contacts:
   - Root server  
   - TLD(Top Level Domain) server (.com)  
   - Authoritative server  
5. IP address is returned  

---

### Key Idea

> DNS is like the **phonebook of the internet**

---

## 4. TCP Connection Establishment

Before HTTP communication, a connection must be established.

### TCP Three-Way Handshake

    Client → SYN → Server  
    Server → SYN-ACK → Client  
    Client → ACK → Server  

After this, a reliable connection is established.

---

## 5. HTTP Deep Dive

HTTP = HyperText Transfer Protocol  
It defines how clients and servers communicate.

---

### Structure of an HTTP Request

    GET /index.html HTTP/1.1  
    Host: example.com  
    User-Agent: Chrome  

- **GET** → Method  
- **/index.html** → Resource  
- **HTTP/1.1** → Protocol version  

---

### Common HTTP Methods

- **GET** → Retrieve data  
- **POST** → Send data  
- **PUT** → Update data  
- **DELETE** → Remove data  

---

### Structure of an HTTP Response

    HTTP/1.1 200 OK  
    Content-Type: text/html  

    <html>
      <body>Hello World</body>
    </html>

---

### HTTP Status Codes

- **200 OK** → Success  
- **301/302** → Redirection  
- **404 Not Found** → Resource not found  
- **500 Internal Server Error** → Server issue  

---

## 6. Stateless Nature of HTTP

HTTP is **stateless**, meaning:

> Each request is independent — the server does not remember previous requests

---

### Problem

How does a website remember:
- Logged-in users?
- Shopping carts?

---

### Solution (Preview)

- Cookies  
- Sessions  

(*Covered in later lectures*)

---

## 7. Lab 2: Observing Web Communication

### Task 1: Inspect HTTP Requests

1. Open browser (Chrome/Firefox)  
2. Press **F12 (Developer Tools)**  
3. Go to **Network tab**  
4. Visit any website  

Observe:
- Request method (GET/POST)  
- Status code  
- Headers  

---

### Task 2: Analyze DNS

Open terminal and run:

    nslookup google.com  

or

    ping google.com  

---

### Task 3: Observe Headers

Look for:
- Host  
- User-Agent  
- Content-Type  

---

## 8. Summary

- DNS converts domain names into IP addresses  
- TCP establishes reliable connection (3-way handshake)  
- HTTP defines request–response communication  
- HTTP is stateless  
- Developer tools help visualize real web traffic  

---

## 9. Thought Questions

1. What happens if DNS fails?  
2. Why is HTTP designed to be stateless?  
3. How would web performance change without caching?

---

## 💡 Did You Know?

The tool **curl**, widely used for testing HTTP requests, was created by **![Daniel Stenberg](../figures/DanielStenberg.jpeg)** in 1997.

Today, curl is one of the most important utilities in web development and is used by:
- Developers for testing APIs  
- DevOps engineers for automation  
- Security professionals for debugging network issues  

Despite its simplicity, curl supports **dozens of protocols** and is included in most operating systems by default.

> Fun fact: Daniel Stenberg still actively maintains curl, making it one of the most consistently developed open-source projects in the world.

---
