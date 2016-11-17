react-native event source
=========================

Server-Sent Events for your React Native apps! Based on @remy's
[EventSource polyfill](https://github.com/remy/polyfills/blob/master/EventSource.js).

## Installing

Run the following command in your project's directory to grab the latest published version of this code:

```bash
$ npm install react-native-event-source --save
```

<<<<<<< HEAD
## Usage

### Linking the Library
In order to use quick actions you must first link the library to your project.  There's excellent documentation on how to do this in the [React Native Docs](http://facebook.github.io/react-native/docs/linking-libraries-ios.html#content).

=======
>>>>>>> madriska/master
### Using in your project

```js
import RNEventSource from 'react-native-event-source'
```

Now you're ready to connect to your SSE endpoint and start streaming updates!
:godmode:

```js
const eventSource = new RNEventSource('https://my-sse.com/stream');

eventSource.addEventListener('message', (event) => {
  console.log(event.type); // message
  console.log(event.data);
});
```

Here is a full example that subscribes to a SSE stream and writes the results to `console.log`

```js
import React, { Component } from 'react';
import { View, Text } from 'react-native';

import RNEventSource from 'react-native-event-source';

class MyApp extends Component {
  componentDidMount() {
    this.eventSource = new EventSource('https://sse.com/stream');

    // Grab all events with the type of 'message'
    this.eventSource.addEventListener('message', (data) => {
      console.log(data.type); // message
      console.log(data.data);
    });
  }
  componentDidUmnount() {
    this.eventSource.removeAllListeners();
    this.eventSource.close();
  }
  render() {
    return (
      <View>
        <Text>Streaming!</Text>
      </View>
    )
  }
}
```

## License

Copyright (c) 2015 Jordan Byron (http://github.com/jordanbyron/)

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
