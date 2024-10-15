# Enqode Assignment

## Part 1: JS

<p align="justify">The output of this code will be written to the console after 5 seconds. The logs will be the same: "The element in position 5 is: undefined"</p> 
<p align="justify">Explanation: the iteration of the for loop execute nearly immediately for all the elements of the array. then, the "worker" wait for 5 sec to actually execute the functions within the setTimeout method.</p>
<p align="justify">Before the fifth iteration, the "i" equal to 4 (still smaller then the array length, which is 5), and right after that it turns to 5 (because of the "i++") and stop iterating.</p>
<p align="justify">When the function finally executed, after 5 seconds, the i is equal to 5. There isn't an element in array[5], so it printed as "undefined".</p>
<p align="justify">If we want the console to log the one element every five seconds, we should use the setInterval method, or simply multiply the delay argument, in the setTimeout, by the "i" variable. In that case we need to use "let" instead of "var", because the let value depends on it own scope</p>

<p>Option 1:</p>

```
const array = [12, 10, 22, 5, 25]
var i = 0

const logOneElement = ()=> {
    console.log("The element in position " + i + " is: " + array[i])
    if (i === array.length - 1) {
        clearInterval(intervalId)
    } else {
        i++
    }
}

const intervalId = setInterval(logOneElement, 5000)

```

<p>Option 2:</p>

```
const array = [12, 10, 22, 5, 25]

for(let i = 0; i < array.length; i++) {
    setTimeout(()=>{
      console.log("The element in position " + i + " is: " + array[i])
    }, 5000 * i)
}

```

