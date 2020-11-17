# vue-slim-stackedbar
A Simple horizontal stacked bar chart Component for Vue.

![](https://img.shields.io/badge/license-MIT-green)  ![](https://img.shields.io/badge/release-v0.1.8-blue)  ![](https://img.shields.io/badge/Size-9KB-blue)  ![](https://img.shields.io/badge/code%20style-prettier-ff69b4)  




## Browser Support

|Chrome|Firefox|Safari|Edge|IE|
|--|--|--|--|--|
|35+|31+|6+|Legacy+|NOT TESTED|
|--|--|--|--|--|



## Installing

**Installing via npm**

```bash
$ npm install vue-slim-stackedbar
```




## Usage

```js
import StackedBar from 'vue-slim-stackedbar'
```


* To create a stacked bar chart with minimal configuration, write as follows:

```html
<template>
  <StackedBar :data="data" />
</template>
```

```js
export default {
  components: {
    StackedBar,
  },
  data() {
    return {
      data: [
        {
          title: 'First',
          value: 19,
          percent: 19,
          color: '#007bff'
        },
        {
          title: 'Second',
          value: 36,
          percent: 36,
          color: '#20c997'
        },
        {
          title: 'Third',
          value: 45,
          percent: 45,
          color: '#f28b8c'
        }
      ]
    };
  },
};
```


* This will render the following chart:

![](https://gitlab.com/CHESYA/CHE5YA/-/raw/master/uploads/sample.png)




## Props

|Name|Type|Default|Example|Description|
|--|--|--|--|--|
|title|String|X|'String Sample'|Title of Data Stack.<br>Only **String** can be used.|
|value|Number|X|15|Value of data.<br>Only **Number** can be used.|
|percent|Number|X|27|Value of percent.<br>Only **Number** can be used.<br> The sum of the data must not exceed **100**.|
|color|String|X|'#f28b8c'|Title of Data Stack.<br>Only use a **color hash code with #**.|





## Contact

[![](https://img.shields.io/badge/email-che5ya@naver.com-3EAF0E)](mailto:che5ya@naver.com)
[![](https://img.shields.io/badge/facebook-che5ya-4267B2)](https://facebook.com/che5ya)
[![](https://img.shields.io/badge/twitch-che5ya-6441a5)](https://www.twitch.tv/che5ya)




## License

vue-slim-stackedbar is released under MIT license. You are free to use, modify and distribute this software, as long as the copyright header is left intact.
