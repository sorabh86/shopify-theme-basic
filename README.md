# Shopify Theme Development

This is a practise project for development of shopify theme.
Development of basic 

## Installations
1. Install `chocolatey` on windows (powershell)
```powershell
[System.Net.WebRequest]::DefaultWebProxy.Credentials = [System.Net.CredentialCache]::DefaultCredentials; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```
2. Install `themekit` on chocolatey package manager
```powershell
choco install themekit
```

## Steps to setup local environment
1. Create your local theme folder
2. create following folder in theme folder
    * assets
    * config
    * layout
    * locales
    * sections
    * snippets
    * templates
3. add file in folder layout/theme.liquid
```html
<html>
<head>
    {{ content_for_header }}
</head>
<body>
    {{ content_for_layout }}
</body>
</html>
```
4. Login to shopify partner website
5. Under Apps, search Theme Access and install it, Add user and copy access key.
6. Sales channels -> Search Online Store -> Theme, add your theme zipped folder, then publish.
7. Open powershell on local theme folder and run following command, it will create config.yml configuration file for auto CI/CD pipeline.
```powershell
theme configure -s <yourapp>.myshopify.com -t <your-theme-id> -p <your-shopify-theme-access-key>
``` 
8. command to watch changes and push to remote theme.
```powershell
theme watch --allow-live
```

## Apprendix
* [Shopify Theme](https://shopify.dev/themes)