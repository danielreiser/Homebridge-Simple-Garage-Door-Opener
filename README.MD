# Simple Garage Door Opener

[![npm version](https://badge.fury.io/js/homebridge-simple-garage-door-opener.svg)](https://badge.fury.io/js/homebridge-simple-garage-door-opener)

A Homebridge Plugin for controlling your garage door via your iOS device.

Being frustrated about the lack of homekit-enabled garage door openers which don't need any modifications on the garage door itself, I created my own solution.
Oh and it's pretty cheap too.

The setup is pretty straight forward. All you need is a raspberry pi or other device running [homebridge](https://github.com/nfarina/homebridge). A modified remote control (details are down below). That's it.


### Why *another* homebridge plugin?
There are already some plugins out there doing something similar. The problem with this simple setup of mine is the lack of a reporting functionality/backchannel 'cause all I am doing is triggering the opening of the door. Therefore homekit doesn't know anything about the current state (opening/open/closing).
Most plugins need some kind of sensory input to tell homekit exactly that. As I can't tell homekit what state the door actually is in, I just pretend to know and give homekit some information to work with.


### Getting Started

#### Prepare your existing garage door remote
As I am living in a house with multiple parties, I can't modify the garage door electronics directly. So I looked for an other way. I just used the existing remote control which is a `Sommer Handsender 4020` which is pretty common in Germany and modified it.

PLEASE NOTE THAT I DON'T HAVE MUCH EXPERIENCE IN BUILDING ELECTRICAL CIRCUITS AND THEREFORE WON'T PROVIDE HELP IN BUILDING THE CIRCUIT.

#### Install via npm (>= v6.x.x)
`npm install homebridge-simple-garage-door-opener -g`


#### Install Manually
Clone the latest release [here](https://github.com/danielreiser/Homebridge-Simple-Garage-Door-Opener). Install via `npm -i -g`.


#### Edit the ./homebridge/config.json
You don't need that much to get started. Just tell Simple Garage Door Opener which GPIO you want to use and you're good to go. (More options available)

```
"accessories": [{
        "accessory": "SimpleGarageDoorOpener",
        "name": "SimpleGarageDoorOpener",
        "doorSwitchPin": 12,
        "simulateTimeOpening": 15,
        "simulateTimeOpen": 30,
        "simulateTimeClosing": 15
    }]
```

#### Misc
Feel free to give me feedback, create PRs or submit issues, enhancements and bugs.
