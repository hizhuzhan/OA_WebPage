# OA_WebPage

### H5手机端页面
#### 此demo用到的技术：<br>
* **等比缩放**（用与适配各个不同尺寸的手机屏幕）；<br>
  >js代码<br>
  ><pre><code><script>
  >   var width = document.documentElement.clientWidth || document.body.clientWidth;
  >   document.getElementsByTagName("html")[0].style.fontSize = width / 750 * 100 + "px";
  ><script>
  ></code></pre>
  >
***
* **移动端mobiscroll时间控件**（由于用到的日期控件需要精确到分钟，而H5自带的datetime控件兼容性极差）；<br>
  >引入js与css<br>
  ><pre><code><script src="js/jquery.js" type="text/javascript"></script>
  > <script src="js/jquery-1.10.0.min.js"></script>
  > <script src="js/mobiscroll_002.js" type="text/javascript"></script>
  > <script src="js/mobiscroll_004.js" type="text/javascript"></script>
  > <link href="css/mobiscroll_002.css" rel="stylesheet" type="text/css">
  > <link href="css/mobiscroll.css" rel="stylesheet" type="text/css">
  > <script src="js/mobiscroll.js" type="text/javascript"></script>
  > <script src="js/mobiscroll_003.js" type="text/javascript"></script>
  > <script src="js/mobiscroll_005.js" type="text/javascript"></script>
  > <link href="css/mobiscroll_003.css" rel="stylesheet" type="text/css">
  ></code></pre>
  >
  >js代码<br>
  ><pre><code>
  ><script type="text/javascript">
  >  $(function(){
  >      //时间控件-------start
  >      var currYear = (new Date()).getFullYear();  
  >      var opt={};
  >      opt.date = {preset : 'date'};
  >      opt.datetime = {preset : 'datetime'};
  >      opt.time = {preset : 'time'};
  >      opt.default = {
  >          theme: 'android-ics light', //皮肤样式
  >          display: 'modal', //显示方式 
  >          mode: 'scroller', //日期选择模式
  >          dateFormat: 'yyyy-mm-dd',
  >          lang: 'zh',
  >          showNow: true,
  >          nowText: "今天",
  >          startYear: currYear - 10, //开始年份
  >          endYear: currYear + 80 //结束年份
  >      };
  >      $("#fldsqrq").mobiscroll($.extend(opt['date'], opt['default']));
  >      var optDateTime = $.extend(opt['datetime'], opt['default']);
  >      $("#fldqjsj_start").mobiscroll(optDateTime).datetime(optDateTime);
  >      $("#fldqjsj_end").mobiscroll(optDateTime).datetime(optDateTime);
  >      //时间控件-------end
  >  });
  ></script>
  ></code></pre>

