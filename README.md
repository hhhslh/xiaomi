# xiaomi
#### 小米页面
* 自动轮播---定时器
```
var index = $(".circle li.selected").index();
function goLeft(){
       if(index == 3) { index = -1; }
       $(".circle li").eq(index+=1).addClass("selected").siblings().removeClass("selected");
       $(".box-img li").eq(index).fadeIn().siblings().fadeOut();
}
function goRight(){
       if(index == 0) { index = 4; }
       $(".circle li").eq(index-=1).addClass("selected").siblings().removeClass("selected");
       $(".box-img li").eq(index).fadeIn().siblings().fadeOut();
}
$(".left").click(function(){
       goLeft()
})
$(".right").click(function(){
       goRight()
})
////定时器方法
function exportTimer(){
       timer = setInterval(function(){
            goLeft();
       },2000);
}
//第一次执行定时器
exportTimer();
//圆点触碰停止及开始定时器
$(".circle li").hover(
      function(){
           clearInterval(timer)
      },
      function(){
            exportTimer();
       }
)
//图片触碰停止及开始定时器
$(".box-img li").hover(
       function(){
            clearInterval(timer)
       },
       function(){
            exportTimer();
       }
)
//左按钮触碰停止及开始定时器
$(".left").hover(
       function(){
           clearInterval(timer)
       },
       function(){
           exportTimer();
       }
 )
//右按钮触碰停止及开始定时器
$(".right").hover(
      function(){
         clearInterval(timer)
      },
      function(){
          exportTimer();
      }
)
```
* 点击轮播---jQuery效果
```
$(".circle li").click(function(){
       var index = $(this).index();
       $(this).addClass("selected").siblings().removeClass("selected");
       $(".box-img li").eq(index).fadeIn().siblings().fadeOut();
})
```
*其它原理都同上，不一一陈述。
