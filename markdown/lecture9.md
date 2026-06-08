# 🛠️ Instructor’s Note on AI & Ethics

**Content Origin:** This lecture material was drafted with the assistance of ChatGPT and has been carefully reviewed and edited by the instructor to ensure technical accuracy and alignment with course goals.

**A Word of Caution:** In the field of Web Technologies, AI is a powerful productivity tool—but it is not a substitute for foundational knowledge.

**Ethics & Accountability:**
You are encouraged to use AI to:
- Clarify concepts
- Debug code

However, you are **fully responsible** for anything you submit. Copying AI-generated material without understanding it is a violation of academic integrity and prevents the development of critical thinking skills required for real-world systems.

> ✅ Always verify — never just copy.
# Week 9: XML & Related Technologies
## XML Basics, XHTML, XML Structure, XML vs HTML

---

# Learning Outcomes

By the end of this lecture, students should be able to:

- Explain what XML is and why it was developed.
- Understand the structure of an XML document.
- Identify XML elements, attributes, and nesting rules.
- Differentiate between XML and HTML.
- Understand the purpose of XHTML.
- Write simple well-formed XML documents.
- Recognize practical applications of XML in modern computing.

---

# Introduction

So far, we have focused on HTML, which is used to create web pages.

HTML tells browsers:

> "How should information be displayed?"

XML focuses on something different:

> "What does the information mean?"

XML allows us to describe, organize, and exchange data between different systems.

---

# Motivation

Consider the following information:

| Student ID | Name | Program |
|------------|--------|----------|
| 101 | Ali | BSCS |
| 102 | Sara | BSIT |

A web page may display this information using HTML tables.

However, if another system wants to process this data automatically, it needs a structured format that describes the meaning of each piece of information.

This is where XML becomes useful.

---

# What is XML?

**XML** stands for:

> **eXtensible Markup Language**

It was designed to:

- Store data
- Transport data
- Describe data
- Enable data exchange between different systems

Unlike HTML, XML does not have predefined tags.

Developers create their own tags according to their needs.

Example:

```xml
<student>
    <id>101</id>
    <name>Ali</name>
    <program>BSCS</program>
</student>
```

Notice that:

- `<student>`
- `<id>`
- `<name>`
- `<program>`

are custom tags.

---

# Why Was XML Created?

HTML was designed primarily for presentation.

Example:

```html
<h1>Ali</h1>
```

The browser knows it is a heading.

But what does "Ali" represent?

- Student?
- Teacher?
- Employee?

HTML does not specify that meaning.

XML solves this problem:

```xml
<studentName>Ali</studentName>
```

Now the meaning is clear.

---

# Characteristics of XML

XML is:

- Self-descriptive
- Human readable
- Machine readable
- Platform independent
- Extensible
- Structured

Example:

```xml
<book>
    <title>Web Technologies</title>
    <author>Imran Ali</author>
</book>
```

Even without documentation, we can understand the data.

---

# XML Document Structure

A typical XML document contains:

1. XML Declaration
2. Root Element
3. Child Elements
4. Attributes (optional)

Example:

```xml
<?xml version="1.0"?>

<student>
    <id>101</id>
    <name>Ali</name>
    <program>BSCS</program>
</student>
```

---

# XML Declaration

Usually appears at the beginning.

```xml
<?xml version="1.0"?>
```

Purpose:

- Indicates that the file is XML.
- Specifies XML version.

Sometimes encoding is also included:

```xml
<?xml version="1.0" encoding="UTF-8"?>
```

---

# Root Element

Every XML document must have exactly one root element.

Correct:

```xml
<students>
    <student>
        ...
    </student>
</students>
```

Incorrect:

```xml
<student>
</student>

<teacher>
</teacher>
```

Multiple root elements are not allowed.

---

# Elements

Elements are the primary building blocks of XML.

Example:

```xml
<name>Ali</name>
```

Here:

- Opening tag = `<name>`
- Content = `Ali`
- Closing tag = `</name>`

Entire element:

```xml
<name>Ali</name>
```

---

# Nested Elements

Elements can contain other elements.

Example:

```xml
<student>
    <id>101</id>
    <name>Ali</name>
</student>
```

This creates a hierarchical structure.

Visualization:

```text
student
├── id
└── name
```

---

# Attributes

Additional information can be stored using attributes.

Example:

```xml
<student id="101">
    <name>Ali</name>
</student>
```

Attribute:

```xml
id="101"
```

---

# Elements vs Attributes

Both can store information.

Using Elements:

```xml
<student>
    <id>101</id>
</student>
```

Using Attributes:

```xml
<student id="101">
</student>
```

General recommendation:

Use elements for data and attributes for metadata.

---

# Empty Elements

Elements without content can be written as:

```xml
<phone></phone>
```

Or:

```xml
<phone />
```

Both represent an empty element.

---

# XML Naming Rules

Tag names:

- Are case-sensitive.
- Cannot start with numbers.
- Cannot contain spaces.
- Should be meaningful.

Valid:

```xml
<studentName>
```

Invalid:

```xml
<123student>
```

Invalid:

```xml
<student name>
```

---

# Case Sensitivity

XML is case-sensitive.

These are different:

```xml
<Name>
```

```xml
<name>
```

```xml
<NAME>
```

The opening and closing tags must match exactly.

Correct:

```xml
<name>Ali</name>
```

Incorrect:

```xml
<name>Ali</Name>
```

---

# Well-Formed XML

A well-formed XML document follows all XML syntax rules.

Requirements:

- Single root element
- Proper nesting
- Matching opening and closing tags
- Case consistency
- Quoted attribute values

Example:

```xml
<student>
    <name>Ali</name>
</student>
```

---

# Incorrect XML Example

```xml
<student>
    <name>Ali
</student>
```

Problem:

- Closing tag for `<name>` is missing.

---

# Proper Nesting

Correct:

```xml
<student>
    <name>Ali</name>
</student>
```

Incorrect:

```xml
<student>
    <name>Ali
</student>
</name>
```

Tags must close in reverse order of opening.

---

# XML Tree Structure

XML documents naturally form a tree.

Example:

```xml
<university>
    <department>
        <student>
            <name>Ali</name>
        </student>
    </department>
</university>
```

Tree:

```text
university
└── department
    └── student
        └── name
```

---

# What is XHTML?

XHTML stands for:

> eXtensible HyperText Markup Language

It combines:

- HTML
- XML rules

In simple words:

> XHTML is HTML written according to XML syntax requirements.

---

# Why XHTML Was Introduced

Traditional HTML browsers were very forgiving.

Example:

```html
<p>Hello
```

Browsers often displayed it anyway.

XHTML introduced stricter rules to improve:

- Consistency
- Reliability
- Interoperability

---

# XHTML Rules

All tags must be closed.

Correct:

```html
<p>Hello</p>
```

Incorrect:

```html
<p>Hello
```

---

# XHTML Rule: Lowercase Tags

Correct:

```html
<h1>Welcome</h1>
```

Incorrect:

```html
<H1>Welcome</H1>
```

---

# XHTML Rule: Proper Nesting

Correct:

```html
<b><i>Text</i></b>
```

Incorrect:

```html
<b><i>Text</b></i>
```

---

# XHTML Rule: Quote Attribute Values

Correct:

```html
<img src="photo.jpg" />
```

Incorrect:

```html
<img src=photo.jpg>
```

---

# XHTML Rule: Close Empty Elements

Correct:

```html
<br />
```

```html
<hr />
```

```html
<img src="photo.jpg" />
```

---

# XML vs HTML

| XML | HTML |
|------|------|
| Stores data | Displays data |
| User-defined tags | Predefined tags |
| Focuses on meaning | Focuses on presentation |
| Strict syntax rules | More forgiving |
| Used for data exchange | Used for web pages |
| Extensible | Fixed set of tags |

---

# Example: HTML

```html
<h1>Ali</h1>
<p>BSCS Student</p>
```

Purpose:

Display information to users.

---

# Example: XML

```xml
<student>
    <name>Ali</name>
    <program>BSCS</program>
</student>
```

Purpose:

Describe and store information.

---

# Real-World Uses of XML

Although JSON has become very popular, XML is still widely used in:

- Configuration files
- Office documents (DOCX, PPTX, XLSX)
- Android application resources
- RSS feeds
- Enterprise systems
- Web services (SOAP)
- Data interchange between organizations

---

# XML and Modern Technologies

Many modern technologies rely on XML behind the scenes.

Examples:

### Microsoft Office Files

```text
.docx
.xlsx
.pptx
```

Internally contain XML files.

---

### Android Layout Files

```xml
<TextView
    android:text="Hello" />
```

Android applications use XML extensively.

---

# Advantages of XML

- Platform independent
- Easy data exchange
- Human readable
- Extensible
- Structured format
- Widely supported

---

# Limitations of XML

- Verbose (requires many tags)
- Larger file sizes
- More complex than JSON
- Can become difficult to manage for very large documents

---

# XML vs JSON (Brief Introduction)

XML:

```xml
<student>
    <name>Ali</name>
</student>
```

JSON:

```json
{
    "name": "Ali"
}
```

JSON is generally shorter and easier to process in web applications.

However, XML remains important in many existing systems.

---

# Summary

- XML stands for eXtensible Markup Language.
- XML is used to store, organize, and exchange data.
- XML uses custom tags.
- XML documents must be well-formed.
- Every XML document requires a single root element.
- XHTML is HTML written according to XML rules.
- XML focuses on data and meaning.
- HTML focuses on presentation and display.
- XML continues to be widely used in many software systems.

---

# In-Class Activity

Create a well-formed XML document representing all courses you are studying during this semester.

Requirements:

- Root element: courses
- Each course should include:
  - Course code
  - Course title
  - Instructor name
  - Credit hours
  - Semester

After creating the XML document:

1. Verify that all tags are properly closed.
2. Check for proper nesting.
3. Ensure there is exactly one root element.
4. Identify which parts are data and which could be attributes.

[W3C Markup Validator](https://validator.w3.org/)