<img src='./assets/image.webp' style='width: 100%;' alt='Cover Image' />

# TypeScript
<br/>

## How To Install TypeScript :

> - First We Need To install NodeJS on Our Device to work as compiler for the typescript

### Installing TypeScript :
> - To Install TypeScript we can add it as package to the specific project or download it to be globally installed on our devices <br/>To Globally install typescript on our devices run this code ``` npm install -g typescript ``` <br>To Locale install in the project we can run this ``` npm install typescript --save-dev ```

>TypeScript is Made with extension of file ``` .ts ``` to be like that ``` testing.ts ``` <br>To Compile This File will type in terminal ``` tsc ``` for typescript compiler and then our file name ``` tsc ./testing.ts ```<br>To Watch always the file we can write ``` tsc -w ./index.ts ```

### Making the Configure File
> Configure file is containing the setting of the typescript you can edit many thing from it like where is the place that all the typescript will found in and where is the place that will compile to after compiling to javascript

<h5> The Following Code Show The Configuration File of the TypeScript : </h5>

```

{
  // Visit https://aka.ms/tsconfig to read more about this file
  "compilerOptions": {
    // File Layout
    "rootDir": "./src", // => This is where to find the typescript files
    "outDir": "./dist", // this is where to compile the typescript file [change to javascript]

    // Environment Settings
    // See also https://aka.ms/tsconfig/module
    "module": "nodenext",
    "target": "esnext",
    "types": [],
    // For nodejs:
    // "lib": ["esnext"],
    // "types": ["node"],
    // and npm install -D @types/node

    // Other Outputs
    "sourceMap": true,
    "declaration": true,
    "declarationMap": true,

    // Stricter Typechecking Options
    "noUncheckedIndexedAccess": true,
    "exactOptionalPropertyTypes": true,

    // Style Options
    // "noImplicitReturns": true,
    // "noImplicitOverride": true,
    // "noUnusedLocals": true,
    // "noUnusedParameters": true,
    // "noFallthroughCasesInSwitch": true,
    // "noPropertyAccessFromIndexSignature": true,

    // Recommended Options
    "strict": true,
    "jsx": "react-jsx",
    "verbatimModuleSyntax": true,
    "isolatedModules": true,
    "noUncheckedSideEffectImports": true,
    "moduleDetection": "force",
    "skipLibCheck": true,
  }
}


```

### After making init the folder as typescript environment :

> After making innit the folder as typescript environment that's make so easy to compile files now you can only type in your terminal ``` tsc -w ``` and it will watch the whole folder you make ``` rootDir path folder ``` and compile into the dist folder without specifing file.

### Types in TypeScript
<ul> <li>string</li><br> <li>number</li><br> <li>boolean</li> <br><li>any - any is Generic Type we will not face problems if we change to another type later with it</li> <br></ul>

```
let name:string = 'muhammed';

let age:number = 20;

let all:any = 'Ahmed';

all = 20;

console.log(all); // => 20 "No Error will be shown"

let test; // => Data Type : any

let stuName = 'Ali'; // => Data Typw : string

```

> if we didn't specified data type to variable and didn't give it value that compiler will not know it's type and give it type any !

### Variable with types can change many type :

> You can make the variable change many type by adding ``` | ``` operator between every type like this :

```

let variable1 : string | number ;
// OR
let variable1 : (string | number) ;
// OR
let variable1 : (string | number) = 'Ahmed';
// OR
let variable1 : (string | number) = 20;

variable1 = 10;

variable1 = 'Yasser';


```
