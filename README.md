## Clean project model to node and typescript

### Start the project as a node project

```
npm init -y
```

### Create and Configure the .editorconfig file as follows:

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

### Install packages in DevDependencies

```
npm install typescript ts-node-dev prettier eslint dotenv --save-dev
npm install eslint-config-prettier eslint-plugin-prettier babel-eslint --save-dev
```

### Install @types in DevDependencies
```
npm install @types/eslint @types/express @types/morgan @types/mysql @types/prettier @types/cors --save-dev
```

### Install packeges in Dependencies
```
npm install express cors morgan body-parser --save
```

### Create tsconfig.json file running the following command

```
npx tsc --init
```

### Configure the .tsconfig.json file as follows:

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

### Create .eslintrc.json file running the following command

```
npx eslint --init
```

### Configure the .eslintrc.json file as follows:

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

### Create the .gitignore file and add the following lines:

```
echo node_modules dist .env > .gitignore
```

### Create the .env and the .env.local files and add the following lines:

```
echo PROJECT_NAME= PROJECT_PORT=3000 DB_HOST=localhost DB_NAME= DB_USER=root DB_PASSWORD= DB_PORT=3306 >.env
echo PROJECT_NAME= PROJECT_PORT= DB_HOST= DB_NAME= DB_USER= DB_PASSWORD= DB_PORT= >.env.local
```

### Configure the package scripts as follows:

```
"dev": "ts-node-dev src/server.ts",
"start": "node ./dist/src/server.js",
"build": "tsc"
```

### Create the folder structure
```
mkdir src/controllers && mkdir src/models && mkdir src/routes && mkdir src/database
```

### Create the initial files
```
cd src && echo "import { express } from 'express'" > server.ts && cd ..
cd src/controllers && echo '' > name.controller.ts && cd .. && cd ..
cd src/models && echo '' > name.model.ts && cd .. && cd ..
cd src/routes && echo '' > router.ts && cd .. && cd ..
cd src/database && echo '' > db.ts && cd .. && cd ..
```
