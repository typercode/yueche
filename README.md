# yueche
海淀驾校约车软件

## 为什么要写这个软件呢？
   2014年7月份报考的海淀驾校，因为我的周六日时间不固定，所以报的是需要自己约车的班型，顺利考完科目一之后，结果连续两周在网上约车，都约不到，好气啊。嗯，这就是我为啥要写这个软件的原因，因为通过自己的技术能够约到车的感觉也是蛮好的。
   
## 前期准备、大概思路
   于是熟悉了一下网上约车流程，看到了一个拦路虎：验证码，刚好当时做的产品里面用到了OCR（Optical character recognition）技术[tesseract](https://github.com/tesseract-ocr/tesseract)，可以识别简单的验证码，类似这样的![海驾的登陆验证码](http://haijia.bjxueche.net/tools/CreateCode.ashx?key=ImgCode&random=0.4004024330433442)
，都是字母和数字的组合，识别率还不错，基本可以达到80%，对这个软件来说已经足够了；另外这个网站用的.net写的，如果熟悉.net开发的话，有一些简单表单验证机制，这也不难，通过[jsoup](https://github.com/jhy/jsoup)来解析页面信息，最后跟着表单一起提交就可以了。表单的具体信息通过[fiddler2](https://www.telerik.com/download/fiddler/fiddler2)来看，很方便。当然，还有一些运气，因为我发现了一个很有用的地方（这个在程序里能够体现出来），帮助我大大的提高了约车的成功率；处理http请求用的[HttpClient](https://hc.apache.org/httpcomponents-client-4.5.x/index.html)，后来发现jsoup也可以处理请求。还有一个定时，约车是从每天早上7点35分开始，到晚上10点结束，定时器用的[quartz](https://github.com/quartz-scheduler/quartz)；还用刀了一些jdk内部的东西，线程池等等。
