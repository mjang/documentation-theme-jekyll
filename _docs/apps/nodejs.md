---
title: Node.js
category: Sample Apps
category-order: 2
order: 1
---


> **Sample App** <br>
Download the sample app below or branch from github.<br><br>
<button type="button" class="btn btn-secondary"><i class="material-icons">file_download</i> DOWNLOAD</button>&nbsp;&nbsp;&nbsp;{% octicon mark-github class:"right left" aria-label:hi %}&nbsp;&nbsp;[View on Github](http://github.com){: .important}
{: .plain-blockquote}



### Running the Sample App  
The node sample app will use the OAuth 2.0 confidential client flow. An Authorization Code is exchanged for a token. Your app must be able to securely store and transmit information. Check out the section on [client types](#) to lean more about which authorization method to use.

#### Steps

1. Make sure you have node installed
2. From the command line navigate to the sample app folder and run 'npm install' to install dependencies
3. In the _.config_ file in the root of the sample app set the following variables.

```
CONST tenant = 'YOUR-TENANT-NAME.forgerock.com'
CONST client_id = 'APP-CLIENT-ID'
CONST secret = 'APP-SECRET'
```
{: .language-javascript}

Run 'npm start' to start the app. It will open in your default browser and will use port 3000.


### Where to go from here  



<br><br><br><br>
