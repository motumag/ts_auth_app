# How to setup typescript project

A simple Node.js project set up with TypeScript, ES Modules, and Nodemon for easy development. This guide will help you set up the environment for development in Visual Studio Code.

## Prerequisites

- [Node.js](https://nodejs.org/) installed
- [npm](https://www.npmjs.com/get-npm) or [yarn](https://classic.yarnpkg.com/en/docs/install) installed
- [Visual Studio Code](https://code.visualstudio.com/) installed

## Getting Started

### 1. Initialize the Project

```bash
mkdir my-typescript-project
cd my-typescript-project
npm init -y
```

### 2. Install Dependencies and compile the using tsc

```bash
npm install --save-dev typescript @types/node nodemon ts-node
npx tsc --init
```

### 3. Now setup the tsconfig.json file with your owun requirement, module or commonjs

```bash
{
  "compilerOptions": {
    "target": "ES2020",
    "module": "ES2020",
    "outDir": "./dist",
    "rootDir": "./src",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "moduleResolution": "node"
  },
  "include": ["src/**/*"],
  "exclude": ["node_modules"]
}
```

### 4. Create Your Project Structure and index.ts file

```bash
mkdir src
touch /src/index.ts
// src/index.ts

const greeting: string = "Hello, TypeScript with ES Modules and Nodemon!";
console.log(greeting);


```

### 5. Update package.json

```bash
 "scripts": {
    "start": "node dist/index.js",
    "build": "tsc",
    "dev": "nodemon --watch 'src/**/*.ts' --exec 'ts-node' src/index.ts"
  },
```

### 6. Run the app

```bash
npm run dev
```
