<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128545109/13.1.4%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/E4325)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->
<!-- default file list -->
*Files to look at*:

* [Default.aspx](./CS/WebSite/Default.aspx) (VB: [Default.aspx](./VB/WebSite/Default.aspx))
<!-- default file list end -->
# How to paste URL to ASPxHtmlEditor as a hyperlink
<!-- run online -->
**[[Run Online]](https://codecentral.devexpress.com/e4325/)**
<!-- run online end -->


<p>To paste URL to ASPxHtmlEditor as a hyperlink, you can handle client-side <a href="http://documentation.devexpress.com/#AspNet/DevExpressWebASPxHtmlEditorScriptsASPxClientHtmlEditor_CommandExecutedtopic"><u>ASPxClientHtmlEditor.CommandExecuted</u></a> and <a href="http://documentation.devexpress.com/#AspNet/DevExpressWebASPxHtmlEditorScriptsASPxClientHtmlEditor_HtmlChangedtopic"><u>ASPxClientHtmlEditor.HtmlChanged</u></a> events. In the CommandExecuted event handler check the command name. If it is ASPxClientCommandConsts.KBPASTE_COMMAND or ASPxClientCommandConsts.PASTE_COMMAND, get html from ASPxHtmlEditor in the HtmlChanged event handler and replace each URL with the corresponding hyperlink in HTML format.</p><p>Please note that in this example we didn’t change the ASPxHtmlEditor behavior for Internet Explorer because this browser wraps URLs in hyperlink in HTML format by default.</p>

<br/>


