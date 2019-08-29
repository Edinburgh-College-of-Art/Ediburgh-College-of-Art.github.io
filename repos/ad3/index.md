---
layout: page
title: Architectural Design 3 - Unit 3
---

Welcome to Architectural Design 3: Unit 3. Throughout the course, should you have any questions about arduino programming, get in touch with [Digital Development](mailto:DigiDevECA@ed.ac.uk?subject=Help!). Follow the setup below and bookmark this page for reference.

## Setup

### Hardware

- **Arduino**

  To get started, first you are going to need an Arduino. Arduno Uno ar available at the [ECA bookit stores](https://bookit.eca.ed.ac.uk/av/) across campus.

- **Sensors**

  Sensor kits are also available from the bookit store. As the semester progresses, you will need to look for sensor that can get the data you need. If you aren't sure which sensor you need, email [Digital Development](mailto:DigiDevECA@ed.ac.uk?subject=Help With Sensors&body=Hi,%0A%0A I Need X in order to do Y. Which sensor do I need?)

### Software

- [Arduino IDE](https://www.arduino.cc)

  To start programming the Arduino, you will need the Arduino Integrated Development Environment (IDE). There are tons of [tutorials](https://www.arduino.cc/en/Tutorial/HomePage) available. It is also worth bookmarking the [Arduino Reference](https://www.arduino.cc/reference/en/)

- [GitHub Repository](https://github.com/Edinburgh-College-of-Art/architectural-design-unit-3)

  The AD3 GitHub repo contains a few more advanced examples as well as an up to date version of the FireFly Firmata. [Download the Repository](https://github.com/Edinburgh-College-of-Art/architectural-design-unit-3/archive/master.zip) or [Sign-up for GitHub](https://github.com), download the [GitHub Desktop App](https://desktop.github.com). Git is a great way to manage your code especially if you need help debugging.

  If you don't want to sign-up for github, you can simply clone the repository using git in command line. If you are on windows, [follow the setup](#Git-Windows) at the bottom of the page

---

## Resources

### Arduino

- [Arduino Tutorials](https://www.arduino.cc/en/Tutorial/HomePage)
- [Arduino Reference](https://www.arduino.cc/reference/en/)

### Rhino / Grasshopper / Firefly

Previous Master Student Henri made up some documentation for using the Firmata and Rhino / Grasshopper / Firefly. Some information is out of data, but the rest is still useful.

- <a href="https://edinburgh-college-of-art.github.io/architectural-design-unit-3/docs/AD3-Arduino-Session-1-Handout.pdf" download>Part 1</a>
- <a href="https://edinburgh-college-of-art.github.io/architectural-design-unit-3/docs/AD3-Arduino-Session-2-Handout.pdf" download>Part 2</a>
- <a href="https://edinburgh-college-of-art.github.io/architectural-design-unit-3/docs/AD3-Arduino-Session-3-Handout.pdf" download>Part 3</a>
- <a href="https://edinburgh-college-of-art.github.io/architectural-design-unit-3/docs/AD3-Arduino-Session-4-Handout.pdf" download>Part 4</a>

### Re-Use

We would incourage you to use waste materials as much as possible. There are all manner of electronics components to be stripped out of old elctronic equipment such as buttons, sliders, knobs and so forth.

Check out the [Free-Use Hub](https://www.eca.ed.ac.uk/facility/free-use-hub) at the Firestation for some interesting finds.

### Where to Buy Components

I fyou absolutely must buy some sensor or components, the the follow are reputable suppliers the deal in RoHS compliant materials. Of course, it never hurts to [ask if we have something already.](mailto:DigiDevECA@ed.ac.uk?subject=Sensors&body=Hi,%0A%0A Do you have X I can beg, borrow or steal?)

- [Pimoroni](https://shop.pimoroni.com/)
- [CPC / Farnell](http://cpc.farnell.com)
- [Ooz Nest](https://ooznest.co.uk/) (3D Printers and Steppers)
- [RS](http://uk.rs-online.com/)
- [Rapid](http://www.rapidonline.com/)

### Where can I work with Electronics?

If you want to go beyond using a breadboard and need some workshop space there are some fascilities available in the University and the wider city of Edinburgh. We wouldn't encourage students to use there own soldering irons, so there are some fascilities available on request.

- [uCreate Studio](https://www.ucreatestudio.is.ed.ac.uk)
- [Design Informatics](https://www.eca.ed.ac.uk/profile/mark-kobine)

Out of hours and outside the university there are some fadcilities available for electonic prototyping

- [Eagle Lab at CodeBase](https://labs.uk.barclays/locations/edinburgh)
- [Edinburgh HackLab](https://edinburghhacklab.com)

---


<h3 id="Git-Windows"> <i class="fab fa-windows"></i> Git for Windows</h3>
<a href="https://www.youtube.com/watch?v=339AEqk9c-8">Video Tutorial</a>
<ol>
    <li>Download the Git for Windows <a href="https://git-for-windows.github.io/">installer</a>.</li>
    <li>Run the installer and follow the steps below:
        <ol>

            <li>
                Click on "Next" four times (two times if you've previously
                installed Git).  You don't need to change anything
                in the Information, location, components, and start menu screens.
            </li>
            <li>
                <strong>
                    Select “Use the nano editor by default” and click on “Next”.
                </strong>
            </li>

            <li>
                Keep "Use Git from the command line and..." selected and click on "Next".
                If you forgot to do this programs that you need for the workshop will not work properly.
                If this happens rerun the installer and select the appropriate option.
            </li>

            <li>Click on "Next".</li>

            <li>
                Keep "Checkout Windows-style, commit Unix-style line endings" selected and click on "Next".
            </li>

            <li>
                <strong>
                    Select "Use Windows' default console window" and click on "Next".
                </strong>
            </li>

            <li>Click on "Install".</li>


            <li>Click on "Finish".</li>
        </ol>
    </li>
    <li>
        If your "HOME" environment variable is not set (or you don't know what this is):
        <ol>
            <li>Open command prompt (Open Start Menu then type <code>cmd</code> and press [Enter])</li>
            <li>
                Type the following line into the command prompt window exactly as shown:
                <p><code>setx HOME "%USERPROFILE%"</code></p>
            </li>
            <li>Press [Enter], you should see <code>SUCCESS: Specified value was saved.</code></li>
            <li>Quit command prompt by typing <code>exit</code> then pressing [Enter]</li>
        </ol>
    </li>

</ol>
<p>This will provide you with both Git and Bash in the Git Bash program.</p>

You can now clone the repository with
```bash
git clone http://github.com/Edinburgh-College-of-Art/architectural-design-unit-3
```
