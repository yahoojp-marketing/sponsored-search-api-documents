# Tracking Parameters
Retrieving the information on which type of ads are clicked will be possible from Sponsored Search API tracking parameters. <br>
This functions can easily confirm the effect of ads, which it may leads to a better advertisement.<br>
Tracking parameteres available on Sponsored Search API are as follows.<br>
<br>
[Note]<br>
This function is designed for third party tool providers who use the Sponsored Search API. <br>
Third party tool providers are allowed to use the tracking data only for effectiveness measurement on their own system. <br>
Providers are not allowed to provide, transfer, or sell the raw tracking data to their customers (advertisers).<br>
<br>
Conversion Analytics on Mobile App Download ads is available for Android App only. And it can count a download event by user when he/she directly goes to download via 'Google Play Store App' from your ad, but a download occurred on 'Google Play Store' browser edition cannot be a conersion counted.<br>
<br>


| Parameter | Description | Sample URL Format |
| ---------- | ------------------- | ---------------------- |
| creative | Ad Tracking ID <br> An ID assigned to each ad for tracking purpose. Differing from Ad ID. | Landing Page URL <br> http://www.example.com/?creative={creative} <br> Tracking URL <br> http://www.example.com/?lp={lpurl}&creative={creative}  |
| keyword | Bidded keyword | Landing Page URL  <br> http://www.example.com/?keyword={keyword} <br> Tracking URL <br> http://www.example.com/?lp={lpurl}&keyword={keyword} |
| matchtype | Match type of the keyword <br> e: Exact Match <br> p: Phrase Match <br> b: Broad Match | Landing Page URL <br> http://www.example.com/?matchtype={matchtype} <br> Tracking URL <br> http://www.example.com/?lp={lpurl}&matchtype={matchtype} |
| device | Device type <br> m: Smartphone and mobile <br> t: Tablet <br> c: PC | Landing Page URL  <br> http://www.example.com/?device={device} <br> Tracking URL <br> http://www.example.com/?lp={lpurl}&device={device} |
| campaignid | Campaign tracking ID <br>  An ID assigned to each campaign for tracking purpose. Differing from Campaign ID. | Landing Page URL <br> http://www.example.com/?campaignid={campaignid} <br> Tracking URL <br> http://www.example.com/?lp={lpurl}&campaignid={campaignid}|
| adgroupid |Ad group tracking ID <br> An ID assigned to each Ad group for tracking purpose. Differing from Ad group ID. | Landing Page URL <br> http://www.example.com/?adgroupid={adgroupid} <br> Tracking URL <br> http://www.example.com/?lp={lpurl}&adgroupid={adgroupid}|
| feeditemid |Ad display option tracking ID <br> An ID assigned to each Ad display option (such as QuickLinks, Callout, etc.) for tracking purpose. Differing from Ad display option ID. | Landing Page URL <br> http://www.example.com/?feeditemid={feeditemid} <br> Tracking URL <br> http://www.example.com/?lp={lpurl}&feeditemid={feeditemid} |
| ifmobile | Any value can be appended to the URL when ads are clicked from Smartphone, if you enable this parameter. It will allow you to convert it to Smartphone URL and to add parameters. <br> * Available for Landing Page URL, Tracking URL and Custom parameters. | http://www.example.com/?ifmobile={ifmobile:[value]} |
| ifnotmobile| Any value can be appended to the URL when ads are clicked from PC/Tablet, if you enable this parameter. It will allow you to convert it to PC/Tablet URL and to add parameters. <br> * Available for Landing Page URL, Tracking URL and Custom parameters. | http://www.example.com/?ifnotmobile={ifnotmobile:[value]} |
| lpurl | Landing Page URL is inserted into the part of this {lpurl}. It is available for Tracking URL | For the case when Landing Page URL is <br> http://www.example.com /?param=1 <br> Tracking URL:  <br> http://www.example.com /?lp={lpurl} <br> The URL after ad click:  <br> http://www.example.com /?lp=http://www.example.com /%3Fparam%3D1 |
| lpurl+2 | For the case when 2 times encoding of symbols (?, =, “, #, t, ‘,) and a blank space are needed on Tracking URL which includes "lpurl" (Landing Page URL). | For the case when Landing Page URL is <br> http://www.example.com/?param=1 <br> Tracking URL:  <br> http://www.example.com/?lp={lpurl+2} <br> The URL after ad click: <br> http://www.example.com/?lp=http://www.example.com/%253Fparam%253D1 |
| lpurl+3 | For the case when 3 times encoding of symbols (?, =, “, #, t, ‘,) and a blank space are needed on Tracking URL which includes "lpurl" (Landing Page URL). | For the case when Landing Page URL is <br> http://www.example.com /?param=1 <br> Tracking URL:  <br> http://www.example.com/?lp={lpurl+3} <br> The URL after ad click: <br> http://www.example.com/?lp=http://www.example.com/%25253Fparam%25253D1 |
| unescapedlpurl | For the case no encoding is needed on Tracking URL which includes "lpurl" (Landing Page URL). <br> It can be put only on start of URL. | For the case when Landing Page URL is <br> http://www.example.com /?param=1 <br> Tracking URL:  <br> {unescapedlpurl}&param2=2 <br> The URL after ad click: <br> http://www.example.com/?param=1&param2=2 |
| escapedlpurl | For the case when encoding of symbols (:, /, ?, =, %,) is needed on Tracking URL which includes "lpurl" (Landing Page URL). | For the case when Landing Page URL is <br> http://www.example.com /?param=1 <br> Tracking URL: <br> http://www.example.com/?lp={escapedlpurl} <br> The URL after ad click: <br> http://www.example.com/?lp=http:%3A%2F%2Fwww.example.com%2F%3Fparam%3D |
| escapedlpurl+2 | For the case when 2 times encoding of symbols (:, /, ?, =, %,) are needed on Tracking URL which includes "lpurl" (Landing Page URL). | For the case when Landing Page URL is <br> http://www.example.com /?param=1 <br> Tracking URL:  <br> http://www.example.com/?lp={escapedlpurl+2} <br> The URL after ad click: <br> http://www.example.com/?lp=http:%253A%252F%252Fwww.example.com%252F%253Fparam%253D1 |
| escapedlpurl+3 | For the case when 3 times encoding of symbols (:, /, ?, =, %,) are needed on Tracking URL which includes "lpurl" (Landing Page URL). | For the case when Landing Page URL is <br> http://www.example.com /?param=1 <br> Tracking URL:  <br> http://www.example.com/?lp={escapedlpurl+3} <br> The URL after ad click: <br> http://www.example.com/?lp=http:%25253A%25252F%25252Fwww.example.com%25252F%25253Fparam%25253D1 |
