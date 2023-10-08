# Learn JavaScript

## Document Object Model (DOM)

Let's say we have a given sample html file:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Learning JS</title>
    <style>
        .heading{
            color: red;
        }
    </style>
</head>
<body>
    <h1 id="demo-heading-1" class="heading">JavaScript Tutorial</h1>
    <div id="dummy">
        <p id="demo">Lorem Ipsum</p>
        <input type="text" id="inp-1" name="inp-1" value="Your Name">
        <button id="btn-1">Click Me</button>
    </div>
    <h1 id="demo-heading-2" class="heading">DOM</h1>
    <script>
        console.log(document.getElementById('demo').innerText)
    </script>
</body>
</html>
```


## Selecting Elements

Major methods to select elements are `getElementById`, `getElementsByClassName`, and `getElementsByTagName`.

1. `getElementById`
```js
console.log(document.getElementById('demo'))
```
*Output:*
```html
<p id="demo">Lorem Ipsum</p>
```
2. `getElementsByTagName`<br> 

This will generate an array of elements which matches the condition.
```js
console.log(document.getElementsByTagName('h1')[0])
```
*Output:*
```html
<h1 id="demo-heading-1" class="heading">JavaScript Tutorial</h1>
```

3. `getElementsByClassName` <br>

This will generate an array of elements which matches the condition.
```js
console.log(document.getElementsByClassName('heading')[0])
```
Output:
```html
<h1 id="demo-heading-1" class="heading">JavaScript Tutorial</h1>
```

### Advance Query Selector

4. `querySelector`
5. `querySelectorAll`

## Modifying the DOM

#### **1. Changing Element Content**

- **innerText**:
  Set or get the human-readable text within an element.

  ```html
  <p id="para">Hello, World!</p>

  <script>
      const para = document.getElementById('para');
      para.innerText = "Hello, Universe!";
  </script>
  ```

  **Output**:
  ```
  Hello, Universe!
  ```

- **textContent**:
  Set or get the text of an element, including any child elements.

  ```html
  <p id="para">Hello, <span>World!</span></p>

  <script>
      const para = document.getElementById('para');
      console.log(para.textContent);  // Outputs "Hello, World!"
      para.textContent = "Greetings, Galaxy!";
  </script>
  ```

  **Output**:
  ```
  Greetings, Galaxy!
  ```

- **innerHTML**:
  Set or get the HTML content inside an element.

  ```html
  <div id="content"></div>

  <script>
      const content = document.getElementById('content');
      content.innerHTML = "<p>This is a paragraph.</p>";
  </script>
  ```

  **Output**:
  ```
  <p>This is a paragraph.</p>
  ```

#### **2. Modifying Attributes**

- **getAttribute & setAttribute**:
  Access and modify element attributes.

  ```html
  <img id="image" src="old_image.jpg" alt="Old Image">

  <script>
      const image = document.getElementById('image');
      const currentSrc = image.getAttribute('src');
      console.log(currentSrc);  // Outputs "old_image.jpg"

      image.setAttribute('src', 'new_image.jpg');
      image.setAttribute('alt', 'New Image');
  </script>
  ```

  **Output**:
  The image's source changes to "new_image.jpg" and its alt text changes to "New Image".

#### **3. Modifying Classes**

- **classList**: Utilize the `add`, `remove`, `toggle`, and `contains` methods.

  ```html
  <div id="box" class="blue"></div>

  <script>
      const box = document.getElementById('box');

      box.classList.add('rounded');  // Adds 'rounded' class
      box.classList.remove('blue');  // Removes 'blue' class
      box.classList.toggle('active');  // Toggles 'active' class
      console.log(box.classList.contains('rounded'));  // Outputs "true"
  </script>
  ```

  **Output**:
  The `div` will no longer have the class "blue", but will now have the classes "rounded" and "active".

#### **4. Creating, Appending, and Removing Elements**

- **createElement, appendChild, & removeChild**:

  ```html
  <ul id="list">
      <li>Item 1</li>
  </ul>

  <script>
      const list = document.getElementById('list');

      // Create new element
      const newItem = document.createElement('li');
      newItem.innerText = "Item 2";

      // Append new element to the list
      list.appendChild(newItem);

      // Remove an element
      const firstItem = list.children[0];
      list.removeChild(firstItem);
  </script>
  ```

  **Output**:
  The list will display:
  ```
  Item 2
  ```

## Navigating the DOM
The DOM (Document Object Model) is a hierarchical, tree-like structure that represents the content of a webpage. When navigating the DOM, we often traverse from one node to another, such as moving from parent to child, from sibling to sibling, etc.

1. `parentNode`
The `parentNode` property returns the parent node of a specified node, as a Node object.
```js
const el = document.getElementById('demo');
console.log(el.parentNode);
```
Output:
```html
<div>
        <p id="demo">Lorem Ipsum</p>
        <input type="text" id="inp-1" name="inp-1" value="Your Name">
        <button id="btn-1">Click Me</button>
    </div>
```

2. `children`
The `children` property returns an HTMLCollection of an element's child elements.
```

```

3. `firstChild` & `lastChild`
4. `firstElementChild` & `lastElementChild`
5. `nextSibling` & `previousSibling`
6. `nextElementSibling` & `previousElementSibling`
