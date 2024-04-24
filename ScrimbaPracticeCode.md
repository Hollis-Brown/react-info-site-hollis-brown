# Scrimba Part 1: React Info Site Practice Notes
### Vid 3
- Rewrite code from memory
```javascript
ReactDOM.render(<h1>Hello, everyone!</h1>, document.getElementById("root"))
```
### Vid 4
- Add ul and 2+ list
```javascript
ReactDOM.render(
  <ul><li>Thing 1</li><li>Thing 2</li></ul>,
  document.getElementById("root")
)
```
### Vid 7
- Create a main component called MainContent and add simple h1 "I'm learning React!"
- Render it in `ReactDOM.render`
```javascript
function MainContent() {
  return (
      <h1>I'm learning React!</h1>
  )
}
ReactDOM.render(
  <div>
      <Navbar />
      <MainContent />
  </div>,
  document.getElementById("root")
)
```
### Vid 8 
- Challenge - recreate the above line of code in vanilla JS by creating and appending an h1 to our div#root (without using innerHTML).
    - Create a new h1 element
    - Give it some textContent
    - Give it a class name of "header"
    - append it as a child of the div#root
```javascript
const h1 = document.createElement("h1")
h1.textContent = "This is an imperative way to program"
h1.className = "header"
document.getElementById("root").append(h1)
```    
### Vid 9
- Challenge -create a navbar in JSX:
    - Use the semantic `nav` element as the parent wrapper
    - Have an h1 element with the brand name of your "website"
    - Insert an unordered list for the other nav elements
        - Inside the `ul`, have three `li`s for "Pricing",
        "About", and "Contact"
    - Don't worry about styling yet - it'll just be plain-looking HTML for now
```javascript
const navbar = (
    <nav>
        <h1>Bob's Bistro</h1>
        <ul>
            <li>Menu</li>
            <li>About</li>
            <li>Contact</li>
        </ul>
    </nav>
)

ReactDOM.render(navbar, document.getElementById("root"))
```
### Vid 10
- Build and deploy to netlify was taught in Module 2 by Instructor Alexander

### Vid 14
- Challenge: find out what happens if we try to append JSX
to our div#root using .append() instead of ReactDOM

  1. Create a sample page in JSX (≥ 4 elements) and save them in a variable
  2. Select the div with the ID of "root" and use `.append()` to append
   your JSX
  3. See if you can guess what will show up in the browser before running
   the code
  4. See if you can explain what actually shows up in the browser
```javascript
// Not necessary to write code
// Be sure to surround multiple JSX elements with a div and/or a React fragment
// Be sure to include import statements for react library for building user interfaces, and for rendering components to the DOM
import React from "react"
import ReactDOM from "react-dom"
// Be sure to include this statement at the bottom to render the component and display it with the ID root. 
ReactDOM.render(page, document.getElementById("root"))
```

### Vid 15 
- Challenge: Starting from scratch, build and render the HTML for our section project. Check the Google slide for what you're trying to build.
```javascript
import React from "react"
import ReactDOM from "react-dom"

const page = (
    <div>
        <img src="./react-logo.png" width="40px" alt="React Logo"/>
        <h1>Fun facts about React</h1>
        <ul>
            <li>Was first released in 2013</li>
            <li>Was originally created by Jordan Walke</li>
            <li>Has well over 100K stars on GitHub</li>
            <li>Is maintained by Facebook</li>
            <li>Powers thousands of enterprise apps, including mobile apps</li>
        </ul>
    </div>
)

ReactDOM.render(page, document.getElementById("root"))
// Don't forget to be inclusive and considerate, always add in an ALT tag devvies!
```

### Vid 16
- Pop Quiz!
    1. Why do we need to `import React from "react"` in our files?
        - To use React functionalities, such as creating components, using JSX syntax, and utilizing React features like hooks and context.
    2. If I were to console.log(page) in index.js, what would show up?
        - It would show the compiled JavaScript representation of the JSX element page, which is typically a function call to create the element.
    3. What's wrong with this code:
    ```javascript
    const page = (
      <h1>Hello</h1>
      <p>This is my website!</p>
    )
    ```
        - Needs a React fragment to avoid producing an error. 

    4. What does it mean for something to be "declarative" instead of "imperative"?
        - It means describing what you want to achieve without specifying the exact steps to achieve it.

    5. What does it mean for something to be "composable"?
        - It means that components or elements can be combined or nested together to create more complex and reusable structures.

### Vid 17
- Challenge: 
    - Part 1: Create a page of your own using a custom Page component
        - It should return an ordered list with the reasons why you're excited to be learning React.
    - Render your list to the page
```javascript
import React from "react"
import ReactDOM from "react-dom"

function Page() {
    return (
        <ol>
            <li>It's part of the tech stack that's in demand for obtaining employment at the moment.</li>
            <li>The UI library doesn't have as steep of a learning curve as JavaScript originally did for me</li>
            <li>I enjoy writing JSX and JavaScript, React's declarativeness and composability, and how reactive the functionality is in my projects.</li>
        </ol>
    )
}

ReactDOM.render(<Page />, document.getElementById("root"))
```

### Vid 18
- Challenge: 
    - Part 2: 
        - Add a `header` element with a nested `nav` element. Inside the `nav`, include a `img` element with the image of the React logo inside (`src="./react-logo.png"`) and make sure to set the width to something more manageable so it doesn't take up the whole screen
        - Add an `h1` with some text describing the page. (E.g. "Reasons I'm excited to learn React"). Place it above the ordered list.
        - Add a `footer` after the list that says: `"© 20xx <last name here> development. All rights reserved."`
```javascript
import React from "react"
import ReactDOM from "react-dom"

function Page() {
    return (
        <div>
            <header>
                <nav>
                    <img src="./react-logo.png" width="40px" />
                </nav>
            </header>
            <h1>Reasons I'm excited to learn React</h1>
            <ol>
                <li>It's a popular library, so I'll be 
                able to fit in with the cool kids!</li>
                <li>I'm more likely to get a job as a developer
                if I know React</li>
            </ol>
            <footer>
                <small>© 2021 Ziroll development. All rights reserved.</small>
            </footer>
        </div>
    )
}

ReactDOM.render(<Page />, document.getElementById("root"))
```
### Vid 19
- Quiz!
  1. What is a React component?
      - A piece of reusable code that is in the form of a function which is self-contained in a file with exportation syntax for importing into another file.

  2. What's wrong with this code?
  ```javascript
  function myComponent() {
    return (
        <small>I'm tiny text!</small>
    )
  }
  ```
      - Functions need to be capitalized and/or adhere to PascalCase.

  3. What's wrong with this code?
  ```javascript
  function Header() {
    return (
        <header>
            <nav>
                <img src="./react-logo.png" width="40px" />
            </nav>
        </header>
    )
  }

  ReactDOM.render(Header(), document.getElementById("root"))
  ```
    - Multiple element JSX should be wrapped with a div and/or a React fragment. 

### Vid 20
- Mini Challenge:
    - Move the `header` element from Page into its own component called `"Header"`.
- <mark>Original Code</mark>
```javascript
import React from "react"
import ReactDOM from "react-dom"

function Page() {
    return (
        <div>
            <header>
                <nav>
                    <img src="./react-logo.png" width="40px" />
                </nav>
            </header>
            <h1>Reasons I'm excited to learn React</h1>
            <ol>
                <li>It's a popular library, so I'll be 
                able to fit in with the cool kids!</li>
                <li>I'm more likely to get a job as a developer
                if I know React</li>
            </ol>
            <footer>
                <small>© 2021 Ziroll development. All rights reserved.</small>
            </footer>
        </div>
    )
}

ReactDOM.render(<Page />, document.getElementById("root"))
```

- <mark>New Code</mark>
```javascript
import React from "react"
import ReactDOM from "react-dom"

function Header() {
    return (
        <header>
            <nav>
                <img src="./react-logo.png" width="40px" />
            </nav>
        </header>
    )
}

function Page() {
    return (
        <div>
            <Header />
            <h1>Reasons I'm excited to learn React</h1>
            <ol>
                <li>It's a popular library, so I'll be 
                able to fit in with the cool kids!</li>
                <li>I'm more likely to get a job as a developer
                if I know React</li>
            </ol>
            <footer>
                <small>© 2021 Ziroll development. All rights reserved.</small>
            </footer>
        </div>
    )
}

ReactDOM.render(<Page />, document.getElementById("root"))
```
- Challenge: 
    - Move the `footer` into its own component called "Footer" and render that component inside the Page component.
    - Move the `h1` and `ol` together into another component called "MainContent" and render inside Page as well.
```javascript
import React from "react"
import ReactDOM from "react-dom"

function Header() {
    return (
        <header>
            <nav>
                <img src="./react-logo.png" width="40px" />
            </nav>
        </header>
    )
}

function Footer() {
    return (
        <footer>
            <small>© 2021 Ziroll development. All rights reserved.</small>
        </footer>
    )
}

function MainContent() {
    return (
        <div>
            <h1>Reasons I'm excited to learn React</h1>
            <ol>
                <li>It's a popular library, so I'll be 
                able to fit in with the cool kids!</li>
                <li>I'm more likely to get a job as a developer
                if I know React</li>
            </ol>
        </div>
    )
}

function Page() {
    return (
        <div>
            <Header />
            <MainContent />
            <Footer />
        </div>
    )
}

ReactDOM.render(<Page />, document.getElementById("root"))
```

###Vid 21
- Challenge: 
    - Add an `ul` inside the Header's `nav` and create the following `li`s: "Pricing", "About", & "Contact"
    - Using flexbox, line up the nav items horizontally, and put them inline with the React logo.
    - Change the image styling to happen in CSS instead of in-line
    - For practice, add a new class to the image in order to style it
- <mark>index.js file below</mark>
```javascript
import React from "react"
import ReactDOM from "react-dom"

function Header() {
    return (
        <header>
            <nav className="nav">
                <img src="./react-logo.png" className="nav-logo" />
                <ul className="nav-items">
                    <li>Pricing</li>
                    <li>About</li>
                    <li>Contact</li>
                </ul>
            </nav>
        </header>
    )
}

function Footer() {
    return (
        <footer>
            <small>© 2021 Ziroll development. All rights reserved.</small>
        </footer>
    )
}

function MainContent() {
    return (
        <div>
            <h1>Reasons I'm excited to learn React</h1>
            <ol>
                <li>It's a popular library, so I'll be 
                able to fit in with the cool kids!</li>
                <li>I'm more likely to get a job as a developer
                if I know React</li>
            </ol>
        </div>
    )
}

function Page() {
    return (
        <div>
            <Header />
            <MainContent />
            <Footer />
        </div>
    )
}

ReactDOM.render(<Page />, document.getElementById("root"))
```
- <mark>styles.css below</mark>
```css
.nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.nav-logo {
    width: 60px;
}

.nav-items {
    list-style: none;
    display: flex;
}

.nav-items > li {
    padding: 10px;
}
```
### Vid 22
- Challenge was to put the code into their own files which is pretty self-explanatory.

### Vid 24
- I created my own wire frame of this project and it's stored in my Svelte Info Site iteration of this project. 

### Vid 25
- Challenge: Project Setup
    - I've had tons of practice setting up and creating the folder/file structure of a React application, with components, CSS styling etc. So there should be no question as to my proficiency at doing such.
### Vid 26
- Just goes through how to properly use Figma and the fact that I have the requisite images downloaded from Figma uploaded into this project is proof I have (at least) minimal proficiency executing this task. 

### Vid 27
- Challenge: Complete the Navbar to match the design
    - Hint: use the Figma file for the most accurate peek at the design (colors, sizes, fonts, etc.)
- <mark>Navbar.js below</mark>
```javascript
import React from "react"

export default function Navbar() {
    return (
        <nav>
            <img src="../images/react-icon-small.png" className="nav--icon" />
            <h3 className="nav--logo_text">ReactFacts</h3>
            <h4 className="nav--title">React Course - Project 1</h4>
        </nav>
    )
}
```
- <mark>style.css below</mark>
```css
nav {
    display: flex;
    align-items: center;
    background-color: #21222A;
    height: 90px;
    padding: 30px 25px;
}

.nav--logo_text, .nav--title {
    margin: 0;
}

.nav--logo_text {
    margin-right: auto;
    color: #61DAFB;
    font-weight: 700;
    font-size: 22px;
}

.nav--title {
    color: #DEEBF8;
    font-weight: 600;
}

.nav--icon {
    height: 30px;
    margin-right: 7px;
}
```
### Vid 28 
- Challenge: Build the main section!
- Skip 2 aspects of the design for now:
    1. The colored bullets in the list
    2. The larger React logo on the side
- <mark>Main.js below</mark>
```javascript
import React from "react"

export default function Main() {
    return (
        <main>
            <h1>Fun facts about React</h1>
            <ul>
                <li>Was first released in 2013</li>
                <li>Was originally created by Jordan Walke</li>
                <li>Has well over 100K stars on GitHub</li>
                <li>Is maintained by Facebook</li>
                <li>Powers thousands of enterprise apps, including mobile apps</li>
            </ul>
        </main>
    )
}
```
- I didn't include the style.css file or the progression of the styling in this video because it was as they say "old hat".

### Vid 29
- Challenge is to utilize the `::marker` CSS pseudo-element to select a marker box of a list item or bullet point (as in my case) then you just apply size and coloring accordingly.

### Vid 30
- Challenge is to render an image. 
    - You can shove it in the public folder 
    - Or you can import the image as a module like this
    - <mark>Navbar.js below</mark>
    ```javascript
    import React from "react";
    import ReactIcon from '../assets/react-icon-small.png';

    export default function Navbar() {
    return (
        <nav>
            <img src={ReactIcon} className="nav--icon" alt={"ReactIcon"} />
            <h3 className="nav--logo_text">ReactFacts</h3>
            <h4 className="nav--title">React Course - Project 1</h4>
        </nav>
    );
    }

    ```
    - <mark>style.css below</mark>
    ```css
    <!-- Factored Final Code, however if you want to move the image you just play with the directional options for each property. -->
        main {
    padding: 57px 27px;
    color: white;
    background-image: url(./images/react-icon-large.png);
    background-repeat: no-repeat;
    background-position: right 75%;
    }

    ```