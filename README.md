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
<ul> <li>string</li><br> <li>number</li><br> <li>boolean</li> <br> <li>object</li> <br><li>any - any is Generic Type we will not face problems if we change to another type later with it</li> <br></ul>

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

```

let arr : string[] = ['ali','hossam','amin'];

for(let i = 0;i < arr.length;i++){
  console.log(arr[i].repeat(2)); //This will cause warning so better use [! , ?]
}

console.log(arr[i]?.repeat(2)); // ? mean arr[i] can be undefiend (optional)

console.log(arr[i]!`.repeat(2)); // ! mean arr[i] mustn't be undefiend 

```

### Multi Diemensional Arrays

```
let arr1: string[] = ['a','b','c'];

let arr2: number[] = [1,2,3,4];

let arr3 : (string | number)[] = [1 , 2 ,3 ,4 ,'A','B'];

let arr4 : (string | number | string[])[] = [1,2,'A',['A','B']];
 

```

### Type Annotation :

> In config file there is multi features you can enable like :


```

"noImplicitReturns": true, // it will show error in the function if there is no return value
"noImplicitOverride": true, // Force me ues override word when overriding function
"noUnusedLocals": true, // Error on unused local variables
"noUnusedParameters": true, // Error on unused function parameter
"noFallthroughCasesInSwitch": true, // Error when using switch without break
"noEmitOnError": true, // !Important : this one is not exist as default in the config file you can added it , it strict the typescript file to be not compiled to javascript until the error in the typescript file is gone if there is no error it will change to js file

```


### Retured Value from Function :

```

function test(name:string , age:number) : string {
  return `Hello ${name} your age is ${age}`;
}

```

### Optional & Default Parameters :

```
//Default Value
function showData(name = 'Unknown', age, country) {
    return `${name} ${age} ${country}`;
}

console.log(showData(undefined,10 , 'EGY')); // Unknown 10 EGY

//Optional Value
function showData(name : string, age : number, country?:string){
    return `${name} ${age} ${country}`;
}

console.log(showData('Muhammed',10)); // Here country i can type it or can ignore it and i will didn't face any problems but it will return undefined in it's place



```

> Very Important Note : Optional Parameter it comes in the last i can't put optional paramter in first will cause me error

### Function Rest Parameter

```

function sumNums (...nums: number[]): number {
    let result:number = 0;
    nums.forEach((num) => result += num);
    return result;
    //return nums.reduce((acc,curr) => acc+=curr);
}

//Arrow Function

const sumNums = (...nums:number[]) : number => {
    return nums.reduce((acc,curr) => acc+=curr , 0);
}

console.log(sumNums(4,6)); // will return 10

```
### Type Alias

> Give you abillity to to rename the types you have like in this example :

```
type n = number;

let num1 : n = 5;

type stNum = string | number;

let container : stNum = 10;

container = 'test';

```

### Advanced Type Alias

> You can deal with advanced type alias like a class you defince the variable it must be in their and the data type of each one  but what is the diffrence between them ? <br> ``` type (or interface) ``` → only describes the structure of the data, no methods, no logic. <br> ``` class ``` → can have fields and methods, and you can create instances with new.


```

type Person = {
    name: string,
    age: number,
    isDriver : boolean
}


const person1:Person = {name:'Ahmed Muhammed',age: 30 , isDriver: false};

console.log(person1);

```
> You can inherit from types like inheritence from classes like in this example :

```

type Person = {
    name: string,
    age: number,
    isDriver : boolean
}

type Employee = Person & {
    jop: string,
    salary : number
}

const person1:Person = {name:'Ahmed Muhammed',age: 30 , isDriver: false};

const emp1: Employee  = {name:'Muhammed',age:23,isDriver:true,jop:'Front-End Dev',salary:30e3}

console.log(person1);

console.log(emp1);


```


### Return Types

```
// So I can return all the value i need as specific types from the function
function compare(num1: number , num2: number) : -1 | 0 | 1 {
  if(num1 === num2){
    return 0;
  }else if(num1 > num2){
    return 1;
  }else{
    return -1;
  }
}


//We Can use types in this
type nums = -1 | 0 | 1 ;
function compare(num1: number , num2: number) : nums{
  if(num1 === num2){
    return 0;
  }else if(num1 > num2){
    return 1;
  }else{
    return -1;
  }
}

```

### Tubles

> Tubles : has <br>1-Specific No of Elements <br>2-We know each position what data type of it 

```

let articles : [ number , string , boolean ] = [ 1 , 'Artical Number : 1' , false ];

articles = ['test' , 1 , 'Artical One' , false]; //Error -> First we put string in the first of tuble and we init as string as first , Second we put extra number of needed we init as 3 arguments only

articles = [2 , 'Artical Number : 2' , true]; // No Problems

```

> we can face type of errors here or bug if we init the tuble and after that we pushed element it will be added to handle this we must make the tuble readonly (so we can't push any element through it)


```
let articles : [ number , string , boolean ] = [ 1 , 'Artical Number : 1' , false ];

articles.push(100); // -> [1 , 'Artical Number : 1' , false , 100];

// To Handle it : 

let articles : readonly [ number , string , boolean ] = [ 1 , 'Artical Number : 1' , false ];

articles.push(100) // -> will face error

// But we can still change the tuble without problems even if it's readonly

articles = [ 1 , 'Artical Number : 1' , false ]


```
