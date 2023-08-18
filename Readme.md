<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128545109/13.1.4%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/E4325)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->

# HTML Editor for ASP.NET Web Forms - How to paste a URL as a hyperlink
<!-- run online -->
**[[Run Online]](https://codecentral.devexpress.com/128545109/)**
<!-- run online end -->

To paste a URL to [ASPxHtmlEditor](https://docs.devexpress.com/AspNet/DevExpress.Web.ASPxHtmlEditor.ASPxHtmlEditor) as a hyperlink, follow the steps below:

1. Subscribe to [CommandExecuted](https://docs.devexpress.com/AspNet/js-ASPxClientHtmlEditor.CommandExecuted) and [HtmlChanged](https://docs.devexpress.com/AspNet/js-ASPxClientHtmlEditor.HtmlChanged) events.

    ```aspx
    <dx:ASPxHtmlEditor ID="he" runat="server">
        <ClientSideEvents HtmlChanged="he_OnHtmlChanged" CommandExecuted="he_OnCommandExecuted" />
    </dx:ASPxHtmlEditor>
    ```

2. In the [CommandExecuted](https://docs.devexpress.com/AspNet/js-ASPxClientHtmlEditor.CommandExecuted) event handler, check if the `PASTE` command is executed.
  
    ```js
    function he_OnCommandExecuted(s, e) {
        if (e.commandName === ASPxClientCommandConsts.KBPASTE_COMMAND || e.commandName === ASPxClientCommandConsts.PASTE_COMMAND) 
            process = 0;
    }
    ```

3. In the [HtmlChanged](https://docs.devexpress.com/AspNet/js-ASPxClientHtmlEditor.HtmlChanged) event handler, obtain HTML code from the editor and replace each URL with the corresponding hyperlink in the HTML format.
   
    ```js
    function he_OnHtmlChanged(s, e) {
        if (process === 0) {
            process = -1;
            var text = s.GetHtml();
            s.SetHtml("");
            var newText = text.replace(/(?:(https?:\/\/[\/\w\.\,\-\?\=\&\%\+\#\&&amp;]*[^&lt;^&lt;a\s^\)]\/?))(?=<br>|\&nbsp|<\/div>|$|\)|\s|\))/g, "<a href=\"$1\">$1</a>");
            s.ExecuteCommand(ASPxClientCommandConsts.PASTEHTML_COMMAND, newText);
       }
    }
    ```
## Files to Review

* [Default.aspx](./CS/WebSite/Default.aspx) (VB: [Default.aspx](./VB/WebSite/Default.aspx))
