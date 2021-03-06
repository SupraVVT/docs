### TLS 1.x by default passes the SCH_SEND_AUX_RECORD flag to the underlying SCHANNEL API

|   |   |
|---|---|
|Details|When using TLS 1.x, the .NET Framework relies on the underlying Windows SCHANNEL API. Starting with .NET Framework 4.6, the [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/desktop/api/schannel/ns-schannel-_schannel_cred) flag is passed by default to SCHANNEL. This causes SCHANNEL to split data to be encrypted into two separate records, the first as a single byte and the second as <em>n</em>-1 bytes. In rare cases, this breaks communication between clients and existing servers that make the assumption that the data resides in a single record.|
|Suggestion|If this change breaks communication with an existing server, you can disable sending the [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/desktop/api/schannel/ns-schannel-_schannel_cred) flag and restore the previous behavior of not splitting data into separate records by adding the following switch to the [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app configuration file:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Net.DontEnableSchSendAuxRecord=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre> <blockquote> [!IMPORTANT] This setting is provided for backward compatibility only. Its use is otherwise not recommended.</blockquote> |
|Scope|Edge|
|Version|4.6|
|Type|Retargeting|
|Affected APIs|<ul><li><xref:System.Net.Security.SslStream?displayProperty=nameWithType></li><li><xref:System.Net.ServicePointManager?displayProperty=nameWithType></li><li><xref:System.Net.Http.HttpClient?displayProperty=nameWithType></li><li><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType></li><li><xref:System.Net.HttpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.FtpWebRequest?displayProperty=nameWithType></li></ul>|

