# First step typescript

This first step goal is to be able to craft by your own hand an empty typescript project
This project must be executable.
For achieve this goal, you need to aware with your mind and skills (JCVD)
And, maybe more real, you need to read this file and understand instructions.

## Your first step.

If you can read this line, maybe you are the one! (no ..in real you are legion (find the reference)).

So... be serious... or not.

Your first step is simply create a new branch (need to be present physically and mentally for achieve this)
Your branch must be a fork of the main branch and name it with your name.

Be aware to the fact: all peoples on this repo can access to your branch...
For exemple, if your name is :
Jane Doe, you need to create a branch with the name
`doe_jane`
For the lost sheep, here a link
https://rewind.com/blog/how-to-create-new-branch-github/

## And after
So now you have branch, you need to be on it ...
Once again, all manipulations will be seen during the session.

## And after?
Bah, it's not finished :D
You need to create your base project...
for this, you need to use :

`npm init`

Follow all questions and at the end,  you will be able to see new file named:
`package.json`

Hell yeah!


## And after? (v2)

You need to create file name
`tsconfig.json`
```json
{
    "compilerOptions": {
        "target": "es5",
        "module": "commonjs",
        "lib": [
            "es2017",
            "es7",
            "es6",
            "dom"
        ],
        "declaration": true,
        "outDir": "dist",
        "noEmitOnError": true,
        "rootDir": "./src",
        "strict": true,
        "esModuleInterop": true
    },
    "exclude": [
        "node_modules",
        "dist"
    ]
}
```

## And after? (v3 - almost the end)

Adapt your package.json ,` we need some cool stuf`,
you can use npm install with the name of dependency or simply
`copy/paste` your needs from package.json then execute `npm install`

replace script part by this
```json
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node dist/main.js",
    "dev": "concurrently \"npx tsc --watch\" \"nodemon -q dist/main.js\"",
    "build": "npx tsc"
  }
```

add this part at the end of the object
```json
"devDependencies": {
    "@types/node": "^20.11.20",
    "concurrently": "^8.2.2",
    "nodemon": "^3.1.0",
    "ts-node": "^10.9.2",
    "typescript": "^5.3.3"
}
```


## And after? (v4 - very almost the end)

Now, we have define some important things:
First : we have define the main file (entry point) of the application
for example (and check your package.json to get your) , i've used

`"main":main.ts`

Second: we have define in `tsconfig.json` the name of source folder
`rootDir: ./src`

so with theses informations, we need to create in root of project (at the same level of package.json)
a folder `src` and in this folder a file named `main.ts`

Finally, add the following content in:

```typescript
const main = (): void => {
    console.log('Hell Yeah, im the king of typscript :D');
}

main();
```


## Test it

Now run this command :

`npm run dev`