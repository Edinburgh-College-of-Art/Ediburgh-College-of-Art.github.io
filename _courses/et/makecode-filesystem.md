---
layout: page
title: ! 'Arduino IDE Setup for micro:bit'
course: Electronic Things
repo_url: electronic-things
order: 1
week: 3
---

Currently the filesystem extension for MakeCode is in beta. There is a working version that requires you to add a community made extension on Github.

## Requirements

- A GitHub Account

## Adding Github Repository to available packages

1. Go to [MakeCode](https://makecode.microbit.org)
2. Start a project
3. From the setup cog, select `Extensions`
4. Scroll to the bottom until _Want to create your own extension? Log in to GitHub_
5. follow process for generating a token
6. paste the url for the fork `https://github.com/Cybot101/pxt-filesystem`
7. click on result to add

### Notes

Data can be streamed over Serial and then downloaded as a `.csv` from there.

**Tested on:**

| OS                   | Browser | micro:bit Firmware Version |
| -------------------- | ------- | -------------------------- |
| macOS Mojave 10.14.6 | Chrome  | `253`                      |


### Example

<pre id="pre1" class="makecode">
input.onButtonPressed(Button.A, function () {
    files.appendLine(
    "output.txt",
    "Hello"
    )
})
input.onButtonPressed(Button.B, function () {
    files.readToSerial("output.txt")
})
basic.forever(function () {

})
</pre>

### Useful Links

- [How to Create a MakeCode Package for Micro:Bit](https://learn.sparkfun.com/tutorials/how-to-create-a-makecode-package-for-microbit/all)
