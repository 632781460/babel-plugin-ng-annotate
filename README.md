# babel-plugin-ng-annotate - babel 6.x

## How to install

```
$ npm install --save-dev babel-plugin-ng-annotate
```

Note: this library depends on the [syntax decorators](https://www.npmjs.com/package/babel-plugin-syntax-decorators) plugin for parsing. Simply `$ npm install --save-dev babel-plugin-syntax-decorators babel-preset-es2015` and follow the setup instructions below.

## How to setup for chrome debug


#### .babelrc
```js
//don`t transform the syntax that chrome52 native support
{
  //"presets":[es2015],
  "plugins": ["transform-es2015-modules-commonjs",  "syntax-decorators", "ng-annotate-2", {keepClass: true}]
}
```

## How to setup for prod
#### .babelrc
```js
{
  "presets":[es2015],
  "plugins": ["transform-es2015-modules-commonjs",  "syntax-decorators", "ng-annotate-2"]
}
```


## How to use

```js
@Inject('service1', 'service2', 'service3')
class MyController {

    constructor() {
        this.service1();
    }

    method() {
        this.service2();
    }

    anotherMethod() {
        this.service3();
    }
}

angular.controller('MyController', MyController);
```
