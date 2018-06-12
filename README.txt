Hi,

Just sharing with you an example for sending HTML emails using the Email Widget.

Don't forget to ```#define BLYNK_MAX_SENDBYTES 1024``` and keep it below 1024 bytes, including subject.

Also allow text/hetml on Blynk Email Widget settings.

Use [Link Shortner](https://goo.gl/) to make the picture link shorter. And [HTML Editor](https://html-online.com/editor/) to see changes on the HTML example.

```cpp
<table border="0" width="100%" cellspacing="0">
<tbody>
<tr>
<th style="background-color: #04c0f8; width: 46%; padding: 0px 10px; font-size: 32px;">HTML +&nbsp;<img src="https://goo.gl/VtPJWa" alt="" width="80" height="80" />&nbsp;= 🚀</th>
<th style="background-color: #04c0f8; margin-bottom: 5px; text-align: center; padding: 10px; font-family: sans-serif; font-size: 32px; width: 86.715%;">EMAIL</th>
</tr>
<tr>
<td style="background-color: #ffffff; font-size: 3px; width: 133%;" colspan="2">&nbsp;</td>
</tr>
<tr>
<td style="background-color: #f0f0f0; padding: 10px; font-family: verdana, sans-serif; width: 100%;" colspan="2">
<p style="text-align: center;"><strong>YOUR TEXT GOES HERE</strong></p>
</td>
</tr>
</tbody>
</table>
```

Use **\\** (backslash) before every **"** and that way the compiler won't consider it as a String stuff. So Arduino code should loop like:
```
String myHTML = String("<table border=\"0\" width=\"100%\" cellspacing=\"0\"><tbody><tr><th style=\"background-color: #04c0f8; width: 46%; padding: 0px 10px; font-size: 32px;\">HTML +&nbsp;<img src=\"https://goo.gl/VtPJWa\" alt=\"\" width=\"80\" height=\"80\" />&nbsp;= ☝</th><th style=\"background-color: #04c0f8; margin-bottom: 5px; text-align: center; padding: 10px; font-family: sans-serif; font-size: 32px; width: 86.715%;\">EMAIL</th></tr><tr><td style=\"background-color: #ffffff; font-size: 3px; width: 133%;\" colspan=\"2\">&nbsp;</td></tr><tr><td style=\"background-color: #f0f0f0; padding: 10px; font-family: verdana, sans-serif; width: 100%;\" colspan=\"2\"><p style=\"text-align: center;\"><strong>YOUR TEXT GOES HERE</strong></p></td></tr></tbody></table>");

Blynk.email("your_email@mail.com", "Subject: Button Logger", myHTML);
```
