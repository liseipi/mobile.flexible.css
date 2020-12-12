## Flexible.CSS

## 说明

* 页面在渲染过程中CSS执行是优于JS执行的，在flexible.js做html的fontsize的自适应过程，页面初始化会有明显的闪动，为了解决这一问题，我用CSS来替代JS的执行。
* Flexible.css的原理同Flexible.js相同，都是修改了fontsize，不同的是我用SCSS把自适合尺寸的CSS提前渲染好了。
* 默认html页面最大宽设为540px，你可以使用对等设计稿750px的flexible.750.css
* Flexible.css的雏形是用em，当初是以父级自适应子元素盒子，原因是2015年前大部分手机对rem兼容性差，但对媒体查询兼容性很好。
* CDN: https://cdn.jsdelivr.net/gh/liseipi/mobile.flexible.css@1.0/css/flexible.css

### 配合HTML最大宽度使用

```
@improt 'flexible.css/css/flexible.css'

html {
  max-width: 540px;
  margin: 0 auto;
  background-color: #f8f8f8;
  min-height: 100%;
  overflow-x: hidden;
  box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.1);
  font-size: 32px;
}
```

### 使用

采用750布局，设计稿尺寸为750px时使用SCSS计算

```
@function REM($px) {
  @return $px / 750 * 1rem;
}
```

默认采用540布局，设计稿为750px时可以计算到，540/750=0.72

```
@function REM($px) {
  @return $px / 540 * 0.72 * 1rem;
}
```