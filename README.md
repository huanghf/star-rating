# star-rating
## 实现原理
![](https://ws4.sinaimg.cn/large/006tKfTcgy1fnqvphubb8j30lu0dodhh.jpg)
## Link
- demo
- github

## 主要代码
### css
```css
.score_wrapper {
      display:inline-block;
      font-size: 45px;
      cursor: pointer;
      color: #dc2020;
      -webkit-user-select:none;
      -moz-user-select:none;
      -ms-user-select:none;
      user-select:none;
    }
```

### html
```html
<div class="score_wrapper"></div>
```

### javascript
```javascript
    $(function () {
      ScoreInit(3); //初始化，参数是0～5的数字，代表星数，传空默认0颗星
    })
    //点击
    function ScoreInit(e) {
      Score((e == null) ? 0 : e);
      $(".score_wrapper").bind('click', function (e) {
        var eachWidth = $(".score_wrapper").width() / 5;
        var X = e.pageX - $(this).offset().left;
        var score = Math.floor(X / eachWidth) + 1;
        Score(score);
      })
    }
    //评分
    function Score(rate) {
      $(".score_wrapper").html("★★★★★☆☆☆☆☆".slice(5 - rate, 10 - rate));
    }
```
