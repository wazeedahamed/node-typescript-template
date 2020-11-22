# Node typescript template

Node template with preset typescript development environment

## Initial setup

Run below command to install node dependencies for typescript

> npm install

## Development

Run below command to start node project in development mode

> npm run start:dev

## Production build

Run below command to build node project for production. Build files will be placed in `build` folder

> npm run start

## Clone repository

> git clone https://github.com/wazeedahamed/node-typescript-template.git

## Manual Setup

Below are the commands (windows command prompt) to setup the template manually. Reference [typescript/node-starter-project](https://khalilstemmler.com/blogs/typescript/node-starter-project/ "Node Starter Project")

* Create a project folder. Open command prompt and run below command

    > mkdir `<<project_folder_name>>`

    > cd `<<project_folder_name>>`

* Create Package.json

    > npm init -y

* Add Typescript

    > npm install typescript --save-dev

* Add Node Types

    > npm install @types/node --save-dev

* Add `rimraf`

    > npm install rimraf --save-dev

* Create Typescript configuration

    > npx tsc --init --rootDir src --outDir build --esModuleInterop --resolveJsonModule --lib es6 --module commonjs --allowJs true --noImplicitAny true

* Create `src` folder and `index.ts` file

    > mkdir src
    > echo. > src\index.ts

* Add `ts-node` and `nodemon`

    > npm install --save-dev ts-node nodemon

* Configure `nodemon`

    > echo { "watch": ["src"], "ext": ".ts,.js", "ignore": [], "exec": "ts-node ./src/index.ts" } > nodemon.json

* Open `package.json` and add below scripts

    

``` json
    {
        "scripts": {
            "start:dev": "nodemon",
            "build": "rimraf ./build && tsc",
            "start": "npm run build && node build/index.js"
        }
    }
    ```
