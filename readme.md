# 📘 React Basics – Notes Summary 

---

## 📦 `package-lock.json`

### What is it?
`package-lock.json` is an auto-generated file by **npm** that locks the exact versions of installed packages and their sub-dependencies.

### ✅ Purpose:

- Ensures consistent installs across devices and teams  
- Records exact versions and nested dependencies  
- Improves installation speed  
- Prevents bugs from mismatched package versions  

### Summary:

> Ensures repeatable builds and dependency stability.

---

## 🧾 `manifest.json`

### What is it?
A JSON file that defines metadata for a **Progressive Web App (PWA)**.

### ✅ Key Uses:

- App name, short name  
- Icons (for home screen)  
- Theme/background color  
- Display behavior (fullscreen, standalone, etc.)

### Summary:

> Helps browsers install your web app and control how it looks/behaves when launched.

---

## 🤖 `robots.txt`

### What is it?
A plain text file that tells **search engine bots** which parts of your website to crawl or not crawl.

### ✅ Example:

User-agent: *
Disallow: /admin/
Allow: /public/


### Summary:

> Controls which pages search engines can index and which they should ignore.

---

## 🕷️ What is Crawling?

### Definition:
Crawling is when search engine bots **visit and read your site** to understand its content.

### Process:

- Bot visits site (crawl)  
- Reads page content  
- Stores it (indexing)  
- Ranks it in search results  

### Summary:

> Crawling is the first step before indexing and ranking your site.

---

## 📦 Is HTML Bundled?

### No.

HTML is **not bundled** like JS or CSS. It is the **entry point** of a web app.

### Why?

- HTML is used to load other files (like JS and CSS)  
- Browsers read HTML directly, so bundling it isn’t necessary  

### Summary:

> HTML is the main guide; JS and CSS are the tools being optimized.

---

## 🏗️ Why React Needs a Bundler (But Vanilla JS Doesn’t)

| Feature                 | HTML/CSS/JS | React               |
| ----------------------- | ----------- | ------------------- |
| Uses JSX                | ❌ No        | ✅ Yes               |
| Modules (import/export) | ❌ No        | ✅ Yes               |
| Needs compilation       | ❌ No        | ✅ Yes (via bundler) |
| Browser-ready           | ✅ Yes       | ❌ No                |

### Summary:

> React uses JSX and modules that the browser can't understand directly. So, a bundler like **Vite** is needed.

---

## ⚡ What is Vite?

### Definition:

> **Vite** is a frontend build tool and development server. It compiles, bundles, and serves modern JavaScript apps.

### Key Features:

- Lightning-fast dev server  
- Modern JS & module support  
- Supports React, Vue, etc.  
- Fast production builds  

### Summary:

> Vite is a **tool**, not a library. It helps bundle and serve frontend apps.

---

## 📚 What is a Library vs Framework?

### Library:

- A set of functions you call  
- You control the flow  
- Example: **React, Axios**

### Framework:

- Framework controls the flow, calls your code  
- More opinionated  
- Example: **Angular, Next.js**

### Analogy:

> **Library = Cool buddy you ask for help**  
> **Framework = Military general who gives orders**

---

## 📄 What is `npx` vs `npm`?

| Tool  | What it Does                              |
| ----- | ----------------------------------------- |
| `npm` | Installs packages globally or locally     |
| `npx` | Executes packages without installing them |

### Summary:

> `npx` runs a package **temporarily**. `npm` installs it to your project.

---

## 🌐 How a Web Page is Loaded – Full Flow

### 🧠 Step-by-Step:

1. **User Enters URL:**  
   - Browser sends a request to DNS to resolve the domain to an IP address.

2. **DNS Resolution:**  
   - DNS server responds with IP of the web server.

3. **Browser Sends HTTP Request:**  
   - Browser makes a GET request to server (e.g., `index.html`).

4. **Server Responds:**  
   - Sends back HTML file.  
   - HTML includes links to CSS and JS.

5. **Browser Parses HTML:**  
   - Builds the **DOM Tree** (Document Object Model).

6. **CSS Is Loaded:**  
   - Builds the **CSSOM Tree** (CSS Object Model).

7. **JS Is Loaded:**  
   - JS is parsed and executed using the **JavaScript engine** (like V8).  
   - DOM can be modified using JS (e.g., React rendering components).

8. **Rendering Phase:**  
   - DOM + CSSOM → Render Tree  
   - Layout and paint happen.

9. **User Sees the Page.**

### Notes:
- In React, we only write `.js/.jsx` code, but React creates real HTML & CSS under the hood using JavaScript DOM APIs.  
- Browsers don’t convert JS to HTML; rather, JS **manipulates** the DOM.

### Summary:
> A webpage is loaded through a series of steps starting from DNS resolution to rendering, and JavaScript (like React) plays a key role in making the page dynamic.

---

Yes! ✅ You understood it exactly right — and here’s the full explanation with proper notes formatting for your GitHub or Notion documentation:

---

## 🚀 What Happens When You Push a Project Without `node_modules` to GitHub?

### 📦 Step-by-Step:

1. You create a React/Node project:

   * It generates `package.json`, `package-lock.json`, and a `node_modules` folder.

2. You **add `.gitignore`**, which ignores `node_modules` (because it's too large and can be regenerated).

3. You push only:

   * `package.json` (📃 tells which packages to install)
   * `package-lock.json` (🔒 locks exact versions)

4. Someone else **clones** your project and runs:

```bash
npm install
```

✅ Result:
They will get the **same versions** of packages that you used, because `package-lock.json` tells npm to install **exact versions**.

---

## 🛑 What If You Don’t Have `package-lock.json`?

* Then `npm` may install slightly **newer versions** (if `^` is used in `package.json`), which could lead to:

  * Bugs
  * Inconsistencies between environments

---

## 🧠 Summary for Notes:

> When you push a project to GitHub **without `node_modules`**, as long as you include `package-lock.json`, other developers can run `npm install` and get the **exact same versions** of packages, ensuring the app behaves the same everywhere.

---

Ah! Yes — you heard right. React **does have its own DOM**, but it's not the same as the browser's real DOM. Here's a simple, clear explanation for your notes:

---

## 🧠 React DOM vs Browser DOM

### 🔸 What is the **Browser DOM**?

The **Document Object Model (DOM)** is how the browser represents your HTML page as a **tree structure**. You can use JavaScript to:

* Add/remove elements
* Change styles
* Update text
* React to clicks, etc.

---

### 🔹 What is the **React DOM**?

> React doesn’t directly update the **Browser DOM**.
> Instead, it creates a **Virtual DOM** — a copy of the browser’s DOM in memory.

### 🧊 Virtual DOM = React's Own DOM

React uses this **Virtual DOM** to:

* Track what your UI should look like
* Compare it with the previous version
* Efficiently update **only the parts that changed** in the real DOM

---

### 📊 Summary Table

| Feature           | Browser DOM      | React Virtual DOM         |
| ----------------- | ---------------- | ------------------------- |
| Exists in memory? | ❌ No             | ✅ Yes                     |
| Created by        | Browser          | React                     |
| Faster updates?   | ❌ No (expensive) | ✅ Yes (optimized diffing) |
| Directly visible? | ✅ Yes            | ❌ No (internal to React)  |

---

### ✅ Final Summary (for your notes):

> React uses its own **Virtual DOM**, a lightweight in-memory copy of the real Browser DOM. React updates this Virtual DOM first, then efficiently updates only the changed parts in the actual Browser DOM. This makes React fast and efficient.

---

Great! Let’s break down **what a component is** in **React** — in a simple, clear way for your notes.

---

## 🧱 What is a Component in React?

### 🔸 Simple Definition:

A **component** is a **reusable block of code** that represents a part of the user interface (UI).

Think of components like **Lego blocks**:
You build your full app by combining many small, individual components.

---

### 🧠 Example:

```jsx
function Welcome() {
  return <h1>Hello, React!</h1>;
}
```

This is a **React component**. It returns JSX (like HTML) and can be reused anywhere.

---

### 📦 Types of Components:

1. **Functional Component** (most common)

   ```jsx
   function Button() {
     return <button>Click Me</button>;
   }
   ```

2. **Class Component** (older style)

   ```jsx
   class Button extends React.Component {
     render() {
       return <button>Click Me</button>;
     }
   }
   ```

---

### 🔁 Reusability:

Once created, you can use a component like a tag:

```jsx
<App />
<Header />
<Footer />
```

Just like using custom HTML elements!

---

### ✅ Summary for Notes:

> A **React component** is a small, reusable piece of UI. It can be a button, a form, a navbar, or an entire page. You write components using functions (or classes) and combine them to build full applications.

---

Yes! In React, a **functional component** is just a **JavaScript function** — but with one key difference:

👉 It **returns JSX** — a special syntax that looks like HTML but is actually JavaScript.

---

## 🧠 What Does a React Functional Component Return?

A functional component **returns** the UI (in the form of JSX) that you want to show on the screen.

### 🔹 Example:

```jsx
function Hello() {
  return <h1>Hello, world!</h1>;
}
```

* `Hello` is a function ✅
* It returns `<h1>Hello, world!</h1>` — **JSX**, not HTML

---

### 🧬 JSX is Not HTML

* It looks like HTML but it's actually **JavaScript syntax**.
* Behind the scenes, React converts this JSX into `React.createElement()` calls, which build the **Virtual DOM**.

---

### 🔄 React then:

1. Converts JSX into JavaScript objects (virtual DOM nodes)
2. Figures out what changed
3. Updates the real DOM accordingly

---

### ✅ Summary (for your notes):

> A **React functional component** is a JavaScript function that **returns JSX** — a syntax that describes the UI. React uses this to render parts of the screen.

---

✅ Yes, that’s a great way to think about it — in **React**, we are essentially giving **HTML programming abilities**.

---

## 🧠 React = HTML + JavaScript Combined

In traditional web development:

* HTML describes the **structure** (what to show)
* CSS styles it (how it looks)
* JavaScript adds **behavior** (what it does)

---

### 🧩 In React:

You combine **HTML-like syntax (JSX)** with **JavaScript logic** inside one file/component.

---

### 🔥 Why is This Powerful?

Because in React:

| Without React                | With React                      |
| ---------------------------- | ------------------------------- |
| HTML is static               | JSX can be dynamic              |
| JS updates DOM manually      | React updates DOM for you       |
| HTML can’t have conditions   | JSX supports `if`, `map`, etc.  |
| Code is scattered (HTML, JS) | Code is organized in components |

---

### ✨ Example:

```jsx
function Greet(props) {
  return <h1>Hello, {props.name}!</h1>;
}
```

* Looks like HTML (`<h1>`)
* Acts like JavaScript (`{props.name}` is JS)
* Reusable like a function

---

### ✅ Summary for Notes:

> React gives **HTML programming power** by allowing you to write **JSX**, where you mix HTML-like tags with JavaScript logic. This makes UI building dynamic, reusable, and powerful.

Ahh got it! You're asking whether `<Tab />` is a **tag**, **JSX**, or something else — and how it actually works when used. Let's break it down simply 👇

---

## 🔍 Is `<Tab />` a Tag or JSX?

✅ `<Tab />` is **JSX** syntax — not an HTML tag.
It's a **React component** being used like a tag.

> JSX (JavaScript XML) lets you write code that **looks like HTML**, but it's actually **JavaScript under the hood**.

---

## 🧱 What Happens Behind the Scenes?

When you write this:

```jsx
<Tab />
```

React internally converts it into:

```js
React.createElement(Tab)
```

This means:

* It **calls the `Tab` function** (or class, if it's a class component)
* Whatever JSX that `Tab` returns, **gets inserted into the DOM**

---

## 🔁 Example Flow

### Step 1: Create Component

```jsx
function Tab() {
  return <div>This is a Tab Component</div>;
}
```

### Step 2: Use It

```jsx
<App>
  <Tab />
</App>
```

### Step 3: React Translates

Internally, React converts:

```jsx
<Tab />
```

into:

```js
React.createElement(Tab, null)
```

Which executes:

```js
Tab() → returns JSX → inserted into DOM
```

---

## 💡 Will Code Be Injected Over There?

Yes — the **returned JSX** from `Tab()` will be **injected/rendered** exactly where `<Tab />` was written.

---

## ✅ Summary for Notes:

> `<Tab />` is not an HTML tag — it is **JSX** used to render a React component. React turns it into `React.createElement(Tab)` and injects the component’s returned JSX into the DOM where the tag appears.

---

Let me know if you want to see what it would look like on an actual HTML page!





