# 📁 **Creating and Compiling a TypeScript Project in VS Code**  

In this guide, we'll create a new **TypeScript project** called `hello-work` on your desktop, learn how to **compile** TypeScript code, and see how **TypeScript helps catch errors** before runtime! 🛠️

---

## 🎯 **Step 1: Creating the Project Folder**

1️⃣ Go to your **Desktop** folder and create a new folder for your project.

### **Commands to Create the Project Folder:**
```bash
cd Desktop
mkdir hello-work
cd hello-work
```

🔹 **Note:** You can name the folder **anything you like**. Here, we’ve named it `hello-work`.

---

## 🛠️ **Step 2: Opening the Project in VS Code**

1️⃣ Open **VS Code**.  

2️⃣ Drag and drop the `hello-work` folder into **VS Code** to open it as a project.

3️⃣ Alternatively, you can open the folder directly from the terminal:

```bash
code .
```

---

## 🖥️ **Step 3: Using the Terminal in VS Code**

You can use the **integrated terminal** in VS Code to run commands.

1️⃣ In VS Code, go to **View > Terminal**.  
2️⃣ **Shortcut:**  
   - On **Mac**: `Control + \` (backtick)  
   - On **Windows/Linux**: `Ctrl + ~`

This opens a terminal window at the bottom of VS Code.

---

## 📄 **Step 4: Writing Your First TypeScript File**

1️⃣ Create a new file named `index.ts` in your project folder.

2️⃣ Add the following TypeScript code:

```typescript
// Declaring a variable with a type annotation
let age: number = 25;  // This variable can only hold numbers

// Trying to assign a string will cause an error
age = "twenty-five";  // ❌ Error: Type 'string' is not assignable to type 'number'

console.log(`Your age is ${age}`);
```

---

## 🔎 **Step 5: Compiling the TypeScript File**

Now that we’ve written our code, let’s compile it using the **TypeScript compiler**.

### **Compile the Code:**
```bash
tsc index.ts
```

🔹 This command creates an `index.js` file in your project folder, which contains the compiled JavaScript code.

---

## 🚨 **Understanding TypeScript Error Handling**

Because we declared `age` as a **number**, TypeScript **won't allow** assigning a **string** to it. This is the beauty of TypeScript—it catches these errors **before** running the code.

### **Error Example:**
```bash
index.ts:5:6 - error TS2322: Type 'string' is not assignable to type 'number'.

5 age = "twenty-five";
       ~~~~~~~~~~~~~~
```

---

## 🏁 **Step 6: Running the Compiled JavaScript File**

After compiling, you can run the JavaScript file using **Node.js**.

### **Run the JavaScript File:**
```bash
node index.js
```

🔹 **Output (if no errors):**
```
Your age is 25
```

---

## ⚙️ **Bonus: Configuring the TypeScript Compiler for Modern JavaScript**

By default, the TypeScript compiler targets **older JavaScript versions** (ES5). To take advantage of **modern JavaScript features**, we need to configure TypeScript.

### 1️⃣ **Generate a TypeScript Configuration File (`tsconfig.json`):**
```bash
tsc --init
```

This creates a `tsconfig.json` file in your project folder.

### 2️⃣ **Update the Configuration:**

Open the `tsconfig.json` file and modify the `target` property to use **ES6** (or a later version):

```json
{
  "compilerOptions": {
    "target": "ES6",
    "module": "commonjs",
    "strict": true
  }
}
```

Now, when you compile your TypeScript code, it will target **modern JavaScript features**! 🎉

---

## 🎯 **Final Thoughts**

- **TypeScript** helps catch errors at **compile time**, preventing many runtime issues.  
- It provides **type safety** and allows you to write **cleaner, more maintainable code**.  
- Configuring TypeScript to target modern JavaScript lets you take advantage of **newer features** while ensuring compatibility.

---
