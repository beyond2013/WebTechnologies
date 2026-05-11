# 🛠️ Instructor’s Note on AI & Ethics

**Content Origin:** This lecture material was drafted with the assistance of Google AI Studio and has been carefully reviewed and edited by the instructor to ensure technical accuracy and alignment with course goals.

**A Word of Caution:** In the field of Web Technologies, AI is a powerful productivity tool—but it is not a substitute for foundational knowledge.

**Ethics & Accountability:**
You are encouraged to use AI to:
- Clarify concepts
- Debug code

However, you are **fully responsible** for anything you submit. Copying AI-generated material without understanding it is a violation of academic integrity and prevents the development of critical thinking skills required for real-world systems.

> ✅ Always verify — never just copy.

# Week 6: Advanced HTML5
---

# Lecture Overview

In this lecture, we will study advanced HTML5 features that make modern web pages interactive, structured, and user friendly. We will focus on:

* HTML forms and modern input types
* Multimedia support using audio and video
* Semantic HTML elements
* Accessibility basics
* Lab activity: Building a multi-section webpage

By the end of this lecture, students should be able to:

* Create interactive forms using modern HTML5 controls
* Embed audio and video content in web pages
* Structure webpages using semantic HTML tags
* Apply basic accessibility practices
* Develop a small structured webpage combining all concepts

---

# 1. Introduction to Advanced HTML5

Earlier versions of HTML mainly focused on displaying text and hyperlinks.

HTML5 introduced many modern features that made websites:

* More interactive
* Easier to structure
* Easier to access for users with disabilities
* More multimedia friendly
* Better suited for mobile devices

HTML5 reduced dependence on external plugins like Flash by introducing built-in support for:

* Forms
* Audio
* Video
* Semantic page structure
* Graphics and APIs

Modern websites heavily rely on these HTML5 features.

---

# 2. HTML Forms

## What is a Form?

A form is used to collect input from users.

Examples:

* Login pages
* Registration forms
* Search bars
* Online surveys
* Feedback systems
* Checkout pages

The `<form>` element acts as a container for input controls.

---

## Basic Form Structure

```html
<form>
    <label>Name:</label>
    <input type="text">

    <button>Submit</button>
</form>
```

---

## Common Form Elements

| Element      | Purpose                      |
| ------------ | ---------------------------- |
| `<input>`    | Takes user input             |
| `<textarea>` | Multi-line text input        |
| `<select>`   | Dropdown list                |
| `<option>`   | Option inside dropdown       |
| `<button>`   | Creates buttons              |
| `<label>`    | Describes an input field     |
| `<fieldset>` | Groups related form elements |
| `<legend>`   | Title for fieldset           |

---

# 3. Input Types in HTML5

HTML5 introduced many new input types.

These provide:

* Better user experience
* Mobile-friendly keyboards
* Built-in validation
* Easier data collection

---

## Text Input

```html
<input type="text">
```

Used for general text input.

Example:

* Name
* City
* Subject

---

## Password Input

```html
<input type="password">
```

Characters are hidden while typing.

Used for:

* Passwords
* PIN codes

---

## Email Input

```html
<input type="email">
```

Automatically checks valid email format.

Example:

```html
<input type="email" placeholder="abc@example.com">
```

---

## Number Input

```html
<input type="number">
```

Allows numeric values only.

Example:

```html
<input type="number" min="1" max="100">
```

---

## Date Input

```html
<input type="date">
```

Displays a calendar picker in modern browsers.

---

## Time Input

```html
<input type="time">
```

Used for selecting time.

---

## Range Input

```html
<input type="range" min="0" max="10">
```

Creates a slider control.

Useful for:

* Volume control
* Rating systems
* Brightness settings

---

## Color Input

```html
<input type="color">
```

Displays a color picker.

---

## File Upload

```html
<input type="file">
```

Allows users to upload files.

---

## Checkbox

```html
<input type="checkbox">
```

Allows multiple selections.

Example:

```html
<input type="checkbox"> Cricket
<input type="checkbox"> Football
```

---

## Radio Button

```html
<input type="radio" name="gender">
```

Allows selection of only one option from a group.

Example:

```html
<input type="radio" name="gender"> Male
<input type="radio" name="gender"> Female
```

---

# 4. Useful Form Attributes

## Placeholder

Displays temporary hint text.

```html
<input type="text" placeholder="Enter your name">
```

---

## Required

Makes input mandatory.

```html
<input type="email" required>
```

---

## Readonly

User can see but cannot modify the value.

```html
<input type="text" value="Pakistan" readonly>
```

---

## Disabled

Completely disables the field.

```html
<input type="text" disabled>
```

---

## Autofocus

Automatically places cursor inside the field.

```html
<input type="text" autofocus>
```

---

# 5. Example Registration Form

```html
<form>
    <h2>Student Registration</h2>

    <label>Full Name</label>
    <input type="text" required>

    <label>Email</label>
    <input type="email" required>

    <label>Age</label>
    <input type="number" min="16" max="60">

    <label>Date of Birth</label>
    <input type="date">

    <label>Password</label>
    <input type="password">

    <label>Department</label>
    <select>
        <option>Computer Science</option>
        <option>Information Technology</option>
        <option>Software Engineering</option>
    </select>

    <button type="submit">Submit</button>
</form>
```

---

# 6. Multimedia in HTML5

Before HTML5, multimedia required plugins such as:

* Adobe Flash
* Silverlight
* External media players

HTML5 introduced native support for:

* Audio
* Video

This made multimedia easier, faster, and more secure.

---

# 7. HTML5 Audio

The `<audio>` element is used to play sound files.

## Basic Example

```html
<audio controls>
    <source src="song.mp3" type="audio/mpeg">
</audio>
```

---

## Common Audio Attributes

| Attribute  | Purpose                   |
| ---------- | ------------------------- |
| `controls` | Shows play/pause controls |
| `autoplay` | Starts automatically      |
| `loop`     | Repeats audio             |
| `muted`    | Starts muted              |

---

## Example with Multiple Formats

```html
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
    <source src="audio.ogg" type="audio/ogg">

    Your browser does not support audio.
</audio>
```

Different browsers may support different formats.

---

# 8. HTML5 Video

The `<video>` element is used to display videos.

## Basic Example

```html
<video width="500" controls>
    <source src="movie.mp4" type="video/mp4">
</video>
```

---

## Common Video Attributes

| Attribute          | Purpose                     |
| ------------------ | --------------------------- |
| `controls`         | Displays media controls     |
| `autoplay`         | Starts automatically        |
| `loop`             | Repeats video               |
| `muted`            | Starts muted                |
| `poster`           | Thumbnail image before play |
| `width` / `height` | Video dimensions            |

---

## Example with Poster Image

```html
<video width="600" controls poster="thumbnail.jpg">
    <source src="lecture.mp4" type="video/mp4">
</video>
```

---

# 9. Semantic HTML

## What is Semantic HTML?

Semantic HTML uses tags that clearly describe their meaning.

Instead of using only generic containers like:

```html
<div>
```

HTML5 introduced meaningful tags such as:

* `<header>`
* `<nav>`
* `<main>`
* `<section>`
* `<article>`
* `<aside>`
* `<footer>`

---

# 10. Why Semantic HTML is Important

Semantic HTML improves:

* Code readability
* Website organization
* Search engine optimization (SEO)
* Accessibility
* Maintainability

It helps both humans and machines understand webpage structure.

---

# 11. Common Semantic Elements

## Header

Represents introductory content.

```html
<header>
    <h1>My Website</h1>
</header>
```

---

## Navigation

Contains navigation links.

```html
<nav>
    <a href="#">Home</a>
    <a href="#">About</a>
</nav>
```

---

## Main

Represents the primary page content.

```html
<main>
    Main content here
</main>
```

---

## Section

Groups related content.

```html
<section>
    <h2>Services</h2>
</section>
```

---

## Article

Represents independent content.

Examples:

* Blog post
* News article
* Forum post

```html
<article>
    <h2>News Title</h2>
</article>
```

---

## Aside

Contains side content.

Examples:

* Sidebar
* Advertisements
* Related links

```html
<aside>
    Related posts
</aside>
```

---

## Footer

Represents bottom section of webpage.

```html
<footer>
    Copyright 2026
</footer>
```

---

# 12. Semantic Layout Example

```html
<body>

<header>
    <h1>Tech Blog</h1>
</header>

<nav>
    <a href="#">Home</a>
    <a href="#">Articles</a>
</nav>

<main>

    <section>
        <article>
            <h2>HTML5 Introduction</h2>
            <p>HTML5 provides modern web features.</p>
        </article>
    </section>

    <aside>
        Related Tutorials
    </aside>

</main>

<footer>
    All rights reserved
</footer>

</body>
```

---

# 13. Accessibility Basics

## What is Accessibility?

Accessibility means designing websites that can be used by everyone, including people with:

* Visual impairments
* Hearing impairments
* Physical disabilities
* Cognitive limitations

Accessible websites are easier for:

* Screen readers
* Keyboard navigation
* Assistive technologies

---

# 14. Accessibility Best Practices

## Use Proper Labels

Bad Example:

```html
<input type="text">
```

Better Example:

```html
<label>Name</label>
<input type="text">
```

Labels help screen readers identify form controls.

---

## Add Alt Text to Images

```html
<img src="student.jpg" alt="Student using a laptop">
```

The `alt` attribute describes the image.

It is useful when:

* Images fail to load
* Visually impaired users use screen readers

---

## Use Semantic Elements

Semantic HTML helps assistive technologies understand webpage structure.

Example:

```html
<nav>
```

is more meaningful than:

```html
<div>
```

---

## Maintain Proper Heading Order

Correct:

```html
<h1>Main Title</h1>
<h2>Section</h2>
<h3>Subsection</h3>
```

Avoid skipping levels.

Incorrect:

```html
<h1>Main</h1>
<h4>Subsection</h4>
```

---

## Ensure Keyboard Accessibility

Users should be able to navigate using:

* Tab key
* Enter key
* Arrow keys

Interactive elements should be keyboard accessible.

---

# 15. Combining Semantic HTML and Accessibility

Well-structured semantic HTML naturally improves accessibility.

For example:

* `<nav>` identifies navigation area
* `<main>` identifies primary content
* `<footer>` identifies footer section

Screen readers can quickly move between these sections.

---

# 16. Mini Project Demonstration

## Multi-Section Webpage

The following example combines:

* Semantic HTML
* Forms
* Multimedia
* Accessibility practices

```html
<!DOCTYPE html>
<html>
<head>
    <title>University Portal</title>
</head>
<body>

<header>
    <h1>University Portal</h1>
</header>

<nav>
    <a href="#">Home</a>
    <a href="#">Courses</a>
    <a href="#">Contact</a>
</nav>

<main>

<section>
    <h2>Introduction Video</h2>

    <video width="400" controls>
        <source src="intro.mp4" type="video/mp4">
    </video>
</section>

<section>
    <h2>Student Registration</h2>

    <form>

        <label>Full Name</label>
        <input type="text" required>

        <label>Email</label>
        <input type="email" required>

        <label>Department</label>
        <select>
            <option>Computer Science</option>
            <option>Software Engineering</option>
        </select>

        <button type="submit">Register</button>

    </form>
</section>

</main>

<footer>
    <p>Copyright 2026</p>
</footer>

</body>
</html>
```

---

# 17. Lab Activity

## Lab Task: Build a Multi-Section Webpage

### Objective

Create a webpage that combines:

* Semantic layout
* Multimedia
* HTML forms
* Accessibility features

---

## Requirements

Students must create:

### 1. Header Section

Include:

* Website title
* Logo or heading

---

### 2. Navigation Bar

Include at least 3 links.

Examples:

* Home
* About
* Contact

---

### 3. Main Content Area

Include:

* At least two sections
* One article
* One sidebar/aside

---

### 4. Multimedia Section

Add either:

* One audio file
* One video file

---

### 5. Form Section

Include:

* Text input
* Email input
* Password input
* Dropdown menu
* Submit button

---

### 6. Accessibility Features

Include:

* Labels for inputs
* Alt text for images
* Semantic HTML tags

---

# 18. Suggested Lab Structure

```text
Header
Navigation
Main Content
    ├── Section
    ├── Article
    ├── Aside
    └── Form
Footer
```

---

# 19. Common Student Mistakes

## Forgetting Closing Tags

Incorrect:

```html
<p>Hello
```

Correct:

```html
<p>Hello</p>
```

---

## Missing Form Labels

Inputs without labels reduce accessibility.

---

## Using Only div Elements

Avoid building the entire webpage using only `<div>`.

Use semantic elements where appropriate.

---

## Incorrect Input Types

Example:

Using `text` instead of `email`.

Proper input types improve validation.

---

# 20. Summary

In this lecture, we studied:

* HTML forms
* Modern input types
* Audio and video embedding
* Semantic HTML elements
* Accessibility basics
* Building structured webpages

These concepts form the foundation of modern web development and are heavily used in professional websites.

---

# 21. Practice Questions

1. What is the purpose of HTML forms?
2. Differentiate between checkbox and radio button.
3. What is semantic HTML?
4. Why is accessibility important?
5. Explain the purpose of the `<audio>` and `<video>` tags.
6. What are the benefits of HTML5 input types?
7. Differentiate between `<section>` and `<article>`.
8. What is the purpose of the `alt` attribute?
9. Why are labels important in forms?
10. Explain the role of semantic HTML in accessibility.

---

# 22. Homework

Create a personal portfolio webpage containing:

* Header
* Navigation bar
* About section
* Skills section
* Embedded video or audio
* Contact form
* Semantic HTML structure
* Accessibility improvements

Students should validate their HTML code and ensure proper indentation and readability.
