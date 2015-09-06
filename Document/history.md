﻿#### 2015-09-07 00:23 两处小调整。
* 修改 readme.md 。
* 提交 release 版本的 demo/bin/wke.dll 。

#### 2015-09-04 20:40 修改项目 readme 文件。
* 增加文件 readme.md 描述项目相关信息，并在末尾附原项目 readme.txt 的内容。
* 删除原项目 readme.txt 。

#### 2015-09-04 19:56 实现 <input type="file"/> 文件选择功能。
* 实现 ChromeClient::runOpenPanel 函数，打开文件对话框，支持 multipe 属性多选文件。可通过 demo/bin/file.html 和 Document/demo/file.asp 测试。

#### 2015-09-04 19:53 增加从命令行提供的URL进行加载的功能。
* webBrowser 增加命令行支持，若有命令行参数，则将其作为URL加载。

#### 2015-09-03 10:37 增加项目规范、根据规范调整命名。
* 编写项目规范，位于 Document/rules.md，合作提交的朋友请按规范编写文档和代码。目前此规范还不完善，后续继续添加。
* 根据 Document/rules.md 中的命名规范，以及使语法更正确、含义更清晰，作了以下命名调整：
    - 更名 wkeClientHandler 为 wkeViewHandler（因这里的 "Client" 一词实际上是 WebKit 内部实现相关的东西，在接口中不需要）。
    - 更名 wkeSetClientHandler 为 wkeSetHandler （去掉 Client）。
    - 更名 IWebView::setClientHandler 为 IWebView::setHandler （去掉 Client）。
    - 更名 IWebView::getClientHandler 为 IWebView::handler （去掉 Client、成员函数获取属性不加 get）。
    - 更名 IWebView::cookieEnabled 为 IWebView::isCookieEnabled （获取是否属性前面加 is）。
    - 更名 IWebView::getCaret 为 IWebView::caretRect （成员函数获取属性不加 get、使含义更明确）。
    - 更名 IWebView::getViewDC 为 IWebView::viewDC （成员函数获取属性不加 get）。
    - 更名 IWebView::transparent 为 IWebView::isTransparent （获取是否属性前面加 is）。
    - 更名 IWebView::awaken 为 IWebView::wake（执行操作的函数使用动词）。
    - 更名 IWebView::contentsHeight 为 IWebView::contentHeight（content 即可代表所有内容，无需复数）。
    - 更名 IWebView::contentsWidth 为 IWebView::contentWidth（content 即可代表所有内容，无需复数）。
    - 更名 IWebView::contextMenuEvent 为 IWebView::fireContextMenuEvent（使含义更准确）。
    - 更名 IWebView::copy 为 IWebView::editorCopy （使含义更准确）。
    - 更名 IWebView::cut 为 IWebView::editorCut （使含义更准确）。
    - 更名 IWebView::delete_ 为 IWebView::editorDelete （使含义更准确）。
    - 更名 IWebView::focus 为 IWebView::setFocus （使含义更准确）。
    - 更名 IWebView::isLoadComplete 为 isLoadingCompleted （语法更准确、统一）。
    - 更名 IWebView::isLoaded 为 isLoadingSucceeded （语法更准确、统一）。
    - 更名 IWebView::isLoadFailed 为 isLoadingFailed （语法更准确、统一）。
    - 更名 IWebView::keyDown 为 IWebView::fireKeyDownEvent（使含义更准确）。
    - 更名 IWebView::keyPress 为 IWebView::fireKeyPressEvent（使含义更准确）。
    - 更名 IWebView::keyUp 为 IWebView::fireKeyUpEvent（使含义更准确）。
    - 更名 IWebView::mouseEvent 为 IWebView::fireMouseEvent（使含义更准确）。
    - 更名 IWebView::mouseWheel 为 IWebView::fireMouseWheelEvent（使含义更准确）。
    - 更名 IWebView::paste 为 IWebView::editorPaste （使含义更准确）。
    - 更名 IWebView::selectAll 为 IWebView::editorSelectAll  （使含义更准确）。
    - 更名 IWebView::tick 为 IWebView::IWebView::repaintIfNeeded（使含义更准确）。
    - 更名 IWebView::unfocus 为 IWebView::killFocus（使含义更准确） 。
    - 更名 jsObjectData 为 jsData（Object 函数统一不加 Object）。
    - 更名 jsObjectGetData 为 jsGetData（Object 函数统一不加 Object）。
    - 更名 ON_PAINT_UPDATED 为 wkeOnPaintUpdated（类型用大驼峰命名法）。
    - 更名 ON_TITLE_CHANGED 为 wkeOnTitleChanged（类型用大驼峰命名法）。
    - 更名 ON_URL_CHANGED 为 wkeOnUrlChanged（类型用大驼峰命名法）。
    - 更名 wkeInit 为 wkeInitialize （使含义更准确）。
    - 更名 wkeShutdown 为 wkeFinalize （使含义更准确）。
    - 更名 wkeVersion 为 wkeGetVersion（非成员函数获取数据加 get）。
    - 更名 wkeVersionString 为 wkeGetVersionString（非成员函数获取数据加 get）。
    - 更名 wkeTitle 为 wkeGetTitle，wkeTitleW 为 wkeGetTitleW（非成员函数获取数据加 get）。
    - 更名 wkeWidth 为 wkdGetWidth（非成员函数获取数据加 get）。
    - 更名 wkeHeight 为 wkdGetHeight（非成员函数获取数据加 get）。	
    - 更名 wkeWebViewName 为 wkeGetName（非成员函数获取数据加 get、WebView 相关操作函数命名统一不加 WebView）。
    - 更名 wkeZoomFactor 为 wkeGetZoomFactor（非成员函数获取数据加 get）。
    - 更名 wkeAwaken 为 wkeWake（wake 动词含义更准确）。
    - 更名 wkeContentsWidth 为 wkdGetContentWidth（content 即可代表所有内容无需复数、非成员函数获取数据加 get）。
    - 更名 wkeContentsHeight 为 wkeGetContentHeight（content 即可代表所有内容无需复数、非成员函数获取数据加 get）。
    - 更名 wkeSelectAll 为 wkeEditorSelectAll （使含义更准确）。
    - 更名 wkeCopy 为 wkeEditorCopy （使含义更准确）。
    - 更名 wkeCut 为 wkeEditorCut （使含义更准确）。
    - 更名 wkePaste 为 wkeEditorPaste （使含义更准确）。
    - 更名 wkeFocus 为 wkeSetFocus（使含义更准确）。
    - 更名 wkeUnfocus 为 wkeKillFocus（使含义更准确）。
    - 更名 wkeGlobalExec 为 wkeGetGlobalExec（非成员函数获取数据加 get）。
    - 更名 wkeIsLoadComplete 为 wkeIsLoadingCompleted  （语法更准确、统一）。
    - 更名 wkeIsLoaded 为 wkeIsLoadingSucceeded  （语法更准确、统一）。
    - 更名 wkeIsLoadFailed 为 wkeIsLoadingFailed  （语法更准确、统一）。
    - 更名 wkeMediaVolume 为 wkeGetMediaVolume（非成员函数获取数据加 get）。
    - 更名 wkeSetWebViewName 为 wkeSetName（WebView 相关操作函数命名统一不加 WebView）。
    - 更名 wkeCookieEnabled 为 wkeIsCookieEnabled（获取是否数据是前面加 is）。
    - 更名 wkeGetCaret 为 wkeGetCaretRect （使含义更明确）。

#### 2015-09-03 10:17 将回调全部集中到接口 wkeClientHandler 当中。
* 去掉 wkeBufHandler，将功能合并到 wkeClientHandler 当中。
* wkeClientHandler 中增加一个回调参数，以传递自定义参数。
* 去掉 wkeClientHandler 的 const 属性，避免在回调处理中要需要非 const 访问时导致问题。


#### 2015-08-31 02:13 修改 Document/history.md 的标题级别。 …
每条记录的标题修改为四级标题，因三级在浏览器中查看太大。


#### 2015-08-31 02:13 修改 Document/history.md 的记录格式。 …
每条记录不再使用严格的 markdown 格式，改为直接使用提交日志的文本，但增加 markdown 三级标题。


#### 2015-08-30 23:24 合并 zhanjx1314 实现的 POST 方式加载页面的功能。 …
合并 zhanjx1314 实现的 wkePostURL 函数，该函数可以 POST 方式加载页面。


#### 2015-08-30 22:59 合并 zhanjx1314 实现的获取 cookie 的功能。 …
合并 zhanjx1314 实现的获取 cookie 的功能（wchar_t* 版本），并在其基础上增加了一个 utf8* 版本的重载，另外在 webBrowser 中增加一个菜单项测试此功能。


#### 2015-08-30 02:00 调整 Document/history.md 标题级别（之前太大）。


#### 2015-08-30 01:40 修正 wkeLoadURL 加载中文路径 HTML 文件失败的问题。 …
wkeLoadURL 调用 `KURL::KURL(const KURL& base, const String& relative, const TextEncoding&)` 构造 KURL ，第二个参数传入的是 const char* 类型的 UTF-8 字符串以构造一个 WTF::String 对象，然而 WTF::String::String(const char*) 是把字符串按照 latin1 处理的，正确应该使用 WTF::String::fromUTF8 显式从 UTF-8 构造。可以用 wkeBrowser 加载 demo/bin/中文.html 测试。


#### 2015-08-30 01:36 增加 Document/utility.md 记录一些零碎信息。


#### 2015-08-30 01:23 修正 HTML 中图片地址包含中文时无法显示的问题。 …
WebCore::Document::completeURL 当中构造 KURL 对象时，会调用 encodeRelativeString 将所有 URL（包括本地路径）转换为 UTF-8 编码，导致文件打开失败，显然在 Windows 上路径应该是 GBK。可用 wkeBrowser 加载 demo/bin/english.html 测试。


#### 2015-08-30 01:26 调整 Document/history.md 记录日志的顺序，按时间从新到旧。


#### 2015-08-30 01:19 增加 webBrowser 拖放加载 HTML 文件的功能。


#### 2015-08-29 23:56 修正 jsSet、jsGet 始终访问的是第一次调用时的属性的问题。 …
JSC::Identifier 内部以 JSC::UString 保存属性名称，而 JSC::UString 内部把 char* 类型字符串的指针值作为其 hash 值，虽然在一个字符串内存上设置了与前次不同的字符串内容，但因为使用了同一内存地址（指针相同）， hash 值相同，会认为是同一个字符串。


#### 2015-08-29 22:14 修改 Javascript 绑定相关的接口。 …
* 修改 jsObject、jsArray 函数名为 jsEmptyObject、jsEmptyArray，使其名称更符合实际功能。
* 去掉 jsFunction 函数。
* 增加新的 jsObject、jsFunction 函数用于实现对象和函数的绑定，针对单独页面的绑定。
* 增加 Document 目录，用于存放一些说明性的东西。


#### 2015-08-29 21:22 合并从 SOUI 仓库获取的修改。 …
感谢 SOUI 的作者，其主要增加了两个功能：
* wkePaint 拷贝页面的内容图像到指定内存。
* wkeBufHandler 当页面的内容图像更新时回调通知。


#### 2015-08-29 21:16:57 忽略 build 目录（中间目录）。