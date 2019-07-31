# Getting our SDKs to work with proxies

While our SDKs are not set up to work behind a proxy by default, there are solutions to getting this to work depending on your environment. 

## c#

Add and app.config (for console application) or web.config (for MVC application) to your project using these instruction: https://docs.microsoft.com/en-us/visualstudio/ide/how-to-add-app-config-file?view=vs-2019

Ensure that the default proxy in configured on your local machine (for e.g. in Internet Explorer). 

Add the following to the config fileL 
```
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <system.net>
   <defaultProxy enabled="true" useDefaultCredentials="true">
   <proxy usesystemdefault="true" bypassonlocal="true" />
   </defaultProxy>
</system.net>
</configuration>
```
This tells your app to use the default system wide proxy if your local machine uses a proxy as required by your employer. 

## node.js
