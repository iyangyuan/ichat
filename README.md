ichat
=====
可能是历史上最灵活的jQuery在线客服插件
=====
  
简介：
-------------
  
`ichat`是一款开源免费在线客服`jQuery`插件，通过该插件，您可以自由的定制属于自己的在线客服代码。  
`ichat`充分吸收传统在线客服插件的优点，并加上自身的独特设计，使得`ichat`可定制性异常强大。  
`ichat`追求简单实用，走小清新路线，以便能够适应大多数网站风格。  
`ichat`几乎全部由配置生成，使用简便，不需要写`html`，但需要写`js`，因为配置是`json`对象。  
`ichat`体积小巧，代码高效，采用`jQuery`插件封装，与原有系统零冲突。  
`ichat`兼容旧版本IE浏览器，例如：`IE6`、`IE7`等，虽然效果一般，但至少可以用，火狐、谷歌、360等浏览器更不在话下。  
  
使用说明：
-------------
  
引用插件的js、css文件：  
  
    <link rel="stylesheet" href="css/ichat-1.0.min.css">
    <!--ichat是jQuery插件，必须先引入jQuery-->
    <script src="js/jquery-1.10.2.min.js"></script>
    <script src="js/ichat-1.0.min.js"></script>
  
调用ichat插件，生成在线客服浮窗：  
  
    $("body").ichat({
      //ichat配置
    });
  
使用示例：
-------------
  
    <!DOCTYPE html>
    <html>
      <head>
        <title>ichat使用示例</title>
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link rel="stylesheet" href="css/ichat-1.0.min.css">
      </head>
      <body>
        
        <script src="js/jquery-1.10.2.min.js"></script>
        <script src="js/ichat-1.0.min.js"></script>
        <script>
          $(document).ready(function(){
            $("body").ichat(
              {
                //浮窗位置，取值：left|right
                placement: "right",
                //浮窗到页面顶部的距离相对于浏览器高度的比例，取值：1~100
                //ie6、ie7下此项设置无效
                top: 20,
                //浮窗显示的文本
                title: "在线客服",
                //浮窗配色，取值：black|blue|red|green
                color: "blue",
                //以何种事件展开浮窗，取值：click|hover
                trigger: "click",
                //浮窗展开后的可见内容列表
                items:[
                  {
                    //内容类型，取值：qq|tel|text
                    //qq用来显示客服QQ
                    type: "qq",
                    //内容标题
                    title: "客服QQ",
                    //内容以何种事件展开，取值：click|hover|none
                    trigger: "click",
                    //内容默认是否显示，取值：true|false
                    open: true,
                    //QQ列表
                    items: [
                      {
                        //QQ名称
                        title: "业务客服",
                        //QQ号码
                        qq: "1234567",
                        //自定义QQ图标绝对地址，图标尺寸必须为16x16，如果不想使用自定义图标，请不要写此属性
                        image: "http://www.kpdown.com/sexv/soft_.gif"
                      },
                      {
                        title: "技术客服",
                        qq: "1234568"
                      },
                      {
                        title: "售后客服",
                        qq: "1234569"
                      }
                    ]
                  },{
                    //tel用来显示联系电话
                    type: "tel",
                    title: "联系电话",
                    trigger: "hover",
                    open: false,
                    //电话列表
                    items: [
                      {
                        //作为超链接的title属性，鼠标移到电话上显示
                        title: "总部号码",
                        //电话号码，直接显示在列表中
                        tel: "13200001111",
                        //自定义电话图标绝对地址，图标尺寸必须为16x16，如果不想使用自定义图标，请不要写此属性
                        image: "http://www.kpdown.com/sexv/soft_.gif"
                      },{
                        title: "朝阳区分机",
                        tel: "13200001112"
                      }
                    ]
                  },
                  {
                    //text用来显示文本内容
                    //文本内容无图标，只有标题和内容
                    type: "text",
                    title: "其他信息",
                    trigger: "none",
                    open: true,
                    items: [
                      {
                        //标题即文本的开头，加粗显示；如果不想指定标题，请不要写此属性
                        title: "公告：",
                        //文本内容，紧跟标题
                        text: "关于服务器维护通知",
                        //文本内容链接地址，如果不希望文本是超链接，请不要写此属性
                        href: "http://www.baidu.com"
                      },
                      {
                        title: "联系地址：",
                        text: "北京市海淀区华强大厦Y座2-07B"
                      }
                    ]
                  }
                ]
              }
            );
          });
        </script>
      </body>
    </html>
  