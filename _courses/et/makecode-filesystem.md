---
layout: page
title: ! 'Using the Filesystem from MakeCode'
course: Electronic Things
repo_url: electronic-things
order: 3
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

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_157TU1LJpXsX" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>
<br>
### Useful Links

- [How to Create a MakeCode Package for Micro:Bit](https://learn.sparkfun.com/tutorials/how-to-create-a-makecode-package-for-microbit/all)
