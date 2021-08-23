# 2. Variables

**Variables** in computer science are named entities that serve as placeholders for stored values. Variables can store all sorts of things: numbers, words, and more!

Contents
* [Data Types](#data-types)
* [Declaring & Initializing Variables](#declaring-&-initializing-variables)
---


## Data Types
Data types describe the type of data that we are storing in a variable. In JavaScript, there are seven types:

1. **Number**: integers, numbers with decimals (2, 4.35, -202, ...)
2. **String**: text surrounded by single or double quotes ("Hello World" or 'Hello World!')
3. **Boolean**: true or false
4. **Null**: the *intentional* absence of a value
5. **Undefined**: when variables lack a value

Don't worry about the following data types for now:
6. **Symbol**
7. **Object**

## Declaring & Initializing Variables
We can *declare* and *initialize* variables at the top of our sketch using the word **let**.

```javascript
// declaring & initializing x and y at the top of our sketch
let x = 100;
let y = 50;

function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(200);
  
  ellipse(x, y, 50);
}
```

Notice how we can use arithmetic expressions with variables:

```javascript
let x = 100;
let y = 50;

function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(200);
  
  ellipse(x, y, 50);
  ellipse(x, y + 50, 50);
  ellipse(x, y + 100, 50);
}
```
![ellipses](assets/ellipses.png)

**Key Reflection Question:** why use variables??

Note: We don't have to *initialize* the variable immediately when we declare it. Variables that store colors (colors are technically the "object" data type), for example, must be set in the setup() or draw(). For example:

```javascript
// declaring color variables
let tealColor, orangeColor;

function setup() {
  createCanvas(400, 400);

  // initializing color variables
  tealColor = color(0, 255, 255);
  orangeColor = color(255, 220, 100);
}

function draw() {
  background(tealColor);
  fill(orangeColor);
  rect(100, 100, 100);
}
```


We've previously seen built-in variables like `mouseX` that store a value. Now we're going to create our own **variables**—words that serve as *placeholders* for values such as integers, text, or other values.

### If we don't initialize variables...

* `undefined` will be its value
* `NaN` (not a number) if we try to compute a value with it
* throw an error in the console if we try to pass it to a function like `rect()`

See what happens in the console if you run the following code:

```javascript
let x;

function setup() {
  createCanvas(windowWidth, windowHeight);
  
  console.log(x);
  console.log(x+2);
  rect(x, 10, 10, 10);
}
```

# NOTES: Built-in Variables

**Video resource**: [Dan the Man](https://youtu.be/7A5tKW9HGoM)

---



p5.js has a few **built-in variables** that are already defined and ready to use:

* `width` - the width of the canvas  
* `height` - the height of the canvas  

* `windowWidth` - the width of the *window* containing the canvas  
* `windowHeight` - the height of the *window* containing the canvas  


* `mouseX` - the mouse's x-coordinate    
* `mouseY` - the mouse's y-coordinate

We usually only use `windowWidth` and `windowHeight` in the `setup()` to make the canvas fullscreen:

```javascript
function setup() {
  createCanvas(windowWidth, windowHeight);
}
```

We can create a paintbrush using `mouseX` and `mouseY` (make note of the `background()` second argument which makes it semi-transparent):
```javascript
function setup() {
  createCanvas(windowWidth, windowHeight);
}

function draw() {
  background(0, 5);
  ellipse(mouseX, mouseY, 50);
}
```
![paintbrush](assets/paint.png)



## Resources
[Dan the Man Video Tutorial](https://www.youtube.com/watch?v=dRhXIIFp-ys&list=PLRqwX-V7Uu6Zy51Q-x9tMWIv9cueOFTFA&index=9)