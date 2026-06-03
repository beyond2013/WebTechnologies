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

# Combined Lab: Advanced CSS3 Styling and Effects

## Lab Title
**Advanced CSS3 Styling, Transitions, Animations, and Modern Visual Effects**

## Objectives

By the end of this lab, students will be able to:

- Apply advanced CSS3 visual effects.
- Use CSS transitions for smooth state changes.
- Create simple CSS animations using keyframes.
- Utilize modern CSS features such as gradients, shadows, and transforms.
- Enhance user experience through interactive styling.
- Build an attractive and professional-looking webpage.

---

# Part 1: Starting Point

Use any HTML page created in previous labs (personal profile, portfolio, product page, university page, etc.).

If no previous page is available, create a simple webpage containing:

- Header
- Navigation Menu
- Main Content Section
- Image
- Footer

---

# Part 2: Advanced CSS3 Styling

## Task 1: Apply Gradients

Replace solid background colors with gradients.

### Example

```css
header {
    background: linear-gradient(to right, #4facfe, #00f2fe);
}
```

### Requirements

- Use at least one linear gradient.
- Apply gradients to the header or banner section.

---

## Task 2: Add Shadows

Apply shadows to cards, images, or content sections.

### Example

```css
.card {
    box-shadow: 0px 4px 10px rgba(0,0,0,0.3);
}
```

### Requirements

- Add shadow to at least two elements.
- Use shadows to improve visual appearance.

---

## Task 3: Rounded Corners

Apply rounded corners using:

```css
border-radius: 10px;
```

### Requirements

- Use rounded corners on buttons.
- Use rounded corners on images or content cards.

---

# Part 3: CSS3 Transforms

## Task 4: Element Transformations

Apply CSS transforms when hovering over elements.

### Examples

```css
img:hover {
    transform: scale(1.1);
}
```

```css
button:hover {
    transform: rotate(5deg);
}
```

### Requirements

Implement at least two transformations:

- Scale
- Rotate
- Translate
- Skew

---

# Part 4: CSS3 Transitions

## Task 5: Smooth Hover Effects

Create smooth transitions for interactive elements.

### Example

```css
button {
    transition: all 0.4s ease;
}

button:hover {
    background-color: green;
    color: white;
}
```

### Requirements

Apply transitions to:

- Buttons
- Navigation links
- Images

---

# Part 5: CSS3 Animations

## Task 6: Create a Keyframe Animation

### Example

```css
@keyframes fadeIn {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

Apply animation:

```css
h1 {
    animation: fadeIn 2s ease-in;
}
```

### Requirements

Create at least one custom animation.

Possible ideas:

- Fade In
- Slide In
- Bounce
- Pulse
- Floating Effect

---

## Task 7: Infinite Animation

Create a continuously running animation.

### Example

```css
@keyframes pulse {
    0% {
        transform: scale(1);
    }

    50% {
        transform: scale(1.05);
    }

    100% {
        transform: scale(1);
    }
}
```

Apply it to:

- Logo
- Button
- Banner Image

---

# Part 6: Interactive Navigation Menu

## Task 8

Enhance the navigation bar using:

- Hover effects
- Color changes
- Underline animations
- Smooth transitions

### Example

```css
nav a {
    transition: color 0.3s;
}

nav a:hover {
    color: orange;
}
```

---

# Part 7: Mini Project

Create a visually appealing webpage incorporating all the concepts learned.

## The Page Must Include

### Layout Components

- Header
- Navigation Bar
- Main Content
- At Least One Image
- Footer

### CSS3 Features

- Gradient Background
- Shadows
- Border Radius
- Transform Effects
- Transitions
- Keyframe Animation

---

# Deliverables

Submit:

1. `index.html`
2. `style.css`
3. Any images used

---

