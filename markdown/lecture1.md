🛠️ Instructor’s Note on AI & Ethics

**Content Origin:** This lecture material was drafted with the assistance of Google AI Studio and has been carefully reviewed and edited by the instructor to ensure technical accuracy and alignment with our course goals (Ubuntu, WSL2, and Ruby on Rails).

**A Word of Caution:** In the field of Web Engineering, AI is a powerful tool for productivity, but it is not a substitute for foundational knowledge.

**Ethics & Accountability:** As future engineers, you are encouraged to use AI to clarify concepts or debug code. However, you are solely responsible for the code and documentation you submit. Verbatim copying of AI-generated material without understanding the underlying logic is a breach of academic integrity and prevents the development of the critical thinking skills required to manage complex web systems. Always verify, never just copy.


# Lecture 1: The Architecture of the Modern Web & Your Professional Environment

## 1. Introduction: From "User" to "Developer"
Most of you are used to the Web as **users**—browsing sites on Windows, Mac, or Android. In this course, we shift to being **builders**. 

To build modern web applications, we need an environment that matches the servers that run the internet. Since over **90% of the world's web servers run Linux**, we will be using **Ubuntu**—but we will do it right inside Windows using **WSL2**.

---

## 2. Our Development Stack
To save time and avoid "it works on my machine" bugs, we will use:
*   **Host OS:** Windows 10/11.
*   **Development OS:** `WSL2 (Ubuntu 22.04 LTS)`.
*   **Version Control:** `Git` (Running inside Ubuntu).
*   **The Bridge:** `VS Code` with the **WSL Extension**.
*   **The Engine:** `Ruby on Rails`.

### Why WSL2?
Native Ruby on Rails development on Windows is difficult and prone to errors. **WSL2** gives you a high-performance Linux environment that lets you run professional tools (like Redis, PostgreSQL, and Rails) exactly as they would run on a production server.

---

## 3. Core Concept: The Request-Response Cycle
No matter what OS you use, the web speaks one language: **HTTP (HyperText Transfer Protocol)**.

### The Client (Your Browser)
The browser's job is to send a **Request**. 
*Example:* "Hey Server at `google.com`, please give me your search page."

### The Server (Your Rails App)
The server's job is to send a **Response**. 
*Example:* "Here is the HTML code for the search page. (Status: 200 OK)"

### The "Plumbing" (TCP/IP)
*   **IP Address:** Every computer on the web has a unique address (e.g., `142.250.190.46`).
*   **TCP:** This ensures that your website data doesn't get "corrupted" or lost while traveling through the wires. It breaks data into packets and puts them back together at the destination.

---

## 4. Setup Lab: Building Your Professional Bridge
Since this is our first lecture, your goal is to bridge the gap between Windows and Ubuntu.

### Step 1: Enable WSL2
Open **PowerShell** as Administrator and run:
```powershell
wsl --install
```
*Restart your computer after this finishes.*

### Step 2: Set up Ubuntu
1.  Search for **Ubuntu** in your Windows Start menu and open it.
2.  Follow the prompts to create a **username** and **password**. (Keep this password safe!)
3.  Update your Linux packages:
    ```bash
    sudo apt update && sudo apt upgrade -y
    ```

### Step 3: Install the "Bridge" (VS Code)
1.  Install **VS Code** on your Windows side.
2.  Open VS Code, go to **Extensions** (Ctrl+Shift+X), and search for **"WSL"**. Install it.
3.  In your Ubuntu terminal, type:
    ```bash
    code .
    ```
    *Magic:* This will open VS Code in Windows, but it is actually editing files inside your Ubuntu Linux system!

---

## 5. First Git Task
All lecture notes and assignments will be hosted on GitHub. Let's get your Linux environment connected.

1.  **Configure Git in Ubuntu:**
    ```bash
    git config --global user.name "Your Name"
    git config --global user.email "your_email@example.com"
    ```
2.  **Clone the Course Repo:**
    ```bash
    git clone https://github.com/[your-username]/web-tech-notes.git
    cd web-tech-notes
    ```
3.  **Verify Environment:**
    Run `ruby -v` and `git --version` inside your Ubuntu terminal and take a screenshot.

---

## 6. Summary
*   We are using **WSL2** to get the power of Linux on Windows.
*   **HTTP** is the request/response language of the web.
*   **TCP/IP** is the delivery system.
*   **Git** is how we will manage our code and notes this semester.


***

