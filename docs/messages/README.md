# System message feature

Code: https://github.com/wejs/we-core/blob/master/lib/messages/index.js

## How to set one message:

```js
// types: success, error, warning, info 

res.addMessage('success', {
  // i18n string
  text: 'group.join.success',
  // vars avaible in i18n string
  vars :{
    group: group
  }
});
```
