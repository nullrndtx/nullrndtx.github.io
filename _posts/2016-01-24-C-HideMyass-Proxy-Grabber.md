---
layout: post
title: C# HideMyass Proxy Grabber
summary:
status: draft
hn-discussion:
---

```csharp
public static string[] grabProxy(string source)
{
    // Credits: randalltux // https://rndtx.id/
    var proxies = new List();
    foreach (Match m in Regex.Matches(source, @"([\s\S]*?)(\d+)"))
    {
      string port = m.Groups[2].Value;
      string ip = m.Groups[1].Value;
      ip = Regex.Replace(ip, @"(<(div|span) style=""display:none"">\d+.*?>|<.*?>)", "").Trim();
      proxies.Add(string.Concat(ip, ":", port));
    }
    return proxies.ToArray();
} 
```
