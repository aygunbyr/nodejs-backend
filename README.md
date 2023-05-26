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

Create file `tsconfig.json`

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

