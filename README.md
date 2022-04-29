# Clean project model to node and typescript

### 1 - Create .editorconfig file

### 2 - Configure the .editorconfig file as follows:

```
root = true
[*]
indent_style = space
indent_size = 2
end_of_line = crlf
charset = utf-8
trim_trailing_whitespace = false
insert_final_newline = true
```

### 3 - Install typescript and the prettier in dev mode

```
npm install typescript ts-node-dev @types/express prettier --save-dev
```

### 4 - Create tsconfig.json file running the following command

```
npx tsc --init
```

### 5 - Configure the .tsconfig.json file as follows:

```
{
  "compilerOptions": {
    "target": "es2016",
    "module": "commonjs",
    "esModuleInterop": true,
    "forceConsistentCasingInFileNames": true,
    "strict": false,
    "skipLibCheck": true,
    "outDir": "./dist"
  }
}
```

### 6 - Install eslint package

```
npm install eslint --save-dev
```

### 7 - Create .eslintrc.json file running the following command

```
npx eslint --init
```

### 8 - Configure the .eslintrc.json file as follows:

```
{
  "env": {
    "browser": true,
    "commonjs": true,
    "es2021": true
  },
  "extends": [
    "standard", "prettier"
  ],
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaVersion": "latest"
  },
  "plugins": [
    "@typescript-eslint", "prettier"
  ],
  "rules": {
    "prettier/prettier": "error"
  }
}
```

### 9 - Install eslint config packages

```
npm install eslint-config-prettier eslint-plugin-prettier babel-eslint --save-dev
```

### 10 - Create the .gitignore file and add the following lines:

```
node_modules
dist
.env
```

### 11 - Create the .env and the .env.local files and add the following lines:

```
PROJECT_NAME=''
PORT=''
```

### 12 - Configure the package scripts as follows:

```
"dev": "ts-node-dev src/server.ts",
"start": "node ./dist/src/server.js",
"build": "tsc"
```
