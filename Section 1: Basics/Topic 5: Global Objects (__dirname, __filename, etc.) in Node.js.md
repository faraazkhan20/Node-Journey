### Topic 5: Global Objects (`__dirname`, `__filename`, etc.) in Node.js

Node.js provides several built-in global objects that are always available in every module without needing to import them. These globals make it easier to interact with your program’s environment, file paths, and more. Unlike browser JavaScript, Node.js runs in its own module system, so it provides some special global variables like `__dirname`, `__filename`, `module`, `exports`, and `require`.

Let’s start with `__dirname`. This global variable always contains the **absolute path** of the directory where the currently executing script resides. For example, if your script is located at `C:\Projects\myapp\index.js`, `__dirname` will return `C:\Projects\myapp`.

Create a file called `pathTest.js` and write:

```js
console.log("Current directory:", __dirname);
```

Run it using:

```bash
node pathTest.js
```

You’ll see the full directory path of where the file is saved. This is useful when you want to work with files relative to your script, especially in file operations like reading or writing.

Now, let’s look at `__filename`. This one gives you the **absolute path to the actual file**, including its name. Modify your file to add:

```js
console.log("Current file:", __filename);
```

When run, this will print the full path including the filename, such as `C:\Projects\myapp\pathTest.js`.

These globals are helpful when building file systems or server-side logic that depends on file locations. They are particularly useful when working with Node’s `fs` or `path` modules.

For example, to join a file path using the `path` module:

```js
const path = require('path');

const filePath = path.join(__dirname, 'data', 'info.txt');
console.log("Generated path:", filePath);
```

This ensures your file path is correct no matter the operating system or script location.

Other key global objects in Node.js include:

* `require`: A function used to load external modules.
* `module`: Represents the current module.
* `exports`: An object used to export functions or variables from a module.

For example:

```js
console.log("Module object:", module);
console.log("Exports object:", exports);
```

Though these aren’t traditional objects like `__dirname`, they are part of Node’s module system and help you organize your code.

In conclusion, `__dirname` and `__filename` give you powerful, absolute path references to your files and folders. Understanding and using these globals properly is essential for building scalable, file-aware Node.js applications. They help avoid hardcoding paths and make your code more flexible and portable.
