# Virtual-Fisher-Grinder
## How to use
### 1.Open channel have virtual fisher
### 2.Type %f 1 time
### 3.Open chrome (or any browser) console
### 4.Paste the code
### 4-1.Type in console autoFish(true) to start and autoFish(false) to stop
### 4-2.Press enter
### 5.Don't close the window cuz it will click on the button at there
### 6.To do something else open another browser window
### 7.That's all

#### Note: the program will stop when the verify form shown so... :)

## Script

```js
function format(...code){
    if (code.length === 1) {
        return `[${code[0]}m`
    } else {
        for (i in code){
            formatList = code.join(";")
        }
        return `[${formatList}m`
    }
}
class Logger {
    static author = `[AutoFish]`;
    static log(notes) {
        console.log(`${format(1,94)}${this.author} ${format(92)}${notes}`)
    }
    static warn(notes) {
        console.warn(`${format(1,94)}${this.author} ${format(0)}${format(1)}${notes}`)
    }
}
function fish() {
list = document.querySelectorAll(".label-31sIdr")
if (list[list.length-1].innerText === "Fish Again") {
    list[list.length-1].click()
} else {
    for (i in list){
    if (list[i].innerText === "Fish Again"){
        list[i].click()
        break
    }
}
}
}
isToggled = false
async function idleFisher(time=3500) {
Logger.log("Successfully Start AutoFish!")
while (true) {
    try {
    if (isToggled === true) {    
        await new Promise(r => setTimeout(r, time));
        if(document.querySelectorAll(".embedTitle-2n1pEb.embedMargin-2PsaQ4")[document.querySelectorAll(".embedTitle-2n1pEb.embedMargin-2PsaQ4").length-1].innerText.includes("Anti-bot")){
            Logger.log("Please verify to continues")
            break
        }
        fish()
    } else {
        Logger.log("Successfully Stop AutoFish!")
        break
    }
    } catch {
        Logger.warn("Error!")
        break
    }
}
}
function autoFish(ss=false, time=3500) {
    isToggled = ss
    if (ss === true) {
        idleFisher(time)
    }
}

```
