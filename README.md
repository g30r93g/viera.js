viera.js
========

Node.js library for controlling Panasonic Viera TV, courtesy of Samuel Matis.
This fork contains HDMI switching command and viera application launching.

## How to use

1. Require the module and create an instance of module:

```js
  var Viera = require('./viera');
  
  var tv = new Viera('<ip_address>');
```

2. Start sending commands! (commands listed in ``` codes.txt ```)

```js
  tv.sendCommand("menu");
  
  tv.sendAppRequest("App_ID")
  
  tv.setVolume(20);
  
  tv.setMute(true);
  
  tv.getVolume(function(data) {
      console.log(data);
  });
```

You can also chain multiple methods:
 ```js
  tv.sendCommand("apps")
    .sendCommand("down")
    .sendCommand("enter")
    .setVolume(25);
  ```

You can see an example in  ``` example.js ```

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
