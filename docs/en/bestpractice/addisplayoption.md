# Ad Display Option
## What is “Ad Display Option”?
Ad Display Option is a function of displaying additional information such as a link to other URL page or phone number to Sponsored Search.   
    
There are two features for Ad Display Option:  
* "QuickLink" (Displays a link to other URL page on bottom of the ads)
* "CallExtension" (Displays phone number).  
  
There are two advantages from using Ad Display Option.    
1. Ad spaces become larger and increase the visibility. This will raise the click rate.
2. Can easily access to the page user desires. This will raise the convenience.

## How to operate from Sponsored Search API
To display ads for Ad Display Option, use the three services below from Sponsored Search API.  
##### 1.	FeedItemService 
FeedItemService can retrieve and add/update/delete the FeedItem.  
FeedItem is a component of text, URL link, or phone number to display as Ad Display Option.
  
##### 2.	CampaignFeedService  
CampaignFeedService can set the FeedItem to campaign and retrieve the FeedItem that is set to campaign.
  
##### 3.	AdGroupFeedService
AdGroupFeedService can set the FeedItem to ad group and retrieve the FeedItem that is set to ad group.  
  
## Examples
Company A is planning add the below Ad Display Option by Sponsored Search API for the promotion.
  
##### QuickLink
No                | LINK_TEXT             | LINK_URL                                 
----------------- | --------------------- | -----------------------------------------
1 | Sale | www.example.jp/sale
2 | Store List | www.example.jp/store
3 | Ranking | www.example.jp/ranking
4 | Support | www.example.jp/support
5 | Coupon | www.example.jp/coupon
6 | Special Sale | www.example.jp/specialsale
7 | Point Information | www.example.jp/point
   
##### CallExtension
No                | CALL_PHONE_NUMBER                                 
----------------- | ---------------------
1 | 0120-45-6789

#### 1.	Adding FeedItem
Add FeedItem to Sponsored Search account using FeedItemService.   
For this example, each Ad Display Option will be added to the account of company A (ID: 100000001).  
##### <Request Sample> [For QUICKLINK]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V4">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                  <ns1:feedAttributeValue>Sale</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                  <ns1:feedAttributeValue>http://www.example.jp/sale</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                  <ns1:feedAttributeValue>Store List</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                  <ns1:feedAttributeValue>http://www.example.jp/store</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                  <ns1:feedAttributeValue>Ranking</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                  <ns1:feedAttributeValue>http://www.example.jp/ranking</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                  <ns1:feedAttributeValue>Support</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                  <ns1:feedAttributeValue>http://www.example.jp/support</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                  <ns1:feedAttributeValue>Coupon</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                  <ns1:feedAttributeValue>http://www.example.jp/coupon</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                  <ns1:feedAttributeValue>Special Sale</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                  <ns1:feedAttributeValue>http://www.example.jp/specialsale</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                  <ns1:feedAttributeValue>Point Information</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                  <ns1:feedAttributeValue>http://www.example.jp/point</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### <Response Sample> [For QUICKLINK]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V4">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>FeedItemService</ns1:service>
         <ns1:remainingQuota>9995</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>5</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>20.1486</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>FeedItemReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedItemId>1</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                     <ns1:feedAttributeValue>セール</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://www.example.jp/sale</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
               </ns1:feedItem>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedItemId>2</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                     <ns1:feedAttributeValue>店舗一覧</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://www.example.jp/store</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
               </ns1:feedItem>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedItemId>3</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                     <ns1:feedAttributeValue>ランキング</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://www.example.jp/ranking</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
               </ns1:feedItem>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedItemId>4</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                     <ns1:feedAttributeValue>問合せ</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://www.example.jp/support</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
               </ns1:feedItem>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedItemId>5</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                     <ns1:feedAttributeValue>クーポン</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://www.example.jp/coupon</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
               </ns1:feedItem>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedItemId>6</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                     <ns1:feedAttributeValue>特別セール</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://www.example.jp/specialsale</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
               </ns1:feedItem>
            </ns1:values>
           <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedItemId>7</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                     <ns1:feedAttributeValue>ポイント</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://www.example.jp/point</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
               </ns1:feedItem>
            </ns1:values>                            
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### <Request Sample> [For CALLEXTENSION]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>takami</ns1:apiAccountPassword>
       </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>1000000161</ns1:accountId>
                <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                <ns1:operand>
                    <ns1:accountId>1000000161</ns1:accountId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                        <ns1:feedAttributeValue>0120-45-6789</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                </ns1:operand>
           </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### <Response Sample> [For CALLEXTENSION]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V4">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>FeedItemService</ns1:service>
         <ns1:remainingQuota>9992</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.907</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>FeedItemReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedItemId>1</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                     <ns1:feedAttributeValue>0120-45-6789</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                  <ns1:devicePreference>SMART_PHONE</ns1:devicePreference>
               </ns1:feedItem>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
#### 2. Setting to Campaign
FeedItem will be set to campaign using CampaignFeedService.   
For this example, QuickLink[No.1-4] and CallExtension[No.1] will be set to campaign.  
##### <Request Sample>
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V4">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
         <ns1:accountId>1000000001</ns1:accountId>
      </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:campaignId>100000003</ns1:campaignId>
               <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
               <ns1:campaignFeed>
                  <ns1:feedItemId>1</ns1:feedItemId>
               </ns1:campaignFeed>
               <ns1:campaignFeed>
                  <ns1:feedItemId>2</ns1:feedItemId>
               </ns1:campaignFeed>
               <ns1:campaignFeed>
                  <ns1:feedItemId>3</ns1:feedItemId>
               </ns1:campaignFeed>
               <ns1:campaignFeed>
                  <ns1:feedItemId>4</ns1:feedItemId>
               </ns1:campaignFeed>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:campaignId>100000003</ns1:campaignId>
               <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
               <ns1:campaignFeed>
                  <ns1:feedItemId>1</ns1:feedItemId>
               </ns1:campaignFeed>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### <Response Sample>
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V4"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignFeedService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignFeedReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignFeedList>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000003</ns1:campaignId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:campaignFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000003</ns1:campaignId>
                            <ns1:feedItemId>1</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>
                         <ns1:campaignFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000003</ns1:campaignId>
                            <ns1:feedItemId>2</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>
                         <ns1:campaignFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000003</ns1:campaignId>
                            <ns1:feedItemId>3</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>
                          <ns1:campaignFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000003</ns1:campaignId>
                            <ns1:feedItemId>4</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>
                    </ns1:campaignFeedList>
               </ns1:values>
               <ns1:values>
                   <ns1:operationSucceeded>true</ns1:operationSucceeded>
                   <ns1:campaignFeedList>
                       <ns1:accountId>100000001</ns1:accountId>
                       <ns1:campaignId>100000003</ns1:campaignId>
                       <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                       <ns1:campaignFeed>
                           <ns1:accountId>100000001</ns1:accountId>
                           <ns1:campaignId>100000003</ns1:campaignId>
                           <ns1:feedItemId>1</ns1:feedItemId>
                           <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                       </ns1:campaignFeed>
                   </ns1:campaignFeedList>
                </ns1:values>
           </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
#### 3.	Setting to Ad Group
FeedItem will be set to ad group using AdGroupFeedService.   
For this example, QuickLink[No.5] will be set to ad group.  
##### <Request Sample>
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V4">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
         <ns1:accountId>1000000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
      </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:campaignId>100000003</ns1:campaignId>
               <ns1:adGroupId>100000113</ns1:adGroupId>
               <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
               <ns1:adGroupFeed>
                  <ns1:feeditemId>5</ns1:feeditemId>
               </ns1:adGroupFeed>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:campaignId>100000003</ns1:campaignId>
               <ns1:adGroupId>100000113</ns1:adGroupId>
               <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
               <ns1:adGroupFeed>
                  <ns1:feeditemId>1</ns1:feeditemId>
               </ns1:adGroupFeed>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### <Response Sample>
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V4"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupFeedService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupFeedReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000003</ns1:campaignId>
                        <ns1:adGroupId>100000113</ns1:adGroupId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:adGroupFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000003</ns1:campaignId>
                            <ns1:adGroupId>100000113</ns1:adGroupId>
                            <ns1:feedItemId>5</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                       </ns1:adGroupFeed>
                    </ns1:adGroupFeedList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000003</ns1:campaignId>
                        <ns1:adGroupId>100000113</ns1:adGroupId>
                        <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                        <ns1:adGroupFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000003</ns1:campaignId>
                            <ns1:adGroupId>100000113</ns1:adGroupId>
                            <ns1:feedItemId>1</ns1:feedItemId>
                            <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                       </ns1:adGroupFeed>
                    </ns1:adGroupFeedList>
                </ns1:values>                
           </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
#### 4.	Change of FeedItem setting to Campaign
QuickLink setting to the campaign will be updated, because the special sale has been decided to be held.  
For this example, QuickLink[No.1] will be deleted and QuickLink[No.6] will be set to campaign.  
##### <Request Sample> [For QUICKLINK]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V4">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
         <ns1:accountId>1000000001</ns1:accountId>
      </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:campaignId>100000003</ns1:campaignId>
               <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
              <ns1:campaignFeed>
                  <ns1:feedItemId>2</ns1:feedItemId>
               </ns1:campaignFeed>
               <ns1:campaignFeed>
                  <ns1:feedItemId>3</ns1:feedItemId>
               </ns1:campaignFeed>
               <ns1:campaignFeed>
                  <ns1:feedItemId>4</ns1:feedItemId>
               </ns1:campaignFeed>
              <ns1:campaignFeed>
                  <ns1:feedItemId>6</ns1:feedItemId>
               </ns1:campaignFeed>               
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:campaignId>100000003</ns1:campaignId>
               <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
               <ns1:campaignFeed>
                  <ns1:feedItemId>1</ns1:feedItemId>
               </ns1:campaignFeed>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### <Response Sample> [For QUICKLINK]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V4"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignFeedService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignFeedReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignFeedList>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000003</ns1:campaignId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:campaignFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000003</ns1:campaignId>
                            <ns1:feedItemId>2</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>
                         <ns1:campaignFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000003</ns1:campaignId>
                            <ns1:feedItemId>3</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>
                         <ns1:campaignFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000003</ns1:campaignId>
                            <ns1:feedItemId>4</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>
                       <ns1:campaignFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000003</ns1:campaignId>
                            <ns1:feedItemId>6</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>     
                    </ns1:campaignFeedList>
               </ns1:values>
               <ns1:values>
                   <ns1:operationSucceeded>true</ns1:operationSucceeded>
                   <ns1:campaignFeedList>
                       <ns1:accountId>100000001</ns1:accountId>
                       <ns1:campaignId>100000003</ns1:campaignId>
                       <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                       <ns1:campaignFeed>
                           <ns1:accountId>100000001</ns1:accountId>
                           <ns1:campaignId>100000003</ns1:campaignId>
                           <ns1:feedItemId>1</ns1:feedItemId>
                           <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                       </ns1:campaignFeed>
                   </ns1:campaignFeedList>
                </ns1:values>
           </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### <Request Sample> [For CALLEXTENSION]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V4"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignFeedService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignFeedReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignFeedList>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000003</ns1:campaignId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:campaignFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000003</ns1:campaignId>
                            <ns1:feedItemId>2</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>
                         <ns1:campaignFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000003</ns1:campaignId>
                            <ns1:feedItemId>3</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>
                         <ns1:campaignFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000003</ns1:campaignId>
                            <ns1:feedItemId>4</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>
                       <ns1:campaignFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000003</ns1:campaignId>
                            <ns1:feedItemId>6</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>     
                    </ns1:campaignFeedList>
               </ns1:values>
               <ns1:values>
                   <ns1:operationSucceeded>true</ns1:operationSucceeded>
                   <ns1:campaignFeedList>
                       <ns1:accountId>100000001</ns1:accountId>
                       <ns1:campaignId>100000003</ns1:campaignId>
                       <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                       <ns1:campaignFeed>
                           <ns1:accountId>100000001</ns1:accountId>
                           <ns1:campaignId>100000003</ns1:campaignId>
                           <ns1:feedItemId>1</ns1:feedItemId>
                           <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                       </ns1:campaignFeed>
                   </ns1:campaignFeedList>
                </ns1:values>
           </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### <Response Sample> [For CALLEXTENSION]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V4"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignFeedService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignFeedReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
              <ns1:values>
                   <ns1:operationSucceeded>true</ns1:operationSucceeded>
                   <ns1:campaignFeedList>
                       <ns1:accountId>100000001</ns1:accountId>
                       <ns1:campaignId>100000003</ns1:campaignId>
                       <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                       <ns1:campaignFeed></ns1:campaignFeed>
                   </ns1:campaignFeedList>
                </ns1:values>
           </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
#### 5.	Change of FeedItem setting to Ad Group
QuickLink setting to the ad group will be updated, because the coupon offer has ended.   
For this example, QuickLink[No.5] will be deleted and QuickLink[No.7] will be set toad group. 
##### <Request Sample>
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000003</ns1:campaignId>
                    <ns1:adGroupId>100000113</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:adGroupFeed>
                        <ns1:feeditemId>7</ns1:feeditemId>
                    </ns1:adGroupFeed>
               </ns1:operand>
          </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### <Response Sample>
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V4"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupFeedService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupFeedReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000003</ns1:campaignId>
                        <ns1:adGroupId>100000113</ns1:adGroupId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:adGroupFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000003</ns1:campaignId>
                            <ns1:adGroupId>100000113</ns1:adGroupId>
                            <ns1:feedItemId>7</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                       </ns1:adGroupFeed>
                    </ns1:adGroupFeedList>
                </ns1:values>
           </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### 6.	Canceling the CallExtension
The call center has been abolished, so the setting of CallExtension to the ad group will be deleted. 
##### <Request Sample>
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V4">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
         <ns1:accountId>1000000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
      </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
           <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:campaignId>100000003</ns1:campaignId>
               <ns1:adGroupId>100000113</ns1:adGroupId>
               <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
               <ns1:adGroupFeed></ns1:adGroupFeed>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### <Response Sample>
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V4"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupFeedService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupFeedReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000003</ns1:campaignId>
                        <ns1:adGroupId>100000113</ns1:adGroupId>
                        <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                        <ns1:adGroupFeed></ns1:adGroupFeed>
                    </ns1:adGroupFeedList>
                </ns1:values>                
           </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
