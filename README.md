# Polymer Logger (2.0)
A simple logging mixin for Polymer 2.0. It provides logging labels at both a global and component level, in addition to line-number/column logging.


## Preview

![Screenshot of logger in action, with the example of "[QR-APP - <qr-scanner>:59:21]  : QR Callback, firing event with content: TEST-QR"](http://daniel-cotton.co.uk/blog/upload/Polymer-Logger-Screencap.png)

## Installation

```bash
bower install --save polymer-logger
```

## Usage

### Setup

The PolymerLogger provides a Polymer 2.0 Class Mixin factory. Therefore 
in order for you to use the logging, you'll need to first create a custom-mixin 
using the factory.

Do this by creating a new .html file with contents similar to the following 
e.g. (my-logger.html):

```html
<link rel="import" href="../bower_components/polymer-logger/polymer-logger.html" >

<script>
  const MyLogger = PolymerLoggerBuilder("MY-GLOBAL-LOG-LABEL");
</script>

```
Now we just need to use it within our various components.

### Component Usage

To use inside your app components, simply import the mixin you created and use via the following syntax:
> this.LOGGER.debug

We support info, error, debug and warn log-levels. Full example:

```html
<link rel="import" href="my-logger.html" >

<script>
  class MyElement extends MyLogger(Polymer.Element) {
  
    ready () {
      super.ready();
      // within your code
      this.LOGGER.info('Ready function called');
    }
  }
</script>
```

## Known Issues/Limitations

 - Only designed with string log messages in mind
 [TODO] allow error objects.
