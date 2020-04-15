[![npm version](https://badge.fury.io/js/chalky.svg)](https://badge.fury.io/js/chalky)

`npm i chalky` / `yarn add chalky`

# chalky

# Table of Contents

 - [About](#about)
 - [Demos](#demos)
 - [Properties / API](#properties)
 - [Why?](#why)

 ---

# About

Like [chalk](https://www.npmjs.com/package/chalk), but smaller ([772 bytes](https://bundlephobia.com/result?p=chalky)), self-contained (**no dependencies**), and fewer features.  Think of `chalky` like a 'stripped down', basic version of [chalk](https://www.npmjs.com/package/chalk).. 

`chalky` aims to provide a [chalk](https://www.npmjs.com/package/chalk)-like experience, but for the most basic of console color features. Simple and small. 'Cheaply' add color to your console without worrying about the size of `node_modules`.

We're not quite hardened [chalk](https://www.npmjs.com/package/chalk), but we're still `chalky` :smirk: 

 ---

# Demos

 - Chain like [chalk](https://www.npmjs.com/package/chalk):

```javascript
const smChalk = require('smallchalk');

smChalk.bgRed.black.bold.underline("Lorem ipsum dolor sit amet");
```

 - The last color in the chain is what gets used:

```javascript
// This line..
smChalk.red.green.blue.bgRed.bgBlack.bgYellow("Lorem ipsum dolor sit amet");
// ...is equivalent to this line
smChalk.blue.bgYellow("Lorem ipsum dolor sit amet");


// This line..
smChalk.red.blue("Lorem ipsum dolor sit amet");
// ...is equivalent to this line
smChalk.blue("Lorem ipsum dolor sit amet");
```

---

# Properties

 - **Foreground Colors:**
   - `black`
   - `red`
   - `green`
   - `yellow`
   - `blue`
   - `magenta`
   - `cyan`
   - `white`
   
 - **Background Colors:**
   - `bgBlack`
   - `bgRed`
   - `bgGreen`
   - `bgYellow`
   - `bgBlue`
   - `bgMagenta`
   - `bgCyan`
   - `bgWhite`
 
 - **Formatting:**
   - `bold`
   - `light`
   - `italic`
   - `underline`
   - `blink`
   - `inverse`
   - `hidden`

---
   
# Why?

Two reasons... 

I wanted to understand:
 - How Chalk.js was able to use properties with the same name as both a getter and method on the same object
   - For example, you can do `chalk.blue('foo');` and `chalk.blue.bold('foo');` (`.blue` is being used as both a method and getter)
 - How Chalk.js was able to chain these properties/methods/getters
 
 While modified, some of the code in this repo may resemble Chalk.js as I followed the same logic.
