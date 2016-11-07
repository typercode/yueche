# yueche
海淀驾校约车软件

**写这个软件的动力**

   14年报考海淀驾校，因为周六日时间不固定，所以报的是自己约车的班，考完科目一之后，连续两周在网上约车，都约不到，好气啊。
于是看了一下网上约车流程，有一个拦路虎，就是验证码，刚好当时做的产品里面用到了OCR（Optical character recognition），
可以识别简单的验证码，类似这样的![海驾的登陆验证码](http://haijia.bjxueche.net/tools/CreateCode.ashx?key=ImgCode&random=0.4004024330433442)
都是字母和数字的组合，识别率还不错，基本可以到到80%左右，对我来说已经够用了；另外这个网站用的.net写的，有一些简单表单验证信息，这也不难，通过[jsoup](https://github.com/jhy/jsoup)来解析页面信息，最后跟着表单一起提交就可以了。表单的具体信息通过[fiddler2](https://www.telerik.com/download/fiddler/fiddler2)来看，很方便。当然，还有一些运气，因为我发现了一个很有用的地方（这个在程序里能够体现出来），帮助我大大的提高了约车的成功率。
