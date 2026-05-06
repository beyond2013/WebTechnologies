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

# **Week 5: Markup Foundations**

## **1. SGML (Conceptual Overview)**

* **SGML (Standard Generalized Markup Language)** is a system used to define markup languages.
* It provides rules for creating structured documents.

### **Key Idea**

* SGML is the foundation from which HTML was developed.
* HTML5 is a modern version and is simpler, not strictly based on SGML.

---

## **2. HTML5 Structure**

### **Basic HTML Template**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Page</title>
</head>
<body>
    <h1>Hello World</h1>
</body>
</html>
```

### **Explanation**

* `<!DOCTYPE html>` → Declares the document as HTML5
* `<html>` → Root element of the webpage
* `<head>` → Contains metadata (not visible on the page)
* `<body>` → Contains visible content

---

## **3. Tags and Attributes**

### **Tags**

Tags define elements in HTML.

```html
<p>This is a paragraph</p>
```

* Opening tag: `<p>`
* Closing tag: `</p>`

---

### **Attributes**

Attributes provide additional information about elements.

```html
<a href="https://example.com">Visit</a>
```

* `href` is an attribute
* Attributes are written inside the opening tag

---

### **Common Attributes**

* `id` → Unique identifier
* `class` → Grouping elements
* `href` → Link destination
* `src` → Image source

---

### **Best Practices**

* Use lowercase tag names
* Always use quotes for attribute values
* Use meaningful names

```html
<!-- Good Example -->
<div class="navbar"></div>
```

---

## **4. Semantic Elements**

### **What are Semantic Elements?**

Semantic elements clearly describe their meaning.

---

### **Examples**

| Tag         | Description         |
| ----------- | ------------------- |
| `<header>`  | Top section of page |
| `<nav>`     | Navigation links    |
| `<main>`    | Main content        |
| `<section>` | Section of content  |
| `<article>` | Independent content |
| `<footer>`  | Bottom section      |

---

### **Example**

```html
<header>
    <h1>My Website</h1>
</header>

<main>
    <section>
        <h2>Introduction</h2>
        <p>Welcome to my page.</p>
    </section>
</main>

<footer>
    <p>© 2026</p>
</footer>
```

---

### **Why Use Semantic HTML**

* Improves readability
* Helps search engines understand content
* Supports accessibility tools
* Makes code easier to maintain

---

## 💡 **Lab Activity: Structured HTML Page**

### **Task**

Create a webpage using semantic HTML structure.

---

### **Requirements**

Your page must include:

* `<header>`
* `<nav>`
* `<main>`
* At least **two `<section>` elements**
* `<footer>`

---

### **Starter Template**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>My Structured Page</title>
</head>
<body>

<header>
    <h1>My Website</h1>
</header>

<nav>
    <a href="#">Home</a>
    <a href="#">About</a>
</nav>

<main>
    <section>
        <h2>Introduction</h2>
        <p>This is my first structured page.</p>
    </section>

    <section>
        <h2>Content</h2>
        <p>More content goes here.</p>
    </section>
</main>

<footer>
    <p>© 2026 My Website</p>
</footer>

</body>
</html>
```

---

### **Optional Enhancements**

* Add an `<article>`
* Add an image using `<img>`
* Use `id` and `class` attributes
* Add more sections or links

---

## **Summary**

* SGML is the conceptual foundation of HTML
* HTML defines the structure of web pages
* Tags are the building blocks
* Attributes provide extra information
* Semantic elements improve structure and meaning


