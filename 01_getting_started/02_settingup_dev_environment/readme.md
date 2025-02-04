# 🚀 **Setting Up TypeScript with Node.js & npm**  

Welcome to this setup guide! In this section, we’ll walk through how to install and configure **TypeScript** using **Node Package Manager (npm)**. By the end, you'll be ready to start writing and running TypeScript code in **Visual Studio Code (VS Code)**! 🖥️✨  

---

## 🎯 **Why Do We Need Node.js and npm?**  

To run **TypeScript**, we need a **TypeScript compiler (tsc)**, which helps convert `.ts` files into `.js` files. To install this compiler, we use **npm (Node Package Manager)**, which comes bundled with **Node.js**.

📌 **In short:**  
- **Node.js** is the runtime that lets JavaScript run outside the browser.  
- **npm** is a tool that helps us install packages like TypeScript.

---

## 🛠️ **Step-by-Step Setup Guide**  

### 1️⃣ **Install Node.js**  

First, we need to install **Node.js**. If you already have Node.js, you can skip this step.  

1. Go to the **[official Node.js website](https://nodejs.org/)**. 🌐  
2. Download the **latest version** of Node.js for your operating system.  
3. Follow the installation instructions provided on the website.  

### 2️⃣ **Verify Node.js & npm Installation**  

Once installation is complete, open your terminal and type the following commands to verify that Node.js and npm are installed correctly:

```bash
node -v
```
This will display the **Node.js version** installed on your machine. Example output:
```
v18.12.1
```

Now check if **npm** is installed:
```bash
npm -v
```
Example output:
```
9.5.0
```

---

### 3️⃣ **Install TypeScript Compiler**  

Now that Node.js and npm are installed, let’s install the **TypeScript compiler** globally on your system.

Run this command in the terminal:
```bash
npm install -g typescript
```
The `-g` flag installs TypeScript globally, meaning you can use it in any project without reinstalling.

---

### 4️⃣ **Verify TypeScript Installation**  

After the installation, you can check the TypeScript version to confirm everything is working:

```bash
tsc -v
```
Example output:
```
Version 4.6.3
```
🎉 **Congratulations!** You now have TypeScript installed on your machine.

---

## 🗂️ **Setting Up a New TypeScript Project**  

Now that TypeScript is installed, let’s create a project.

### 1️⃣ **Create a New Folder**  
In your terminal, navigate to the location where you want to create your project and run:

```bash
mkdir my-typescript-project
cd my-typescript-project
```

### 2️⃣ **Initialize npm in Your Project**  
To manage project dependencies, initialize npm:

```bash
npm init -y
```
This will create a `package.json` file, which keeps track of your project dependencies.

### 3️⃣ **Install TypeScript Locally (Optional)**  
Though we installed TypeScript globally, it’s a good practice to install it locally for each project:

```bash
npm install typescript --save-dev
```

---

## 📝 **Writing Your First TypeScript Program**  

### 1️⃣ **Open VS Code**  
Open your project folder in **Visual Studio Code**:

```bash
code .
```

### 2️⃣ **Create a TypeScript File**  
Create a file named `index.ts` and write the following code:

```typescript
function greet(name: string): string {
    return `Hello, ${name}!`;
}

console.log(greet("Sadia")); // Output: Hello, Sadia!
```

### 3️⃣ **Compile the TypeScript File**  
To compile `index.ts` into JavaScript, run the following command in the terminal:

```bash
tsc index.ts
```

This will create an `index.js` file in your folder. 🎉

### 4️⃣ **Run the Compiled JavaScript File**  
Now, run the compiled JavaScript file using Node.js:

```bash
node index.js
```

**Output:**
```
Hello, Sadia!
```

---

## ⚙️ **Bonus: Auto-Compile with TypeScript Watch Mode**  

To make development faster, you can use the **watch mode**, which automatically compiles your TypeScript files when changes are detected.

Run this command:
```bash
tsc --watch
```

Now, whenever you save changes to your `.ts` file, it will automatically compile! 🔥

---
