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

# Lecture 1: The Architecture of the Modern Web & Your Professional Environment

---

## 1. From User to Developer

Most of you interact with the web as users—browsing websites on devices like Windows PCs, Android phones, or tablets.

In this course, we shift perspective:

> From consuming the web → to understanding and building it

To do this effectively, we must understand:
- How the web works internally
- The environment in which web applications are developed

---

## 2. Our Development Environment

To ensure consistency and avoid “it works on my machine” issues, we will use:

- **Host OS:** Windows 10/11
- **Development Environment:** WSL2 (Ubuntu Linux)
- **Code Editor:** VS Code (with WSL Extension)
- **Version Control:** Git
- **Application Framework (example):** Ruby on Rails

> Note: Rails is used as a learning tool. The concepts you learn will apply to other technologies as well.

---

### Why WSL2?

- Over 90% of web servers run on Linux
- Native web development on Windows can cause compatibility issues
- WSL2 provides:
- Real Linux environment inside Windows
- Better compatibility with modern tools
- Industry-relevant workflow

---

## 3. Core Concept: The Request–Response Cycle

The web operates on a simple model:

### Client (Browser)
- Sends an HTTP request
- Example:

GET / HTTP/1.1
Host: google.com

### Server
- Processes request and sends response
- Example:

HTTP/1.1 200 OK
Content-Type: text/html

---

### Conceptual Flow

Browser → HTTP Request → Server
Browser ← HTTP Response ← Server
(via TCP/IP)

---

## 4. The Underlying Network (TCP/IP)

- **IP Address:**
A unique identifier for devices on the network
Example: 142.250.190.46

- **TCP (Transmission Control Protocol):**
- Reliable delivery
- Ordered data transfer
- Error checking

> HTTP operates on top of TCP

---

## 5. Lab 1: Setting Up Your Development Environment

### Step 1: Install WSL2

Open PowerShell as Administrator and run:

wsl --install

Restart your system after installation.

---

### Step 2: Setup Ubuntu

- Open Ubuntu from Start Menu
- Create username and password
- Update system:

sudo apt update && sudo apt upgrade -y

---

### Step 3: Install VS Code + WSL Extension

- Install VS Code (Windows side)
- Install WSL Extension

From Ubuntu terminal:

code .

This opens VS Code connected to your Linux environment.

---

## 6. Version Control Setup (Git)

Configure Git:

git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"

Clone course repository:

git clone https://github.com/[your-username]/web-tech-notes.git
cd web-tech-notes

---

## 7. Verification Task

Run:

ruby -v
git --version

Task: Take a screenshot and submit as proof of setup.

---

## 8. Summary

- The web works on a request–response model
- HTTP is the communication protocol
- TCP/IP ensures reliable data transfer
- WSL2 provides a production-like Linux environment
- Git will be used for managing course work

---

## 9. Thought Question

What problems might arise if the web used UDP instead of TCP for communication?

---
