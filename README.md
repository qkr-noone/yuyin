# yuyin
## 内嵌H5
写公共方法，公共样式
写页面--- 读取数据 --- 内容方法 --- 交互方法 --客户端和前端相互调取方法---安卓和IOS的区别---测试
## 彩铃
写页面---读取数据（运营商接口）---彩铃交互方法--测试
## 余音内嵌H5总结	
1.方法需要判断平台类型安卓还是IOS,根据定义的方法调取,在对外h5分享页面方法，也需要判断平台类型。（在加载首次时就可判断，取一个保存值）
2.客户端调取H5的方法最好方法命名前加window, 有些变量也可以定义为全局变量 window.变量。在调取的客户端方法是在回调时，接下来的操作应该在回调的内部执行（解决回调时间不确定，可能取不到回调返回的值）				
3.数据url转换格式，删减修改,提前定义方法，图片预加载，背景预加载，图片替换默认图，数据请求ajax，统计addup ajax请求，页面弹框方法，其他数据页面公用的方法封装，在页面微信二次分享，定义分享的数据格式。（在切歌曲时，前后分享的歌曲不一致时，需要对wx.ready({}),执行的方法，进行具体的分析）				
4.页面的列表超出部分滚动时，解决IOS齿轮滚动=》-webkit-overflow-scrolling: touch;				
5.页面加载默认图片，数据图片时，需要给合适的宽=》 图片过大影响性能，过小图片不清晰				
6.在页面列表数据中图片不一致高度，影响整体布局排布，=》规定列表图片中div高度和宽，把图片数据作为背景图片进行替换		
7."取消a p input 等标签的:hover 边框颜色变化，outline:none；input在IOS 中使用-webkit-text-fill-color: transparent; input {
    -webkit-tap-highlight-color: rgba(0,0,0,0);
    -webkit-appearance: none;
    -webkit-user-modify: read-write-plaintext-only;
}"				

8.移动端，可以使用tap，性能更加好，在tap事件 中需要return false				
9.执行IOS方法，回调得到的数据时，IOS不能进行返回=》在执行完IOS时，调取H5方法，把返回数据作为参数返回。				
10.h5方法中的audio,在歌词滚动，方法放写在timeupdate，position().top是相对定位父元素的，offset().top是相对视窗的，display 设置为none时候  拿不到wihth heigh top 等属性·，$("body").prepend(JSON.stringify(data));  歌词多种格式解析方法。				
