# Front-end Challenge

> We provided some simple JavaScript template code. Your goal is to modify the application so that you can properly toggle the button to switch between an ON state and an OFF state. When the button is on and it is clicked, it turns off and the text within it changes from ON to OFF and vice versa. You are free to add classes and styles, but make sure you leave the element ID's as they are. 

Submit your code once it is complete and our system will validate your output.

> See the code below: 

```javascript

 ![alt text](https://github.com/kingdanie/php-coding-challenges/assets/52611355/d8bda559-0ef1-415d-b66a-37b5e6864d30 "frontend-challenge screenshot")

import $ from "jquery";
const rootApp = document.getElementById("root");
rootApp.innerHTML = '<button>ON</button>';
```





## The Solution

```javascript

import $ from "jquery";

const rootApp = document.getElementById ("root") ;
rootApp-innerHTML='<button>ON</button>':
rootApp.classList-add('on');

rootApp-addEventListener("click", function() {
  if(rootApp.classList.contains('on')){
    rootApp-innerHTML= '<button>OFF</button>';
    rootApp.classList.remove('on');
    rootApp.classList.add('off");
  }
  else {
    rootApp. innerHTML = '<button>ON</button>';
    rootApp.classList.remove('off");
    rootApp.classList.add('on');
  }
});

```
