# 🐞 **Debugging TypeScript Applications in VS Code**

Debugging is an essential skill that helps you find and fix errors in your code. With VS Code, you can **run TypeScript code line by line**, inspect variables, and understand how your code executes. Let’s walk through setting up debugging for a TypeScript project.

---

## 🎯 **Step 1: Set Up Your Project**

1️⃣ Make sure you have the following project structure:

```
hello-work/
│
├── src/
│   └── index.ts        // Your TypeScript code
│
├── dist/
│   └── index.js        // Compiled JavaScript code
│
└── tsconfig.json       // TypeScript configuration
```

2️⃣ Ensure your `tsconfig.json` is properly configured to output JavaScript files in the `dist` folder:

```json
{
  "compilerOptions": {
    "target": "ES6",
    "rootDir": "./src",
    "outDir": "./dist",
    "sourceMap": true,          // Required for debugging
    "strict": true
  }
}
```

🔹 **Note:** The `sourceMap: true` setting generates `.map` files, which map the compiled JavaScript back to the original TypeScript code—this is crucial for debugging!

---

## 🛠️ **Step 2: Writing Code to Debug**

Create a file called `index.ts` in the `src` folder:

```typescript
let age: number = 20;

if (age < 15) {
    age += 10;
} else {
    age += 5;
}

console.log(`Age after update: ${age}`);
```

---

## 🐞 **Step 3: Setting Breakpoints**

1️⃣ In **VS Code**, open `index.ts`.  
2️⃣ Click on the **left margin** next to the line numbers where you want to pause execution. A **red dot** will appear indicating a **breakpoint**.

For example, set a breakpoint at:

```typescript
let age: number = 20;  // Click here to set a breakpoint
```

---

## ⚙️ **Step 4: Configure Debugging with `launch.json`**

Now, let’s set up the debug configuration.

1️⃣ Go to the **Run and Debug** icon on the left sidebar in VS Code (or press `Ctrl+Shift+D`).  
2️⃣ Click **"create a launch.json file"**.  
3️⃣ Choose **Node.js** as the environment (since we’re running TypeScript through Node).

This creates a `.vscode/launch.json` file. Update it like this:

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "node",
      "request": "launch",
      "name": "Debug TypeScript",
      "program": "${workspaceFolder}/dist/index.js",  // Run the compiled JS file
      "preLaunchTask": "tsc: build - tsconfig.json",  // Compile TS before debugging
      "outFiles": ["${workspaceFolder}/dist/**/*.js"],  // Output folder
      "sourceMaps": true
    }
  ]
}
```

---

## 🚀 **Step 5: Running the Debugger**

1️⃣ Press **F5** to start debugging or click **Run > Start Debugging**.  
2️⃣ The execution will **pause** at the breakpoint you set.

---

## 🔍 **Step 6: Using Debugging Tools in VS Code**

Now that your debugger is running, here are some tools you can use:

### 1️⃣ **Step Over (F10)**  
Executes the current line and moves to the next one without going inside functions.

### 2️⃣ **Step Into (F11)**  
If the current line has a function call, this goes **inside the function** to debug it.

### 3️⃣ **Step Out (Shift + F11)**  
If you are inside a function, this will **exit** the function and return to the caller.

### 4️⃣ **Restart & Stop**  
- **Restart** (Ctrl+Shift+F5) will restart the debugging session.
- **Stop** (Shift+F5) will end the debugging session.

---

## 👀 **Step 7: Watching Variables**

While debugging, you can inspect the values of variables.

1️⃣ On the left side, under the **Run and Debug** panel, find the **WATCH** section.  
2️⃣ Click **"+"** to add a variable, e.g., `age`.  
3️⃣ As you **step through the code**, you’ll see how the value of `age` changes in real-time.

---

## 📝 **Example Debugging Session**

Let’s walk through an example:

1. **Set a breakpoint** at `let age: number = 20;`.
2. **Press F5** to start debugging. The execution will pause at the breakpoint.
3. **Press F10** (Step Over) to execute the line. Check the **WATCH** panel to see `age = 20`.
4. Continue stepping through the `if` condition to see how `age` is updated.

---

## 🎯 **Final Thoughts**

- Debugging TypeScript in VS Code is powerful thanks to **source maps** and integrated tools.
- Setting **breakpoints** and using **step tools** help you find exactly where things go wrong.
- Use the **WATCH** panel to monitor variables and understand the flow of your code.
