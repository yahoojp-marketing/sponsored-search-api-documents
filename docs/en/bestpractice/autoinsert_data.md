# Data Auto Insertion (Data Insertion)
## What is “Data Auto Insertion”?
Data Auto Insertion is a function of changing the title and descriptions of the Sponsored Search ads.<br>
"Data Insertion" can automatically insert the ad title and description flexibly.

## How to operate from Sponsored Search API
To display ads for Data Auto Insertion, use the three services below from Sponsored Search API.

##### 1.	FeedFolderService 
FeedFolderService can retrieve and add/update/delete the FeedFolder information. <br>
FeedFolder is a component of data, which will be used for Data Auto Insertion.
  
##### 2.	FeedItemService  
FeedItemService can add/update/delete the list for the ads from FeedFolder information.

##### 3.	AdGroupAdService
AdGroupAdService can create the ads using the functions for Data Auto Insertion.

## Examples
Company A is planning to add the data list below by Sponsored Search API for the promotion.
  
##### Sale product list
<table class="standard">
                <tr>
                    <th valign="top" >
                        <p>Product (String)</p>
                    </th>
                    <th valign="top" >
                        <p>Price (Price)</p>
                    </th>
                    <th valign="top">
                        <p>Final sale date (Date)</p>
                    </th>
                    <th valign="top" >
                        <p>CampaignId</p>
                    </th>
                    <th valign="top" >
                        <p>AdGroupId</p>
                    </th>
                </tr>
                <tr>
                    <td valign="top">
                        <p>Product 101</p>
                    </td>
                    <td valign="top">
                        <p>100</p>
                    </td>
                    <td valign="top">
                        <p>20151231 000000</p>
                    </td>
                    <td valign="top">
                        <p>500001</p>
                    </td>
                    <td valign="top">
                        <p>600001</p>
                    </td>
                </tr>
                <tr>
                    <td valign="top">
                        <p>Product 102</p>
                    </td>
                    <td valign="top">
                        <p>300</p>
                    </td>
                    <td valign="top">
                        <p>20151231 000000</p>
                    </td>
                    <td valign="top">
                        <p>500001</p>
                    </td>
                    <td valign="top">
                        <p> </p>
                    </td>
                </tr>
                <tr>
                    <td valign="top">
                        <p>Product 103</p>
                    </td>
                    <td valign="top">
                        <p>1,000</p>
                    </td>
                    <td valign="top">
                        <p>20151231 000000</p>
                    </td>
                    <td valign="top">
                        <p>500002</p>
                    </td>
                    <td valign="top">
                        <p> </p>
                    </td>
                </tr>
</table>
*CampaignId and AdGroupId are to set the data on the specific campaign and ad group ID. Cbr>
Can leave the setting blank, if specifying is not necessary.

#### 1.	Adding FeedFolder
Add Feed Folder to Sponsored Search account using FeedFolderService. <br>
For this example, "Sale product list" will be added to the account of company A (ID: 100000001).

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:v5="http://ss.yahooapis.jp/V5">
   <soapenv:Header>
      <v5:RequestHeader>
         <v5:license>XXXX-XXXX-XXXX-XXXX</v5:license>
         <v5:apiAccountId>XXXX-XXXX-XXXX-XXXX</v5:apiAccountId>
         <v5:apiAccountPassword>passwd</v5:apiAccountPassword>
         <v5:accountId>100000001</v5:accountId>
         <v5:onBehalfOfAccountId>XXXXX-XXXX-XXXXX-XXXX</v5:onBehalfOfAccountId>
         <v5:onBehalfOfPassword>passwd2</v5:onBehalfOfPassword>
      </v5:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <v5:mutate>
         <v5:operations>
            <v5:operator>ADD</v5:operator>
            <v5:accountId>100000001</v5:accountId>
            <v5:operand>
               <v5:accountId>100000001</v5:accountId>
               <v5:feedFolderName>Sale product list</v5:feedFolderName>
               <v5:feedAttribute>
                  <v5:feedAttributeName>Product</v5:feedAttributeName>
                  <v5:placeholderField>AD_CUSTOMIZER_STRING</v5:placeholderField>
               </v5:feedAttribute>
               <v5:feedAttribute>
                  <v5:feedAttributeName>Price</v5:feedAttributeName>
                  <v5:placeholderField>AD_CUSTOMIZER_PRICE</v5:placeholderField>
               </v5:feedAttribute>
               <v5:feedAttribute>
                  <v5:feedAttributeName>Last sale date</v5:feedAttributeName>
                  <v5:placeholderField>AD_CUSTOMIZER_DATE</v5:placeholderField>
               </v5:feedAttribute>
               <v5:placeholderType>AD_CUSTOMIZER</v5:placeholderType>
            </v5:operand>
         </v5:operations>
      </v5:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>FeedFolderService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>1.2862</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>FeedFolderReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedFolder>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedFolderId>20001</ns1:feedFolderId>
                  <ns1:feedFolderName>Sale product list</ns1:feedFolderName>
                  <ns1:feedAttribute>
                     <ns1:feedAttributeId>1</ns1:feedAttributeId>
                     <ns1:feedAttributeName>Product</ns1:feedAttributeName>
                     <ns1:placeholderField>AD_CUSTOMIZER_STRING</ns1:placeholderField>
                  </ns1:feedAttribute>
                  <ns1:feedAttribute>
                     <ns1:feedAttributeId>2</ns1:feedAttributeId>
                     <ns1:feedAttributeName>Price</ns1:feedAttributeName>
                     <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                  </ns1:feedAttribute>
                  <ns1:feedAttribute>
                     <ns1:feedAttributeId>3</ns1:feedAttributeId>
                     <ns1:feedAttributeName>Last sale date</ns1:feedAttributeName>
                     <ns1:placeholderField>AD_CUSTOMIZER_DATE</ns1:placeholderField>
                  </ns1:feedAttribute>
                  <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
               </ns1:feedFolder>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### 2.	Adding FeedItem
Next, use FeedItemService to add and set the data to the FeedFolder that was created earlier.

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:v5="http://ss.yahooapis.jp/V5">
   <soapenv:Header>
      <v5:RequestHeader>
         <v5:license>XXXX-XXXX-XXXX-XXXX</v5:license>
         <v5:apiAccountId>XXXX-XXXX-XXXX-XXXX</v5:apiAccountId>
         <v5:apiAccountPassword>passwd</v5:apiAccountPassword>
         <v5:accountId>100000001</v5:accountId>
         <v5:onBehalfOfAccountId>XXXXX-XXXX-XXXXX-XXXX</v5:onBehalfOfAccountId>
         <v5:onBehalfOfPassword>passwd2</v5:onBehalfOfPassword>
      </v5:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <v5:mutate>
         <v5:operations>
            <v5:operator>ADD</v5:operator>
            <v5:accountId>100000001</v5:accountId>
            <v5:placeholderType>AD_CUSTOMIZER</v5:placeholderType>
            <v5:operand>
               <v5:accountId>100000001</v5:accountId>
               <v5:feedFolderId>20001</v5:feedFolderId>
               <v5:feedItemAttribute>
                  <v5:placeholderField>AD_CUSTOMIZER_STRING</v5:placeholderField>
                  <v5:feedAttributeId>1</v5:feedAttributeId>
                  <v5:feedAttributeValue>Product 101</v5:feedAttributeValue>
               </v5:feedItemAttribute>
               <v5:feedItemAttribute>
                  <v5:placeholderField>AD_CUSTOMIZER_PRICE</v5:placeholderField>
                  <v5:feedAttributeId>2</v5:feedAttributeId>
                  <v5:feedAttributeValue>100</v5:feedAttributeValue>
               </v5:feedItemAttribute>
               <v5:feedItemAttribute>
                  <v5:placeholderField>AD_CUSTOMIZER_DATE</v5:placeholderField>
                  <v5:feedAttributeId>3</v5:feedAttributeId>
                  <v5:feedAttributeValue>20151231 000000</v5:feedAttributeValue>
               </v5:feedItemAttribute>
               <v5:placeholderType>AD_CUSTOMIZER</v5:placeholderType>
               <v5:targetingCampaign>
                  <v5:targetingCampaignId>500001</v5:targetingCampaignId>
               </v5:targetingCampaign>
               <v5:targetingAdGroup>
                  <v5:targetingAdGroupId>600001</v5:targetingAdGroupId>
               </v5:targetingAdGroup>
            </v5:operand>
            <v5:operand>
               <v5:accountId>100000001</v5:accountId>
               <v5:feedFolderId>20001</v5:feedFolderId>
               <v5:feedItemAttribute>
                  <v5:placeholderField>AD_CUSTOMIZER_STRING</v5:placeholderField>
                  <v5:feedAttributeId>1</v5:feedAttributeId>
                  <v5:feedAttributeValue>Product 102</v5:feedAttributeValue>
               </v5:feedItemAttribute>
               <v5:feedItemAttribute>
                  <v5:placeholderField>AD_CUSTOMIZER_PRICE</v5:placeholderField>
                  <v5:feedAttributeId>2</v5:feedAttributeId>
                  <v5:feedAttributeValue>300</v5:feedAttributeValue>
               </v5:feedItemAttribute>
               <v5:feedItemAttribute>
                  <v5:placeholderField>AD_CUSTOMIZER_DATE</v5:placeholderField>
                  <v5:feedAttributeId>3</v5:feedAttributeId>
                  <v5:feedAttributeValue>20151231 000000</v5:feedAttributeValue>
               </v5:feedItemAttribute>
               <v5:placeholderType>AD_CUSTOMIZER</v5:placeholderType>
               <v5:targetingCampaign>
                  <v5:targetingCampaignId>500001</v5:targetingCampaignId>
               </v5:targetingCampaign>
            </v5:operand>
            <v5:operand>
               <v5:accountId>100000001</v5:accountId>
               <v5:feedFolderId>53161</v5:feedFolderId>
               <v5:feedItemAttribute>
                  <v5:placeholderField>AD_CUSTOMIZER_STRING</v5:placeholderField>
                  <v5:feedAttributeId>1</v5:feedAttributeId>
                  <v5:feedAttributeValue>Product 103</v5:feedAttributeValue>
               </v5:feedItemAttribute>
               <v5:feedItemAttribute>
                  <v5:placeholderField>AD_CUSTOMIZER_PRICE</v5:placeholderField>
                  <v5:feedAttributeId>2</v5:feedAttributeId>
                  <v5:feedAttributeValue>1,000</v5:feedAttributeValue>
               </v5:feedItemAttribute>
               <v5:feedItemAttribute>
                  <v5:placeholderField>AD_CUSTOMIZER_DATE</v5:placeholderField>
                  <v5:feedAttributeId>3</v5:feedAttributeId>
                  <v5:feedAttributeValue>20151231 000000</v5:feedAttributeValue>
               </v5:feedItemAttribute>
               <v5:placeholderType>AD_CUSTOMIZER</v5:placeholderType>
               <v5:targetingCampaign>
                  <v5:targetingCampaignId>500001</v5:targetingCampaignId>
               </v5:targetingCampaign>
            </v5:operand>
         </v5:operations>
      </v5:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>FeedItemService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>1.5086</ns1:timeTakenMillis>
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
                  <ns1:feedFolderId>20001</ns1:feedFolderId>
                  <ns1:feedItemId>30001</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_STRING</ns1:placeholderField>
                     <ns1:feedAttributeId>1</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>Product 101</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                     <ns1:feedAttributeId>2</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>100</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_DATE</ns1:placeholderField>
                     <ns1:feedAttributeId>4</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>20151231 000000</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
                  <ns1:targetingCampaign>
                     <ns1:targetingCampaignId>868992</ns1:targetingCampaignId>
                  </ns1:targetingCampaign>
                  <ns1:targetingAdGroup>
                     <ns1:targetingAdGroupId>308006520</ns1:targetingAdGroupId>
                  </ns1:targetingAdGroup>
               </ns1:feedItem>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedFolderId>20001</ns1:feedFolderId>
                  <ns1:feedItemId>30001</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_STRING</ns1:placeholderField>
                     <ns1:feedAttributeId>1</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>Product 102</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                     <ns1:feedAttributeId>2</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>300</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_DATE</ns1:placeholderField>
                     <ns1:feedAttributeId>4</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>20151231 000000</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
                  <ns1:targetingCampaign>
                     <ns1:targetingCampaignId>868992</ns1:targetingCampaignId>
                  </ns1:targetingCampaign>
               </ns1:feedItem>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedFolderId>20001</ns1:feedFolderId>
                  <ns1:feedItemId>30001</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_STRING</ns1:placeholderField>
                     <ns1:feedAttributeId>1</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>Product 103</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                     <ns1:feedAttributeId>2</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>1,000</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_DATE</ns1:placeholderField>
                     <ns1:feedAttributeId>3</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>20151231 000000</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
                  <ns1:targetingCampaign>
                     <ns1:targetingCampaignId>868993</ns1:targetingCampaignId>
                  </ns1:targetingCampaign>
               </ns1:feedItem>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### 3.	Adding AdGroupAd
Then, use AdGroupAdService to create the ads for the added data in FeedItemService.<br>
Also, in order to display the ads from Data Auto Insertion, another ad that is not using Data Auto Insertion function have to be available.<br>
*In this example, two of different ads are created.<br>
*Cannot use BulkService to submit ads.

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:v5="http://ss.yahooapis.jp/V5">
   <soapenv:Header>
      <v5:RequestHeader>
         <v5:license>XXXX-XXXX-XXXX-XXXX</v5:license>
         <v5:apiAccountId>XXXX-XXXX-XXXX-XXXX</v5:apiAccountId>
         <v5:apiAccountPassword>passwd</v5:apiAccountPassword>
         <v5:accountId>100000001</v5:accountId>
         <v5:onBehalfOfAccountId>XXXXX-XXXX-XXXXX-XXXX</v5:onBehalfOfAccountId>
         <v5:onBehalfOfPassword>passwd2</v5:onBehalfOfPassword>
      </v5:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <v5:mutate>
         <v5:operations>
            <v5:operator>ADD</v5:operator>
            <v5:accountId>100000001</v5:accountId>
            <!--1 or more repetitions:-->
            <v5:operand>
               <v5:accountId>100000001</v5:accountId>
               <v5:campaignId>1001</v5:campaignId>
               <v5:adGroupId>10001</v5:adGroupId>
               <v5:adName>Best Practice Ad</v5:adName>
               <v5:userStatus>ACTIVE</v5:userStatus>
               <v5:ad xsi:type="v5:TextAd2">
                  <v5:type>TEXT_AD2</v5:type>
                  <v5:url>http://www.example.jp</v5:url>
                  <v5:displayUrl>www.example.jp</v5:displayUrl>
                  <v5:headline>人気の{=Sale product list.Product}が大特価</v5:headline>
                  <v5:description>{=Sale product list.Price}円で販売。</v5:description>
                  <v5:description2>終了まであと{=COUNTDOWN(Sale product list.Last sale date,"ja")}</v5:description2>
               </v5:ad>
            </v5:operand>
            <v5:operand>
               <v5:accountId>100000001</v5:accountId>
               <v5:campaignId>1002</v5:campaignId>
               <v5:adName>Best Practice Normal Ad</v5:adName>
               <v5:userStatus>ACTIVE</v5:userStatus>
               <v5:ad xsi:type="v5:TextAd2">
                  <v5:type>TEXT_AD2</v5:type>
                  <v5:url>http://www.example.jp</v5:url>
                  <v5:displayUrl>www.example.jp</v5:displayUrl>
                  <v5:headline>人気の商品が大特価</v5:headline>
                  <v5:description>期間限定特別価格で販売。</v5:description>
                  <v5:description2>１２月３１日まで</v5:description2>
               </v5:ad>
            </v5:operand>
         </v5:operations>
      </v5:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>AdGroupAdService</ns1:service>
         <ns1:remainingQuota>1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>1.1128</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>AdGroupAdReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroupAd>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:campaignId>1001</ns1:campaignId>
                  <ns1:campaignName>Best Practice Campaign</ns1:campaignName>
                  <ns1:adGroupId>10001</ns1:adGroupId>
                  <ns1:adGroupName>Best Practice AdGroup</ns1:adGroupName>
                  <ns1:adId>100001</ns1:adId>
                  <ns1:adTrackId>0</ns1:adTrackId>
                  <ns1:adName>Best Practice Ad</ns1:adName>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:ad xsi:type="ns1:TextAd2">
                     <ns1:type>TEXT_AD2</ns1:type>
                     <ns1:url>http://www.example.jp</ns1:url>
                     <ns1:displayUrl>www.example.jp</ns1:displayUrl>
                     <ns1:headline>人気の{=Sale product list.Product}が大特価</ns1:headline>
                     <ns1:description>{=Sale product list.Price}円で販売。</ns1:description>
                     <ns1:description2>終了まであと{=COUNTDOWN(Sale product list.Last sale date,"ja")}</ns1:description2>
                  </ns1:ad>
                  <ns1:feedFolderId>20001</ns1:feedFolderId>
               </ns1:adGroupAd>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroupAd>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:campaignId>1002</ns1:campaignId>
                  <ns1:campaignName>Best Practice Campaign</ns1:campaignName>
                  <ns1:adGroupId>10001</ns1:adGroupId>
                  <ns1:adGroupName>Best Practice AdGroup</ns1:adGroupName>
                  <ns1:adId>100001</ns1:adId>
                  <ns1:adTrackId>0</ns1:adTrackId>
                  <ns1:adName>Best Practice Normal Ad</ns1:adName>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:ad xsi:type="ns1:TextAd2">
                     <ns1:type>TEXT_AD2</ns1:type>
                     <ns1:url>http://www.example.jp</ns1:url>
                     <ns1:displayUrl>www.example.jp</ns1:displayUrl>
                     <ns1:headline>人気の商品が大特価</ns1:headline>
                     <ns1:description>期間限定特別価格で販売。</ns1:description>
                     <ns1:description2>１２月３１日まで</ns1:description2>
                  </ns1:ad>
               </ns1:adGroupAd>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### 4.	Change of FeedItem
The data have to be changed from the change of price.<br>
Instead of recreating the ads again for the change, only updating the FeedItemService can solve this.<br>
Changing the data will automatically change the ad titles and/or descriptions.

##### Sale product list (After the change)
<table class="standard">
                <tr>
                    <th valign="top" >
                        <p>Product (String)</p>
                    </th>
                    <th valign="top" >
                        <p>Price (Price)</p>
                    </th>
                    <th valign="top">
                        <p>Final sale date (Date)</p>
                    </th>
                    <th valign="top" >
                        <p>CampaignId</p>
                    </th>
                    <th valign="top" >
                        <p>AdGroupId</p>
                    </th>
                </tr>
                <tr>
                    <td valign="top">
                        <p>Product 101</p>
                    </td>
                    <td valign="top">
                        <p>90</p>
                    </td>
                    <td valign="top">
                        <p>20151231 000000</p>
                    </td>
                    <td valign="top">
                        <p>500001</p>
                    </td>
                    <td valign="top">
                        <p>600001</p>
                    </td>
                </tr>
                <tr>
                    <td valign="top">
                        <p>Product 102</p>
                    </td>
                    <td valign="top">
                        <p>350</p>
                    </td>
                    <td valign="top">
                        <p>20151231 000000</p>
                    </td>
                    <td valign="top">
                        <p>500001</p>
                    </td>
                    <td valign="top">
                        <p> </p>
                    </td>
                </tr>
                <tr>
                    <td valign="top">
                        <p>Product 103</p>
                    </td>
                    <td valign="top">
                        <p>1,000</p>
                    </td>
                    <td valign="top">
                        <p>20151231 000000</p>
                    </td>
                    <td valign="top">
                        <p>500002</p>
                    </td>
                    <td valign="top">
                        <p> </p>
                    </td>
                </tr>
</table>

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:v5="http://ss.yahooapis.jp/V5">
   <soapenv:Header>
      <v5:RequestHeader>
         <v5:license>XXXX-XXXX-XXXX-XXXX</v5:license>
         <v5:apiAccountId>XXXX-XXXX-XXXX-XXXX</v5:apiAccountId>
         <v5:apiAccountPassword>passwd</v5:apiAccountPassword>
         <v5:accountId>100000001</v5:accountId>
         <v5:onBehalfOfAccountId>XXXXX-XXXX-XXXXX-XXXX</v5:onBehalfOfAccountId>
         <v5:onBehalfOfPassword>passwd2</v5:onBehalfOfPassword>
      </v5:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <v5:mutate>
         <v5:operations>
            <v5:operator>SET</v5:operator>
            <v5:accountId>100000001</v5:accountId>
            <v5:placeholderType>AD_CUSTOMIZER</v5:placeholderType>
            <v5:operand>
               <v5:accountId>100000001</v5:accountId>
               <v5:feedFolderId>200001</v5:feedFolderId>
               <v5:feedItemId>300001</v5:feedItemId>
               <v5:feedItemAttribute>
                  <v5:placeholderField>AD_CUSTOMIZER_PRICE</v5:placeholderField>
                  <v5:feedAttributeId>2</v5:feedAttributeId>
                  <v5:feedAttributeValue>90</v5:feedAttributeValue>
               </v5:feedItemAttribute>
               <v5:placeholderType>AD_CUSTOMIZER</v5:placeholderType>
               <v5:targetingCampaign>
                  <v5:targetingCampaignId>500001</v5:targetingCampaignId>
               </v5:targetingCampaign>
               <v5:targetingAdGroup>
                  <v5:targetingAdGroupId>600001</v5:targetingAdGroupId>
               </v5:targetingAdGroup>
            </v5:operand>
            <v5:operand>
               <v5:accountId>100000001</v5:accountId>
               <v5:feedFolderId>200001</v5:feedFolderId>
               <v5:feedItemId>300001</v5:feedItemId>
               <v5:feedItemAttribute>
                  <v5:placeholderField>AD_CUSTOMIZER_PRICE</v5:placeholderField>
                  <v5:feedAttributeId>2</v5:feedAttributeId>
                  <v5:feedAttributeValue>350</v5:feedAttributeValue>
               </v5:feedItemAttribute>
               <v5:placeholderType>AD_CUSTOMIZER</v5:placeholderType>
               <v5:targetingCampaign>
                  <v5:targetingCampaignId>500001</v5:targetingCampaignId>
               </v5:targetingCampaign>
            </v5:operand>
            <v5:operand>
               <v5:accountId>100000001</v5:accountId>
               <v5:feedFolderId>200001</v5:feedFolderId>
               <v5:feedItemId>300001</v5:feedItemId>
               <v5:placeholderType>AD_CUSTOMIZER</v5:placeholderType>
               <v5:targetingCampaign>
                  <v5:targetingCampaignId>500001</v5:targetingCampaignId>
               </v5:targetingCampaign>
            </v5:operand>
         </v5:operations>
      </v5:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>FeedItemService</ns1:service>
         <ns1:remainingQuota>9993</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>3</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>1.1774</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>FeedItemReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>SET</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedFolderId>200001</ns1:feedFolderId>
                  <ns1:feedItemId>300001</ns1:feedItemId>
                  <ns1:approvalStatus>APPROVED_WITH_REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_STRING</ns1:placeholderField>
                     <ns1:feedAttributeId>1</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>Product 101</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                     <ns1:feedAttributeId>2</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>90</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_DATE</ns1:placeholderField>
                     <ns1:feedAttributeId>3</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>20151231 000000</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
                  <ns1:targetingCampaign>
                     <ns1:targetingCampaignId>500001</ns1:targetingCampaignId>
                  </ns1:targetingCampaign>
                  <ns1:targetingAdGroup>
                     <ns1:targetingAdGroupId>600001</ns1:targetingAdGroupId>
                  </ns1:targetingAdGroup>
               </ns1:feedItem>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedFolderId>200001</ns1:feedFolderId>
                  <ns1:feedItemId>300001</ns1:feedItemId>
                  <ns1:approvalStatus>APPROVED_WITH_REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_STRING</ns1:placeholderField>
                     <ns1:feedAttributeId>1</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>Product 102</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                     <ns1:feedAttributeId>2</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>350</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_DATE</ns1:placeholderField>
                     <ns1:feedAttributeId>3</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>20151231 000000</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
                  <ns1:targetingCampaign>
                     <ns1:targetingCampaignId>500001</ns1:targetingCampaignId>
                  </ns1:targetingCampaign>
               </ns1:feedItem>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedFolderId>200001</ns1:feedFolderId>
                  <ns1:feedItemId>300001</ns1:feedItemId>
                  <ns1:approvalStatus>APPROVED_WITH_REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_STRING</ns1:placeholderField>
                     <ns1:feedAttributeId>1</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>Product 103</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                     <ns1:feedAttributeId>2</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>1,000</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute>
                     <ns1:placeholderField>AD_CUSTOMIZER_DATE</ns1:placeholderField>
                     <ns1:feedAttributeId>3</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>20151231 000000</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
                  <ns1:targetingCampaign>
                     <ns1:targetingCampaignId>500001</ns1:targetingCampaignId>
                  </ns1:targetingCampaign>
               </ns1:feedItem>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
