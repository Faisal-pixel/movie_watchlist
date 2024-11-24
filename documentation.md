# To install typescript for the backend
1. <b>Install TypeScript and Required Packages</b>
```bash
npm install typescript ts-node @types/node --save-dev
```
- typescript: TypeScript compiler.
- ts-node: Allows you to run TypeScript files directly in development without compiling them.
- @types/node: Type definitions for Node.js.

2. <b>Initialize TypeScript Configuration</b>
```bash
npx tsc --init
```
3. <b>Update TypeScript Configuration</b>
- Open the tsconfig.json file and update the following properties:
```json
{
  "compilerOptions": {
    "target": "ES6",                           // JavaScript version to output
    "module": "commonjs",                      // Module system for Node.js
    "strict": true,                            // Enable all strict type-checking options
    "esModuleInterop": true,                   // Makes importing modules easier
    "outDir": "./dist",                        // Output directory for compiled files
    "rootDir": "./src",                        // Input directory for source files
    "resolveJsonModule": true,                 // Allow importing JSON files
    "skipLibCheck": true                       // Skip checking type definitions
  },
  "include": ["src/**/*"],                     // Include all files in the src folder
  "exclude": ["node_modules", "dist"]          // Exclude unnecessary files
}

```

# Folder Structure for the Backend
my-backend/
│
|── node-modules/         # Node.js modules
├── src/                  # Contains most of my code. Basically the source code
│   ├── index.ts          # Entry point for your backend. The starting point for the application
│   ├── routes/           # Optional folder for routes. A folder containing all the different route/endpoint.
│   ├── Config/           # Optional folder for configuration files. Stores the configuration files.
│   ├── db/               # Optional folder for database files. Database COnfiguration
│   └── middleware/       # Optional folder for middleware files. Middleware functions
|   └── utils/            # Optional folder for utility files. These will contain utility functions
│
├── tsconfig.json         # TypeScript configuration file
├── package.json          # Node.js configuration file
└── package-lock.json     # Node.js configuration file

# Installing Express for ts
```bash
npm install express @types/express
```

# Using typescript with nodemon
1. <b>Update the "main" field</b> in the package.json file. ```json"main": "src/index.ts"```
2. <b>Add a dev script in pacjage.json</b>
```json
"scripts": {
  "dev": "nodemon src/index.ts"
}
```
3. <b> Create nodemon.json and configure</b>
```json
{
    "exec": "ts-node ./src/index.ts",
    "ext": "ts,js,json",            
    "ignore": ["dist/*"],
    "watch": ["src"]
}
```
4. In the package.json file, remove "type": "module" and ensure you are using the correct setup for ES module compatibility with TypeScript.Add "module": "NodeNext" in tsconfig.json file.