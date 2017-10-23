Base visual component implementation
====================================

[![build status](https://img.shields.io/travis/spasdk/component.svg?style=flat-square)](https://travis-ci.org/spasdk/component)
[![npm version](https://img.shields.io/npm/v/spa-component.svg?style=flat-square)](https://www.npmjs.com/package/spa-component)
[![dependencies status](https://img.shields.io/david/spasdk/component.svg?style=flat-square)](https://david-dm.org/spasdk/component)
[![devDependencies status](https://img.shields.io/david/dev/spasdk/component.svg?style=flat-square)](https://david-dm.org/spasdk/component?type=dev)
[![Gitter](https://img.shields.io/badge/gitter-join%20chat-blue.svg?style=flat-square)](https://gitter.im/DarkPark/spasdk)


Each component is an instance of [Emitter](https://github.com/cjssdk/emitter) module.


## Installation ##

```bash
npm install spa-component
```


## Usage ##

Add the singleton to the scope:

```js
var Component = require('spa-component');
```
Create instance with custom config:

```javascript
var component = new Component({
        $node: document.getElementById(id),
        className: 'bootstrap responsive',
        events: {
            click: function () { 
                // some you`r actions 
            }
        }
    });
component.add( 
    /* addition instance of Component */
);
component.focus();
```

### Constructor config ###


Name       | Type                      | Default value | Description
---------- | ------------------------- | ------------- | -------------
id         | Element                   | cid(0-n)      | component unique identifier (generated if not set)
className  | String                    | name          | space-separated list of classes for "className" property of this.$node
$node      | Element                   | null          | DOM element/fragment to be a component outer container
$body      | Element                   | null          | DOM element/fragment to be a component inner container (by default is the same as $node)
parent     | Component                 | null          | link to the parent component which has this component as a child
children   | Array.<Component>         | []            | list of components in this component
events     | Object.<string, function> | {}            | list of event callbacks
visible    | Boolean                   | true          | component initial visibility state flag
focusable  | Boolean                   | true          | component can accept focus or not
propagate  | Boolean                   | false         | allow to emit events to the parent component



## Development mode ##

> There is a global var `DEVELOP` which activates additional consistency checks and protection logic not available in release mode.


## Contribution ##

If you have any problem or suggestion please open an issue [here](https://github.com/spasdk/component/issues).
Pull requests are welcomed with respect to the [JavaScript Code Style](https://github.com/DarkPark/jscs).


## License ##

`spa-component` is released under the [MIT License](license.md).
