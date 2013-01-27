
# filter

  A simplication of Web Audio API filters.

## Installation

    $ component install web-audio-components/filter

## Example Usage

```javascript
var context = new webkitAudioContext()
  , Filter = require("filter")
  , osc = context.createOscillator()
  , lp = new Filter.Lowpass(context, { frequency: 800 });

osc.connect(lp.input);
lp.connect(context.destination);
osc.start(0);
```

For another example, see the test directory.

## API

### Filter(context, options)

Instantiate a Filter effect module. Expects an `AudioContext` as the first
parameter.

**Options**

- `type` Filter type. Corresponds to the BiquadFilter enum.
- `frequency` Filter frequency.
- `Q` Filter Q.
- `gain` Filter gain.
- `wet` Wet signal gain coefficient.
- `dry` Dry signal gain coefficient.

### Filter.Lowpass(context, options)

A utility constructor for instantiating a lowpass filter.

### Filter.Highpass(context, options)

A utility constructor for instantiating a highpass filter.

### Filter.Bandbass(context, options)

A utility constructor for instantiating a bandpass filter.

### Filter.Lowshelf(context, options)

A utility constructor for instantiating a lowshelf filter.

### Filter.Highshelf(context, options)

A utility constructor for instantiating a highshelf filter.

### Filter.Peaking(context, options)

A utility constructor for instantiating a peaking filter.

### Filter.Notch(context, options)

A utility constructor for instantiating a notch filter.

### Filter.Allpass(context, options)

A utility constructor for instantiating a allpass filter.

### .connect(node)

Connect a Delay module to an `AudioNode`.

### .disconnect()

Disconnect all outgoing connections from a Delay module.

## License

  Copyright (c) 2012 Nick Thompson

  Permission is hereby granted, free of charge, to any person
  obtaining a copy of this software and associated documentation
  files (the "Software"), to deal in the Software without
  restriction, including without limitation the rights to use,
  copy, modify, merge, publish, distribute, sublicense, and/or sell
  copies of the Software, and to permit persons to whom the
  Software is furnished to do so, subject to the following
  conditions:

  The above copyright notice and this permission notice shall be
  included in all copies or substantial portions of the Software.

  THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
  EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
  OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
  NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
  HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
  WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
  FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
  OTHER DEALINGS IN THE SOFTWARE.

