### javascript 跨域


只要协议、域名、端口有任何一个不同，都被当作是不同的域，之间的请求就是跨域操作。

1、如何解决跨域问题?
jsonp、 iframe、window.name、window.postMessage、服务器上设置代理页面

2、造成跨域的两种策略
浏览器的同源策略会导致跨域，这里同源策略又分为以下两种DOM同源策略：
（1）禁止对不同源页面DOM进行操作。这里主要场景是iframe跨域的情况，不同域名的iframe是限制互相访问的。
（2）XmlHttpRequest同源策略：禁止使用XHR对象向不同源的服务器地址发起HTTP请求。

3、跨域的解决方式

（1）跨域资源共享
CORS是一个W3C标准，全称是”跨域资源共享”（Cross-origin resource sharing）。
对于客户端，我们还是正常使用xhr对象发送ajax请求。唯一需要注意的是，我们需要设置我们的xhr属性withCredentials为true，不然的话，cookie是带不过去的哦，设置： xhr.withCredentials = true;
对于服务器端，需要在 response header中设置如下两个字段:Access-Control-Allow-Origin: http://www.yourhost.comAccess-Control-Allow-Credentials:true这样，我们就可以跨域请求接口了。

（2）jsonp
基本原理就是通过动态创建script标签,然后利用src属性进行跨域。

（3）服务器代理
浏览器有跨域限制，但是服务器不存在跨域问题，所以可以由服务器请求所要域的资源再返回给客户端。
服务器代理是万能的。

（4）使用window.name进行跨域
window.name跨域同样是受到同源策略限制，父框架和子框架的src必须指向统一域名。
window.name的优势在于，name的值在不同的页面(或者不同的域名)，加载后仍然存在，除非你显示的更改。并且支持的长度达到2M.

（5）location.hash跨域
location.hash方式跨域，是子框架具有修改父框架src的hash值，通过这个属性进行传递数据，且更改hash值，页面不会刷新。
但是传递的数据的字节数是有限的。

（6）使用postMessage实现页面之间通信
信息传递除了客户端与服务器之前的传递，还存在以下几个问题：
  ● 页面和新开的窗口的数据交互。
  ● 多窗口之间的数据交互。
  ● 页面与所嵌套的iframe之间的信息传递。
window.postMessage是一个HTML5的api，允许两个窗口之间进行跨域发送消息。这个应该就是以后解决dom跨域通用方法了，具体可以参照MDN。













