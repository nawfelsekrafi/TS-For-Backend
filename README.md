# How to use TypeScript on backend ? 💎🔥

> TypeScript was developed by Microsoft to simplify the JavaScript code, making it easier to read and debug. Its type checking prevents many horrendous bugs during runtime. In this article, we will see how to set up typescript in the backend with NodeJS and express.

## Prerequisites

Basics of NodeJS
Basics of Express
Basics of JavaScript
Project Setup and Module Installation:

### Step 1: Run the following command in command prompt/bash/console to create a node project

```bash
npm init -y
```

### Step 2: Adding the required dependencies using the following command.

```bash
npm i express
npm i typescript ts-node @types/node @types/express --save-dev
npm i -D @types/express
```

Notice the devDependency for typescript. Typescript is only required through the development process, In the end, It will be compiled to VanillaJS for runtime. Learn more about types of dependencies.

### Step 3: Configure Typescript using the following command.

```bash
npx tsc --init
```

It will generate tsconfig.json where you can define parameters for typescript like which ECMAScript version to use (like ES3 (default), ES5, ES2015), enable strict type checking or not. Learn more about typescript configuration.

### Step 4: Creating an express server, here we have named it server.ts

# server.ts 

```ts
// Importing module
import express from 'express';

const app = express();
const PORT:Number=3000;
  
// Handling GET / Request
app.get('/', (req, res) => {
    res.send('Welcome to typescript backend!');
})
  
// Server setup
app.listen(PORT,() => {
    console.log('The application is listening '
          + 'on port http://localhost:'+PORT);
})

```

### Step 6: Configure package.json

Add the following line of code in package.json file, tsc command compiles typescript code to Vanilla JavaScript, while node server.js will take the generated Vanilla JavaScript file and start the server.

```ts
"scripts": {
 "build": "tsc",
 "start": " node server.js"
}
```

### Step 7: Run the server using the following command.

```bash
npm run build
npm start
```

Output: Now open the [http://localhost:3000](http://localhost:3000) in any browser to see the server running.

Source: [geeksForGeeks](https://www.geeksforgeeks.org/difference-between-dependencies-devdependencies-and-peerdependencies/)
