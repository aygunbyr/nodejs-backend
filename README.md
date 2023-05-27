# REST API with Node, Express, Typescript & MongoDB + Authentication

I have started learning Node.js backend development therefore I followed this tutorial

[The Complete Guide To Building A REST API With Node, Express, TypeScript & MongoDB + Authentication](https://www.youtube.com/watch?v=b8ZUb_Okxro)

## Environment Setup

Create node.js project with defaults

`npm init -y`

Set up Typescript

```
npm install -D typescript
npm install -D ts-node
```

Install nodemon

`npm install -D nodemon`

Create file tsconfig.json

```
{
    "compilerOptions": {
        "module": "NodeNext",
        "moduleResolution": "node",
        "baseUrl": "src",
        "outDir": "dist",
        "sourceMap": true,
        "noImplicitAny": true,
    },
    "include": ["src/**/*"],
}
```

Create file nodemon.json

```
{
    "watch": ["src"],
    "ext": ".ts,.js",
    "exec": "ts-node ./src/index.ts"
}
```

Add to scripts in package.json

`"start": "nodemon",`

Run server

`npm start`

I added this gitignore file and renamed it as `.gitignore`

[Node.gitignore](https://github.com/github/gitignore/blob/main/Node.gitignore)

## Setup Express Server

Install modules

`npm install express body-parser cookie-parser compression cors`

Install types of modules

`npm install -D @types/express @types/body-parser @types/cookie-parser @types/compression @types/cors`

Create index.ts

```
import express from 'express'
import http from 'http'
import bodyParser from 'body-parser'
import cookieParser from 'cookie-parser'
import compression from 'compression'
import cors from 'cors'

const app = express()

app.use(cors({
    credentials: true
}))

app.use(compression())
app.use(cookieParser())
app.use(bodyParser.json())

const server = http.createServer(app)

server.listen(8080, () => {
    console.log('Server running on http://localhost:8080/')
})
```

## MongoDB Setup

Install mongoose

`npm install mongoose`

Install mongoose types

`npm install -D @types/mongoose`

Aside from that, I installed dotenv to hide my MONGO_URI for security concerns

`npm install dotenv --save`

Create .env file and add MONGO_URI

`MONGO_URI=YOUR_MONGO_URI_HERE`

Update index.ts

Import dotenv

```
import dotenv from 'dotenv'
dotenv.config()
```

Import mongoose

`import mongoose from 'mongoose'`

Add mongoose setup

```
mongoose.Promise = Promise;
mongoose.connect(process.env.MONGO_URI)
mongoose.connection.on('error', (error: Error) => console.log(error))
```
