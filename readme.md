# 📘 Web Development Basics – Notes Summary 

This README contains detailed notes and summaries based on commonly asked web development questions, tools, and files. Useful for quick reference or GitHub documentation.

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

