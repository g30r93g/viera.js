# Viera.js-g30r93g

A node.js library to control Panasonic Viera TV's. Created by Samuel Matis and modified by George Nick Gorzynski. Please see license below.


## Why my fork?
I have included HDMI control and am working on getting apps installed on the TV and power state.

## Usage Example
```js
  var VieraJS = require("viera.js-g30r93g");
  var viera = new VieraJS("ipAddress");
  
  viera.sendRequest("Command", "X_SendKey", "<X_KeyEvent>NRC_" + command.toUpperCase() + "-ONOFF</X_KeyEvent>");
  
  viera.sendCommand("Power");
  viera.sendCommand("Up");
  viera.sendCommand("Menu");
  
  viera.sendHDMICommand(1);
  viera.sendHDMICommand(2);
  
  viera.sendAppCommand("0010000200000001"); // Netflix
  viera.sendAppCommand("0010000100170001"); // Amazon Prime Video
  viera.sendAppCommand("0070000200170001"); // YouTube
  
  viera.getMute((status) => {
    console.log("Mute: " + status);
  });
  viera.getVolume((volume) => {
    console.log("Volume: " + volume);
  });
  
  viera.setMute(true);
  viera.setVolume(30);
```

## License

The MIT License (MIT)

Copyright (c) 2014 Samuel Matis

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

## Modifications
Modified from the original code of Samuel Matis by George Nick Gorzynski
