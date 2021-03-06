---
title: IE and Microsoft Edge FAQ for IT Pros
description: Describes frequently asked questions about Internet Explorer and Microsoft Edge for IT professionals. 
audience: ITPro
manager: msmets
author: ramakoni1
ms.author: ramakoni
ms.reviewer: ramakoni, DEV_Triage
ms.prod: internet-explorer
ms.technology:
ms.topic: kb-support
ms.custom: CI=111020
ms.localizationpriority: Normal
# localization_priority: medium
# ms.translationtype: MT
ms.date: 01/23/2020
---
# Internet Explorer and Microsoft Edge frequently asked questions (FAQ) for IT Pros

## Cookie-related questions

### What is a cookie?

An HTTP cookie (the web cookie or browser cookie) is a small piece of data that a server sends to the user's web browser. The web browser may store the cookie and return it to the server together with the next request. For example, a cookie might be used to indicate whether two requests come from the same browser in order to allow the user to remain logged-in. The cookie records stateful information for the stateless HTTP protocol.

### How does Internet Explorer handle cookies?

For more information about how Internet Explorer handles cookies, see the following articles:

- [Beware Cookie Sharing in Cross-Zone Scenarios](https://blogs.msdn.microsoft.com/ieinternals/2011/03/10/beware-cookie-sharing-in-cross-zone-scenarios/)
- [A Quick Look at P3P](https://blogs.msdn.microsoft.com/ieinternals/2013/09/17/a-quick-look-at-p3p/)
- [Internet Explorer Cookie Internals FAQ](https://blogs.msdn.microsoft.com/ieinternals/2009/08/20/internet-explorer-cookie-internals-faq/)
- [Privacy Beyond Blocking Cookies](https://blogs.msdn.microsoft.com/ie/2008/08/25/privacy-beyond-blocking-cookies-bringing-awareness-to-third-party-content/)
- [Description of Cookies](https://support.microsoft.com/help/260971/description-of-cookies)

### Where does Internet Explorer store cookies?

To see where Internet Explorer stores its cookies, follow these steps:

1. Start File Explorer.
2. Select **Views** \> **Change folder and search options**.
3. In the **Folder Options** dialog box, select **View**.
4. In **Advanced settings**, select **Do not show hidden files, folders, or drivers**.
5. Clear **Hide protected operation system files (Recommended)**.
6. Select **Apply**.
7. Select **OK**.

The following are the folder locations where the cookies are stored:

**In Windows 10**  
C:\Users\username\AppData\Local\Microsoft\Windows\INetCache

**In Windows 8 and Windows 8.1**  
C:\Users\username\AppData\Local\Microsoft\Windows\INetCookies

**In Windows 7**  
C:\Users\username\AppData\Roaming\Microsoft\Windows\Cookies  
C:\Users\username\AppData\Roaming\Microsoft\Windows\Cookies\Low

### What is the per-domain cookie limit?

Since the June 2018 cumulative updates for Internet Explorer and Microsoft Edge, the per-domain cookie limit is increased from 50 to 180 for both browsers. The cookies vary by path. So, if the same cookie is set for the same domain but for different paths, it's essentially a new cookie.

There's still a 5 Kilobytes (KB) limit on the size of the cookie header that is sent out. This limit can cause some cookies to be lost after they exceed that value.

The JavaScript limitation was updated to 10 KB from 4 KB.

For more information, see [Internet Explorer Cookie Internals (FAQ)](https://blogs.msdn.microsoft.com/ieinternals/2009/08/20/internet-explorer-cookie-internals-faq/).

#### Additional information about cookie limits

**What does the Cookie RFC allow?**  
RFC 2109 defines how cookies should be implemented, and it defines minimum values that browsers support. According to the RFC, browsers would ideally have no limits on the size and number of cookies that a browser can handle. To meet the specifications, the user agent should support the following:

- At least 300 cookies total
- At least 20 cookies per unique host or domain name

For practicality, individual browser makers set a limit on the total number of cookies that any one domain or unique host can set. They also limit the total number of cookies that can be stored on a computer.

### Cookie size limit per domain

Some browsers also limit the amount of space that any one domain can use for cookies. This means that if your browser sets a limit of 4,096 bytes per domain for cookies, 4,096 bytes is the maximum available space in that domain even though you can set up to 180 cookies.

## Proxy Auto Configuration (PAC)-related questions

### Is an example Proxy Auto Configuration (PAC) file available?

Here is a simple PAC file:

```vb
function FindProxyForURL(url, host)
{
 return "PROXY proxyserver:portnumber";
}
```

> [!NOTE]
> The previous PAC always returns the **proxyserver:portnumber** proxy.

For more information about how to write a PAC file and about the different functions in a PAC file, see [the FindProxyForURL website](https://findproxyforurl.com/).

**Third-party information disclaimer**  
The third-party products that this article discusses are manufactured by companies that are independent of Microsoft. Microsoft makes no warranty, implied or otherwise, about the performance or reliability of these products.

### How to improve performance by using PAC scripts

- [Browser is slow to respond when you use an automatic configuration script](https://support.microsoft.com/help/315810/browser-is-slow-to-respond-when-you-use-an-automatic-configuration-scr)
- [Optimizing performance with automatic Proxyconfiguration scripts (PAC)](https://blogs.msdn.microsoft.com/askie/2014/02/07/optimizing-performance-with-automatic-proxyconfiguration-scripts-pac/)

## Other questions

### How to set home and start pages in Microsoft Edge and allow user editing

For more information, see the following blog article:

[How do I set the home page in Microsoft Edge?](https://blogs.msdn.microsoft.com/askie/2017/10/04/how-do-i-set-the-home-page-in-edge/)

### How to add sites to the Enterprise Mode (EMIE) site list

For more information about how to add sites to an EMIE list, see [Add multiple sites to the Enterprise Mode site list using a file and the Enterprise Mode Site List Manager (schema v.2)](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/add-multiple-sites-to-enterprise-mode-site-list-using-the-version-2-schema-and-enterprise-mode-tool).

### What is Content Security Policy (CSP)?

By using [Content Security Policy](https://docs.microsoft.com/microsoft-edge/dev-guide/security/content-security-policy), you create an allow list of sources of trusted content in the HTTP headers. You also pre-approve certain servers for content that is loaded into a webpage, and instruct the browser to execute or render only resources from those sources. You can use this technique to prevent malicious content from being injected into sites.

Content Security Policy is supported in all versions of Microsoft Edge. It lets web developers lock down the resources that can be used by their web application. This helps prevent [cross-site scripting](https://en.wikipedia.org/wiki/Cross-site_scripting) attacks that remain a common vulnerability on the web. However, the first version of Content Security Policy was difficult to implement on websites that used inline script elements that either pointed to script sources or contained script directly.

CSP2 makes these scenarios easier to manage by adding support for nonces and hashes for script and style resources. A nonce is a cryptographically strong random value that is generated on each page load that appears in both the CSP policy and in the script tags on the page. Using nonces can help minimize the need to maintain a list of allowed source URL values while also allowing trusted scripts that are declared in script elements to run.

For more information, see the following articles:

- [Introducing support for Content Security Policy Level 2](https://blogs.windows.com/msedgedev/2017/01/10/edge-csp-2/)
- [Content Security Policy](https://en.wikipedia.org/wiki/Content_Security_Policy)

### Where to find Internet Explorer security zones registry entries

Most of the Internet Zone entries can be found in [Internet Explorer security zones registry entries for advanced users](https://support.microsoft.com/help/182569/internet-explorer-security-zones-registry-entries-for-advanced-users).

This article was written for Internet Explorer 6 but is still applicable to Internet Explorer 11.

The default Zone Keys are stored in the following locations:

- HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Internet Settings\Zones
- HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Internet Settings\Zones

### Why don't HTML5 videos play in Internet Explorer 11?

To play HTML5 videos in the Internet Zone, use the default settings or make sure that the registry key value of **2701** under **Software\Microsoft\Windows\CurrentVersion\Internet Settings\Zones\3** is set to **0**.

- 0 (the default value): Allow
- 3: Disallow

This key is read by the **URLACTION\_ALLOW\_AUDIO\_VIDEO 0x00002701** URL action flag that determines whether media elements (audio and video) are allowed in pages in a URL security zone.

For more information, see [Unable to play HTML5 Videos in IE](https://blogs.msdn.microsoft.com/askie/2014/12/31/unable-to-play-html5-videos-in-ie/).

For Windows 10 N and Windows KN editions, you must also download the feature pack that is discussed in [Media feature pack for Windows 10 N and Windows 10 KN editions](https://support.microsoft.com/help/3010081/media-feature-pack-for-windows-10-n-and-windows-10-kn-editions).

For more information about how to check Windows versions, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-version-am-i-running)

### What is the Enterprise Mode Site List Portal?

This is a new feature to add sites to your enterprise mode site list XML. For more information, see [Enterprise Mode Site List Portal](https://github.com/MicrosoftEdge/enterprise-mode-site-list-portal).

### What is Enterprise Mode Feature?

For more information about this topic, see [Enterprise Mode and the Enterprise Mode Site List](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).

### Where can I obtain a list of HTTP Status codes?

For information about this list, see [HTTP Status Codes](https://docs.microsoft.com/windows/win32/winhttp/http-status-codes).

### What is end of support for Internet Explorer 11?

Internet Explorer 11 is the last major version of Internet Explorer. Internet Explorer 11 will continue receiving security updates and technical support for the lifecycle of the version of Windows on which it is installed.

For more information, see [Lifecycle FAQ — Internet Explorer and Edge](https://support.microsoft.com/help/17454/lifecycle-faq-internet-explorer).

### How to configure TLS (SSL) for Internet Explorer

For more information about how to configure TLS/SSL for Internet Explorer, see [Group Policy Setting to configure TLS/SSL](https://gpsearch.azurewebsites.net/#380).

### What is Site to Zone?

Site to Zone usually refers to one of the following:

**Site to Zone Assignment List**  
This is a Group Policy policy setting that can be used to add sites to the various security zones.

The Site to Zone Assignment List policy setting associates sites to zones by using the following values for the Internet security zones:

- Intranet zone
- Trusted Sites zone
- Internet zone
- Restricted Sites zone

If you set this policy setting to **Enabled**, you can enter a list of sites and their related zone numbers. By associating a site to a zone, you can make sure that the security settings for the specified zone are applied to the site.

**Site to Zone Mapping**  
Site to Zone Mapping is stored as the name of the key. The protocol is a registry value that has a number that assigns it to the corresponding zone. Internet Explorer will read from the following registry subkeys for the sites that are deployed through the Site to Zone assignment list:

- HKEY\_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet Settings\ZoneMap
- HKEY\_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet Settings\ZoneMapKey

**Site to Zone Assignment List policy**  
This policy setting is available for both Computer Configuration and User Configuration:

- Computer Configuration > Administrative Templates > Windows Components > Internet Explorer > Internet Control Panel > Security Page
- User Configuration > Administrative Templates > Windows Components > Internet Explorer > Internet Control Panel > Security Page

**References**  
[How to configure Internet Explorer security zone sites using group polices](https://blogs.msdn.microsoft.com/askie/2012/06/05/how-to-configure-internet-explorer-security-zone-sites-using-group-polices/)

### What are the limits for MaxConnectionsPerServer, MaxConnectionsPer1_0Server for the current versions of Internet Explorer?

For more information about these settings and limits, see [Connectivity Enhancements in Windows Internet Explorer 8](https://docs.microsoft.com/previous-versions/cc304129(v=vs.85)).

### What is the MaxConnectionsPerProxy setting, and what are the maximum allowed values for this setting?

The **MaxConnectionsPerProxy** setting controls the number of connections that a single-user client can maintain to a given host by using a proxy server.

For more information, see [Understanding Connection Limits and New Proxy Connection Limits in WinInet and Internet Explorer](https://blogs.msdn.microsoft.com/jpsanders/2009/06/29/understanding-connection-limits-and-new-proxy-connection-limits-in-wininet-and-internet-explorer/).
