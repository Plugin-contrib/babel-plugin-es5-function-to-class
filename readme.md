<p align="center">
  <img src="https://imgur.com/npZZj93.png" width="250px" />
</p>

<h1 align="center">babel-plugin-es5-function-to-class</h1>

### [Live Demo For Babel-Plugin](https://astexplorer.net/#/gist/bcd1d38ee27499e69cff92b8b0801c38/latest) 💻

# IO

## Input
```javascript
function Controller(param1, param2) {
    const name = "hello";
    let age = 21;
  }

  Controller.prototype.name = "hello";

  Controller.prototype.contributeTo = function(param) {
    var foo = "world-k";
  };

  Controller.staticMethod = function(param) {
    var bar = "world-cli";
  };

  Object.defineProperty(Controller.prototype, "hello", {
    get: function() {
      return "world";
    },
    set: function(name) {
      console.log("Do anything with " + name);
    }
  });

  Object.defineProperty(Controller.prototype, "lastname", {
    get: function() {
      return "kiwi";
    }
  });
```

## output
```javascript
class Controller {
  constructor(param1, param2) {
    const name = "hello";
    let age = 21;
    this.name = "hello"
  }

  contributeTo(param) {
    var foo = "world-k";
  }

  static staticMethod(param) {
    var bar = "world-cli";
  }

  get hello() {
    return "world";
  }

  set hello(name) {
    console.log("Do anything with " + name);
  }

  get lastname() {
    return "kiwi";
  }

}
```
#### Features :100:
- [x] Methods on `prototype`
- [x] Static Methods on `prototype`
- [x] Variables and Literals on `prototype`
- [x] Getters, Setters with `defineProperty`
- [x] Block-level Variables


 > ## Note : The babel-plugin-es5-function-to-class will only work properly if there is only one function declared in the input file else it will overwrite with the newest declared function. Will resolve this soon  :smile:

---

## Maintained by 

<img alt="pluggingIn logo" src="https://imgur.com/kjyrz79.png" width="250px" />

## Author

[Aniketh Saha](https://twitter.com/__ANIX__)
