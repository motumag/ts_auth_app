[x]. How to setup typescript with nodejs project?
[1]. mkdir my-typescript-project
[2]. cd my-typescript-project
[3]. npm init -y
[4]. npm install --save-dev typescript @types/node nodemon ts-node
[5]. npx tsc --init

[6]. {
"compilerOptions": {
"target": "ES2020", // ECMAScript target version
"module": "ES2020", // Use ES Modules
"outDir": "./dist", // Output directory for compiled files
"rootDir": "./src", // Root directory for source files
"strict": true, // Enable strict type-checking
"esModuleInterop": true, // Enable compatibility between CommonJS and ES Modules
"skipLibCheck": true, // Skip checking of declaration files
"moduleResolution": "node" // Resolve modules based on Node.js
},
"include": ["src/**/*"],
"exclude": ["node_modules"]
}

[7]. my-typescript-project/
├── src/
│ └── index.ts
├── package.json
├── tsconfig.json
└── node_modules/

[8]. // src/index.ts
const greeting: string = "Hello, TypeScript with ES Modules and Nodemon!";
console.log(greeting);

[9]. {
"name": "my-typescript-project",
"version": "1.0.0",
"main": "dist/index.js",
"type": "module",
"scripts": {
"start": "node dist/index.js",
"build": "tsc",
"dev": "nodemon --watch 'src/\*_/_.ts' --exec 'ts-node' src/index.ts"
},
"devDependencies": {
"typescript": "^X.X.X",
"@types/node": "^X.X.X",
"nodemon": "^X.X.X",
"ts-node": "^X.X.X"
}
}
