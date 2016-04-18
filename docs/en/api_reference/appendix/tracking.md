# Tracking Parameters
Retrieving the information on which type of ads are clicked will be possible from Sponsored Search API tracking parameters. <br>
This functions can easily confirm the effect of ads, which it may leads to a better advertisement.<br>
<br>
This tracking function is designed for third party tool providers who use the Sponsored Search API. <br>
Third party tool providers are allowed to use the tracking data only for effectiveness measurement on their own system. <br>
Providers are not allowed to provide, transfer, or sell the raw tracking data to their customers (advertisers).<br>
<br>
When you set the tracking parameters in the destination URL of Ads, the conversion cannot be measured definitely.<br>
The number of Download of application for Android can be measured, when you set the URL without the tracking parameters in the destination URL of Ads.<br>
<br>

Parameter | Description | URL Format
---------- | ------------------- | ----------------------
creative |Displays Ad Tracking ID (adTrackId).<br>* An unique ID given to each ad. It differs from Ad ID (adId).| http://www.example.com/?creative={creative} 
keyword | Displays bidding keyword.| http://www.example.com/?keyword={keyword} 
matchtype | Displays match type.<br> Details are below.<br> - e: Exact Match<br> - p: Phrase Match<br> - b：Broad Match|http://www.example.com/?matchtype={matchtype} 
device | Displays the device clicked from. <br>Details are below.<br> - m: Smartphone and WAP phone (feature phone)<br> - t: Tablet<br> - c: PC | http://www.example.com/?device={device}<br>
ifmobile | Value will return when ads are clicked from Smartphone or WAP mobile.<br>* Can set only through custom URL.<br>* Also available for QuickLink of Ad Display Option.| http://www.example.com/?ifmobile={ifmobile:[value]}
ifnotmobile| Value will return when ads are clicked from Tablet or PC.<br>* Can set only through custom URL.<br>* Also available for QuickLink of Ad Display Option.|http://www.example.com/?ifnotmobile={ifnotmobile:[value]}
lpurl | The Landing Page URL. Can use for setting to Tracking URL.<br>*Available only for entity that been set for Advanced URL. | - Landing Page URL: http://example.com<br>- Tracking URL setting: {lpurl}?creative=XXXXXXXX<br>- Delivered URL: http://example.com?creative=XXXXXXXX

