# TaskFlow - Interactive Task Manager Using Pure JavaScript

## Project Overview

TaskFlow is a simple Task Manager application built using HTML, CSS, and Vanilla JavaScript.

The purpose of this project is to demonstrate:

* DOM Manipulation
* Event Handling
* Event Delegation
* Event Propagation (Bubbling & Capturing)
* Attributes vs Properties
* Browser Rendering Pipeline
* Local Storage Integration

No frameworks or libraries were used in this project.

---

## Features

### Task Management

Users can:

* Add Tasks
* Edit Tasks
* Mark Tasks as Completed
* Delete Tasks
* Clear All Tasks

### Search & Filter

* Search tasks by title
* Filter tasks by category
* View completed tasks separately

### Theme Toggle

* Light Mode
* Dark Mode
* Theme preference saved in Local Storage

### Task Counters

* Pending Task Counter
* Completed Task Counter

### Local Storage

Tasks remain available even after refreshing the page.

---

## DOM Manipulation

Task cards are created dynamically using DOM APIs.

Methods used:

```javascript
createElement()
append()
appendChild()
replaceChildren()
remove()
createDocumentFragment()
```

Each task card contains:

* Edit Button
* Save Button
* Complete Button
* Delete Button

---

## Attributes vs Properties

Every task card contains custom data attributes:

```html
data-id
data-status
data-category
```

Methods used:

```javascript
getAttribute()
setAttribute()
removeAttribute()
hasAttribute()
dataset
```

### Difference Between Attribute and Property

Property:

```javascript
titleInput.value
```

Returns the current value entered by the user.

Attribute:

```javascript
titleInput.getAttribute("value")
```

Returns the original value defined in HTML.

Example:

If the HTML is:

```html
<input value="Task">
```

And the user changes it to:

```text
Buy Groceries
```

Then:

```javascript
titleInput.value
```

returns:

```text
Buy Groceries
```

while:

```javascript
titleInput.getAttribute("value")
```

still returns:

```text
Task
```

This shows that properties change dynamically while attributes remain the original HTML values.

---

## Event Handling

The application uses addEventListener() for:

* Adding Tasks
* Editing Tasks
* Saving Tasks
* Completing Tasks
* Deleting Tasks
* Searching Tasks
* Filtering Tasks
* Theme Toggle

Example:

```javascript
addTaskBtn.addEventListener("click", addTask);
```

---

## Event Delegation

Instead of adding event listeners to every task button individually, a single event listener is attached to the parent container.

```javascript
taskList.addEventListener("click", function(e) {
   ...
});
```

Benefits:

* Better Performance
* Less Memory Usage
* Supports Dynamically Created Elements

---

## Event Propagation

A separate section demonstrates Event Bubbling and Event Capturing.

### Event Bubbling

Execution Order:

```text
Child
Parent
Grandparent
```

Events move from the target element to its parent elements.

### Event Capturing

Execution Order:

```text
Grandparent
Parent
Child
```

Events move from outer elements towards the target element.

---

## Browser Rendering Pipeline

This project includes a visual explanation of how browsers render web pages.

### HTML Processing

```text
HTML
↓
Tokenization
↓
Parsing
↓
DOM Tree
```

### CSS Processing

```text
CSS
↓
CSSOM Tree
```

### Rendering

```text
DOM Tree + CSSOM Tree
↓
Render Tree
↓
Layout
↓
Paint
↓
Composite
```

### Explanation

#### Tokenization

The browser converts HTML source code into tokens.

#### Parsing

Tokens are converted into objects.

#### DOM Tree

The browser creates a tree structure representing the HTML document.

#### CSSOM Tree

The browser parses CSS and creates a CSS Object Model.

#### Render Tree

The DOM Tree and CSSOM Tree are combined.

#### Layout

The browser calculates the position and size of elements.

#### Paint

The browser draws pixels on the screen.

#### Composite

The browser combines layers and displays the final page.

---

## Local Storage

The application stores data using Local Storage.

Stored Keys:

```javascript
taskflow-tasks
taskflow-counter
taskflow-theme
```

Methods used:

```javascript
localStorage.setItem()
localStorage.getItem()
```

This allows tasks and theme preferences to persist after page refresh.

---

## Project Structure

```text
TaskFlow
│
├── index.html
├── style.css
├── script.js
└── README.md
```

---

## How to Run the Project

1. Download or clone the repository.

```bash
git clone <repository-url>
```

2. Open the project folder.

3. Open index.html in your browser.

No installation or dependencies are required.

---

## Bonus Features Implemented

* Task Search
* Category Filter
* Completed Task Counter
* Pending Task Counter
* Clear All Tasks Button
* Local Storage Integration
* Theme Persistence
* DocumentFragment Usage

---

## Learning Outcomes

Through this project I learned:

* Creating elements dynamically using DOM APIs
* Difference between Attributes and Properties
* Event Handling using JavaScript
* Event Delegation
* Event Bubbling and Capturing
* Browser Rendering Pipeline
* Local Storage Integration
* Building interactive UI without frameworks

---

## Conclusion

TaskFlow is a fully interactive Task Manager application built using only HTML, CSS, and Vanilla JavaScript.

This project demonstrates real-world usage of DOM Manipulation, Event Handling, Event Delegation, Event Propagation, Attributes vs Properties, and Browser Rendering Pipeline concepts while maintaining a clean and responsive user interface.
