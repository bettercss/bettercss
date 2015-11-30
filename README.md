# Bettercss

Bettercss is a css toolkit that provides base libraries for you to include, and extend upon in your css projects.

The toolkit will never boast itself as a framework nor a complete solution. The compiled source provided is to be used for rapid prototyping, and should not to be included as a final solution unless your going for a seriously minimal style.

## Install

You can download or install the source from one of the following locations.

```sh
npm install bettercss

git clone git+https://github.com/bettercss/bettercss.git
```
*Note: zip will be coming soon.*

## Usage

Create yourself a source file and use the following load order when building your project.

```css
/* Resets & Elements */
@import 'bettercss-base';

/* Components */
@import 'bettercss-components';
@import './my-component.css';
@import './button-modifiers.css';

/* Utilities */
@import 'bettercss-utilities';
```

It’s recommend that you use this load order as it limits the specificity problems you may encounter. Starting with the less specific and working down to the more specific.

*Note: The beauty of the toolkit is you don’t have to follow this order and can change if required.*

### Single Library Usage

Only include what's needed for your project. The default behaviour for the toolkit is to include everything, but you can include single libraries and exclude the ones you don’t by doing the following:


```css
/* Base module */
@import 'bettercss-base';

/* Only include the button component */
@import 'bettercss-components/libs/button';

/* Utilities */
@import 'bettercss-utilities/libs/flex';
```

We recommend you always include the base module as it gives your project the best possible start, but nothing is mandatory you can include your own base.


## Processing (Transpiling)

The toolkit provides it’s own preprocessor built on top of the powerful [PostCSS](https://github.com/postcss/postcss). This allows you to sit closer to the css specifications and use future css features now. Once all browsers implement the specifications we can then remove the plugins usage from the preprocessor reducing the dependency coupling and processing time. This is something we could not do with SCSS or Less.

```sh
npm install -g bettercss-preprocessor

bettercss input.css output.css 
```

*Note: `grunt-plugin` and `gulp-plugins` coming soon*

The Bettercss preprocessor is a requirement when processing as we use some css that isn’t supported in the browser currently that needs to be transpiled.

You can see more usage and how you can build on top of the preprocessor [here](https://github.com/bettercss/preprocessor).


