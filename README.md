# **Identify and remove suspicious browser extensions**

![](https://miro.medium.com/v2/resize:fit:700/1*v19Hy_Fkbr6GeRQl-vaZZw.png)

# **How to identify suspicious extensions**

To spot potentially harmful extensions, look out for these warning signs:

1. **Unfamiliar extensions**: Review your installed extensions regularly and look for any that you don’t remember installing.
2. **Vague or generic names**: Be wary of extensions with names that don’t clearly indicate their function.
3. **Excessive permissions**: Question why an extension needs certain permissions. For example, a simple calculator shouldn’t need access to your browsing history.
4. **Sudden changes in browsing experience**: An increase in pop-up ads, unexpected redirects, or significant browser slowdown could indicate a malicious extension.
5. **Poor reviews or low ratings**: Check user reviews and ratings before installing. While not foolproof, they can provide insights into potential issues.
6. **Suspicious behavior**: Extensions that change your homepage, search engine, or other browser settings without your permission are likely malicious.
7. **Unwanted installations**: If you notice new extensions appearing without your knowledge, your browser may be compromised.

# **How to check extension is malicious and remove malicious extensions**

**Firefox**: Open the menu, choose “Add-ons and themes,” find the questionable extension in the “Extensions” tab click on any extension to see in details analysis

![](https://miro.medium.com/v2/resize:fit:700/1*5vqdsBQi7PUoZ2Pk3Q1iIg.png)

Here You can see first is details second is permission when you read this you easily detect what they need to run this and what permission allow to run .

![](https://miro.medium.com/v2/resize:fit:677/1*YPflECD34X0LDaf-jqWJ2Q.png)

Here I debuging this run this command

> about:debugging#/runtime/this-firefox
> 

and click on manifest.json file

![](https://miro.medium.com/v2/resize:fit:700/1*beZj_qYcF7lq5UTmCMs6Dw.png)

# **Analysis of First Manifest (“MSG_extensionName_”)**

- Generic Name: “__MSG_extensionName__” is a placeholder, suspicious as legitimate extensions use specific names.
- Excessive Access: “<all_urls>” in content scripts allows access to all websites, unnecessary for lazy loading.
- Incognito Access: “incognito”: “spanning” enables private browsing access, risky and unneeded.
- All Frames: “all_frames”: true lets it run in iframes, excessive for the stated purpose.
- Empty Permissions: permissions: [] is misleading; “<all_urls>” indirectly grants broad access.
- Conclusion: Suspicious due to generic name, excessive permissions, and unneeded incognito access. Recommend removal.

![](https://miro.medium.com/v2/resize:fit:446/1*1PdnDGVj6QGeBWKMKdA9_w.png)

Here I debugging one more extension and try to read manifest.json file

![](https://miro.medium.com/v2/resize:fit:679/1*tbUjaxlBvDu2F39dxg13lw.png)

# **Why Second Manifest (“Firefox Multi-Account Containers”) Is Not Suspicious**

- **Clear Name**: Specific name “Firefox Multi-Account Containers” indicates a legitimate purpose.
- **Legitimate Permissions**: “<all_urls>”, cookies, tabs, etc., align with its purpose of managing containers.
- **Trusted Source**: Official Mozilla GitHub link (homepage_url) confirms credibility.
- **No Incognito Access**: “incognito”: “not_allowed” reduces privacy risks.
- **Detailed Features**: Includes icons, options UI, and commands, showing transparency and functionality.
- **Conclusion**: Not suspicious; it’s a well-documented, trusted extension by Mozilla.

![](https://miro.medium.com/v2/resize:fit:629/1*evXbJ6HOFdOzQVpUxuaYTg.png)

Then right click on three dots and click on remove it

![](https://miro.medium.com/v2/resize:fit:700/1*R7vk68Aik6SsAH2Wi58QnA.png)

Here I finally remove it suspicious extension

![](https://miro.medium.com/v2/resize:fit:488/1*76TeSQPL5_Lfn55qfIfAPg.png)
