# LESSON ONE - Node.js Generalities #

## 1. Introduction ##
**Node.js** is an open-source, cross-platform, server-side JavaScript runtime built on Google Chrome’s **V8 engine**. It was created by **Ryan Dahl** in **2009** to enable fast, scalable, and efficient web applications using JavaScript beyond the browser environment.

Node.js allows developers to build applications such as APIs, real-time chat systems, video streaming platforms, and single-page applications (SPAs). Unlike traditional desktop software, which requires installation and maintenance, web-based applications built with Node.js can be updated directly on the server—ensuring seamless distribution and version control.

---

## 2. Why Node.js Exists ##
Historically, desktop applications offered direct access to hardware resources (CPU, file system, etc.) but required complex installation and updates. Web development simplified distribution—apps run directly in browsers and are centrally updated.

However, frontend developers using **JavaScript** faced challenges when building backend systems, which traditionally required learning other languages like **Java** or **C#**. Node.js addressed this gap by bringing JavaScript to the backend, powered by Chrome’s **V8 engine**, allowing full-stack JavaScript development using a single language across client and server.

---

## 3. Core Features ##
| Feature                                 | Description                                                                         |
| --------------------------------------- | ----------------------------------------------------------------------------------- |
| **Asynchronous & Event-Driven**         | Uses an event loop to manage I/O efficiently without blocking execution.            |
| **Single-Threaded with Worker Threads** | Handles multiple connections concurrently using non-blocking operations.            |
| **Cross-Platform**                      | Works on Windows, macOS, and Linux.                                                 |
| **Scalable**                            | Ideal for real-time apps requiring many concurrent connections (e.g., chat, games). |
| **Lightweight**                         | Uses minimal resources by streaming data instead of buffering.                      |

### When Node.js Excels ###
- Real-time communication apps (e.g., chat, live updates)
- APIs and microservices
- Streaming services (video/audio)
- Lightweight, data-driven applications

### When to Avoid Node.js ###
- Applications requiring heavy CPU-bound computations (e.g., image processing, machine learning)

---

## 4. Node.js Architecture ##

### Event Loop ###
Node.js operates on a **single-threaded event loop**. It delegates asynchronous tasks (file I/O, network requests, etc.) to background threads handled by **libuv**, while continuing to execute other code. When operations complete, their callbacks are queued and executed when the main stack is free.

### Threads and Processes ###
| Concept     | Description                                                   |
| ----------- | ------------------------------------------------------------- |
| **Process** | An instance of a running program.                             |
| **Thread**  | A unit of execution within a process sharing the same memory. |

Node.js uses **worker threads** and the **cluster module** to offload CPU-bound operations and leverage multi-core CPUs for scalability.

### Streaming and Non-Buffering ###
Node.js sends data in chunks (“data streams”) rather than buffering entire responses. For example, video streams start playing before the full file is downloaded—improving performance and responsiveness.

---

## 5. Comparison with Other Technologies ##

| Technology  | Model                      | Best Use Case                        |
| ----------- | -------------------------- | ------------------------------------ |
| **Node.js** | Asynchronous, event-driven | Real-time and I/O-heavy apps         |
| **Nginx**   | Asynchronous reverse proxy | Load balancing, static file delivery |
| **Apache**  | Multi-thread/process-based | Static content, traditional hosting  |

Nginx is often used as a **reverse proxy** in front of Node.js for handling static assets and distributing requests efficiently.

---

## 6. Modularity and Package Management ##

### Built-in Modules ###
Node.js includes core modules like:
- `fs` (File System)
- `http` (Networking)
- `url` (URL handling)
- `path` (File paths)

Modules are imported using:
```js
const fs = require('fs');
```
Modules expose functionalities through `module.exports`. Once imported, Node.js caches them to improve performance.

### Node Package Manager (npm) ###
**npm** is the official package manager for Node.js. It allows developers to:
- Install external libraries and dependencies.
- Manage project metadata with `package.json`.
- Create and share reusable packages.
- Automate tasks via custom scripts.

---

## 7. Node.js Project Setup (with TypeScript) ##

1. Create a new project folder and open it in **VS Code**.  
2. Initialize the Node.js project:  
   ```bash
   npm init -y
   ```
3. Create a `src` folder and add your source files.  
4. Install TypeScript tools:  
   ```bash
   npm install --save-dev typescript ts-node
   ```
5. Generate a TypeScript configuration file:  
   ```bash
   npx tsc --init
   ```
6. Edit **tsconfig.json** to include:  
   ```json
   {
     "compilerOptions": {
       "rootDir": "./src",
       "outDir": "./dist"
     }
   }
   ```
7. Update **package.json** with scripts:  
   ```json
   {
     "scripts": {
       "start": "ts-node ./src/app.ts",
       "build": "tsc"
     }
   }
   ```
8. Build and run the project:  
   ```bash
   npm run build
   npm start
   ```
9. Add a `.gitignore` file to exclude `node_modules`.  

---

## 8. Common Tools and Extensions ##
| Tool                               | Description                                   |
| ---------------------------------- | --------------------------------------------- |
| **Visual Studio Code (VSC)**       | Recommended editor for Node.js and TypeScript |
| **Node Snippets**                  | Provides code templates for Node.js           |
| **npm Intellisense**               | Suggests installed module imports             |
| **JavaScript/TypeScript Snippets** | Offers auto-completion and hints              |

---

## 9. Useful Links ##
- https://node.org/en  
- https://rust-lang.org/  
- https://survey.stackoverflow.co/2025/  
- https://github.com/Ichbin-123/node-basic.git  

---

## 10. Console Commands Reference ##
1. `node -v` // Check Node.js version  
2. `where node` // Show Node.js installation path  
3. `npm init -y` // Create default package.json  
4. `npm install --save-dev typescript ts-node` // Install TypeScript tools  
5. `npx tsc --init` // Create tsconfig.json file  
6. `npx tsc` // Compile all TypeScript files  
7. `node ./dist/app.js` // Run compiled JavaScript file  
8. `npx ts-node ./src/app.ts` // Run TypeScript file directly  
9. `npm run build` // Build project  
10. `npm start` // Run project  
11. `Ctrl + Shift + P` // Open VS Code command palette  

---

*End of Class Notes Summary*