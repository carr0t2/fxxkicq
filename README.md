# fxxkicq
用魔法打败魔法，保证每一个题目都点击过，dddd

## 使用方法
在比赛平台显示所有题目页面打开控制台，执行下列js代码
```js
num = 0;
count = 0;
$.ajaxSetup({
  complete: function (xhr) {
    if (xhr.responseText == '{"code":0,"message":"操作成功"}') {
      count++;
    }
  },
});
record = setInterval(function () {
  card = document.getElementsByClassName("card")[num++];
  if (card) {
    card.click();
  } else {
    clearInterval(record);
    if (count === --num && document.getElementsByClassName("card").length === count && count) {
      console.log(`我全TM点过了!`);
    } else {
      console.log(`再运行一次`);
    }
  }
}, 500);
```
## 原因

某平台前端代码有点问题，dddd
