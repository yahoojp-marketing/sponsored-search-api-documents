# AdGroupAdService
Use this service to get, add, update, or remove ad information.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/AdGroupAdService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/AdGroupAdService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### Overview
Use this service to create, update and remove ads.

#### Operation
Describe the operation which provides at AdGroupService.

## get
Returns ad information.

### Request

| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [AdGroupAdSelector](../data/AdGroupAdSelector.md) | The selector specifying ad for operation.| 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:campaignIds>100000001</ns1:campaignIds>
                <ns1:campaignIds>100000002</ns1:campaignIds>
                <ns1:adGroupIds>100000001</ns1:adGroupIds>
                <ns1:adGroupIds>100000002</ns1:adGroupIds>
                <ns1:adGroupIds>100000003</ns1:adGroupIds>
                <ns1:adGroupIds>100000004</ns1:adGroupIds>
                <ns1:adIds>100000001</ns1:adIds>
                <ns1:adIds>100000002</ns1:adIds>
                <ns1:adIds>100000003</ns1:adIds>
                <ns1:adIds>100000004</ns1:adIds>
                <ns1:adTypes>TEXT_AD2</ns1:adTypes>
                <ns1:adTypes>MOBILE_AD</ns1:adTypes>
                <ns1:adTypes>APP_AD</ns1:adTypes>
                <ns1:userStatuses>ACTIVE</ns1:userStatuses>
                <ns1:userStatuses>PAUSED</ns1:userStatuses>
                <ns1:approvalStatuses>APPROVED</ns1:approvalStatuses>
                <ns1:approvalStatuses>PRE_DISAPPROVED</ns1:approvalStatuses>
                <ns1:approvalStatuses>POST_DISAPPROVED</ns1:approvalStatuses>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>10</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [AdGroupAdPage](../data/AdGroupAdPage.md) | This object is a container for storing ad information entry. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns1="http://ss.yahooapis.jp/V6"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupAdService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:totalNumEntries>4</ns1:totalNumEntries>
                <ns1:Page.Type>AdGroupAdPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>Campaign</ns1:campaignName>
                        <ns1:adGroupId>100000001</ns1:adGroupId>
                        <ns1:adGroupTrackId>222222</ns1:adGroupTrackId>
                        <ns1:adGroupName>Text ad group</ns1:adGroupName>
                        <ns1:adId>100000002</ns1:adId>
                        <ns1:adTrackId>333333</ns1:adTrackId>
                        <ns1:adName>Text ad2</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:TextAd2">
                            <ns1:type>TEXT_AD2</ns1:type>
                            <ns1:advancedUrl>http://aaaa.jp</ns1:advancedUrl>
                            <ns1:advancedMobileUrl>http://aaaa.jp/mb</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
                            <ns1:customParameters>
                              <ns1:isRemove>FALSE</ns1:isRemove>
                              <ns1:parameters>
                                <ns1:key>site</ns1:key>
                                <ns1:value>yahoo</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id1</ns1:key>
                                <ns1:value>1234</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id2</ns1:key>
                                <ns1:value>a7h59A98yu</ns1:value>
                              </ns1:parameters>
                            </ns1:customParameters>
                            <ns1:advanced>TRUE</ns1:advanced>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>Headline</ns1:headline>
                            <ns1:description>Count down</ns1:description>
                            <ns1:description2>{=COUNTDOWN("2016/01/01 00:00:00","ja")}</ns1:description2>
                        </ns1:ad>
                        <ns1:feedFolderId>100000001</ns1:feedFolderId>
                    </ns1:adGroupAd>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>Campaign</ns1:campaignName>
                        <ns1:adGroupId>100000002</ns1:adGroupId>
                        <ns1:adGroupTrackId>333333</ns1:adGroupTrackId>
                        <ns1:adGroupName>Mobile ad group</ns1:adGroupName>
                        <ns1:adId>100000003</ns1:adId>
                        <ns1:adTrackId>444444</ns1:adTrackId>
                        <ns1:adName>Mobile ad</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:MobileAd">
                            <ns1:type>MOBILE_AD</ns1:type>
                            <ns1:advanced>FALSE</ns1:advanced>
                            <ns1:url>http://www.yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>Mobile ad headline</ns1:headline>
                            <ns1:description>Mobile ad description</ns1:description>
                            <ns1:markupLanguages>HTML</ns1:markupLanguages>
                            <ns1:markupLanguages>CHTML</ns1:markupLanguages>
                            <ns1:markupLanguages>XHTML</ns1:markupLanguages>
                            <ns1:mobileCarriers>DOCOMO</ns1:mobileCarriers>
                            <ns1:mobileCarriers>KDDI</ns1:mobileCarriers>
                            <ns1:mobileCarriers>SOFTBANK</ns1:mobileCarriers>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>Campaign</ns1:campaignName>
                        <ns1:adGroupId>100000003</ns1:adGroupId>
                        <ns1:adGroupTrackId>444444</ns1:adGroupTrackId>
                        <ns1:adGroupName>App ad group</ns1:adGroupName>
                        <ns1:adId>100000004</ns1:adId>
                        <ns1:adTrackId>555555</ns1:adTrackId>
                        <ns1:adName>App ad</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:AppAd">
                            <ns1:type>APP_AD</ns1:type>
                            <ns1:advancedUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedUrl>
                            <ns1:advancedMobileUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
                            <ns1:customParameters>
                              <ns1:isRemove>FALSE</ns1:isRemove>
                              <ns1:parameters>
                                <ns1:key>site</ns1:key>
                                <ns1:value>yahoo</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id1</ns1:key>
                                <ns1:value>1234</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id2</ns1:key>
                                <ns1:value>a7h59A98yu</ns1:value>
                              </ns1:parameters>
                            </ns1:customParameters>
                            <ns1:advanced>TRUE</ns1:advanced>
                            <ns1:headline>App ad headline</ns1:headline>
                            <ns1:description>App ad description1</ns1:description>
                            <ns1:description2>App ad description2</ns1:description2>
                            <ns1:appStore>IOS</ns1:appStore>
                            <ns1:appId>appid1234567890</ns1:appId>
                            <ns1:devicePreference>SMART_PHONE</ns1:devicePreference>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>Campaign</ns1:campaignName>
                        <ns1:adGroupId>100000003</ns1:adGroupId>
                        <ns1:adGroupTrackId>444444</ns1:adGroupTrackId>
                        <ns1:adGroupName>Ad group</ns1:adGroupName>
                        <ns1:adId>100000004</ns1:adId>
                        <ns1:adTrackId>555555</ns1:adTrackId>
                        <ns1:adName>Ad LPO</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:TextAd2">
                            <ns1:type>TEXT_AD2</ns1:type>
                            <ns1:advancedUrl>http://yahoo.co.jp/sample/url</ns1:advancedUrl>
                            <ns1:additionalAdvancedUrls>
                               <ns1:advancedUrl>http://yahoo.co.jp/sample/url1</ns1:advancedUrl>
                            </ns1:additionalAdvancedUrls>
                            <ns1:additionalAdvancedUrls>
                               <ns1:advancedUrl>http://yahoo.co.jp/sample/url2</ns1:advancedUrl>
                            </ns1:additionalAdvancedUrls>
                             <ns1:additionalAdvancedUrls>
                               <ns1:advancedUrl>http://yahoo.co.jp/sample/url3</ns1:advancedUrl>
                            </ns1:additionalAdvancedUrls>                          
                            <ns1:advancedMobileUrl>http://yahoo.co.jp/sample/mobile/url</ns1:advancedMobileUrl>
                            <ns1:additionalAdvancedMobileUrls>
                               <ns1:advancedMobileUrl>http://yahoo.co.jp/sample/mobile/url1</ns1:advancedMobileUrl>
                            </ns1:additionalAdvancedMobileUrls>
                             <ns1:additionalAdvancedMobileUrls>
                               <ns1:advancedMobileUrl>http://yahoo.co.jp/sample/mobile/url2</ns1:advancedMobileUrl>
                            </ns1:additionalAdvancedMobileUrls>                          
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
                            <ns1:customParameters>
                              <ns1:isRemove>FALSE</ns1:isRemove>
                              <ns1:parameters>
                                <ns1:key>site</ns1:key>
                                <ns1:value>yahoo</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id1</ns1:key>
                                <ns1:value>1234</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id2</ns1:key>
                                <ns1:value>a7h59A98yu</ns1:value>
                              </ns1:parameters>
                            </ns1:customParameters>
                            <ns1:advanced>TRUE</ns1:advanced>
                            <ns1:headline>App ad headline</ns1:headline>
                            <ns1:description>App ad description1</ns1:description>
                            <ns1:description2>App ad description2</ns1:description2>
                            <ns1:devicePreference>SMART_PHONE</ns1:devicePreference>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>               
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (ADD)
Add informations of ad.

### Request

| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [AdGroupAdOperation](../data/AdGroupAdOperation.md) | Ads and operation list of the operation. | 

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
         <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
         <ns1:accountId>100000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
      </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:operand>
               <ns1:campaignId>100000001</ns1:campaignId>
               <ns1:adGroupId>100000001</ns1:adGroupId>
               <ns1:adName>Text ad</ns1:adName>
               <ns1:userStatus>ACTIVE</ns1:userStatus>
               <ns1:ad xsi:type="ns1:TextAd2">
                  <ns1:type>TEXT_AD2</ns1:type>
                  <ns1:advancedUrl>http://aaaa.jp</ns1:advancedUrl>
                  <ns1:advancedMobileUrl>http://aaaa.jp/mb</ns1:advancedMobileUrl>
                  <ns1:trackingUrl><![CDATA[http://yahoo.co.jp?url={lpurl}&c={campaignid}&g={adgroupid}&a={creative}&type={site}&pid={id1}&vid={id2}]]></ns1:trackingUrl>
                  <ns1:customParameters>
                     <ns1:isRemove>FALSE</ns1:isRemove>
                     <ns1:parameters>
                        <ns1:key>site</ns1:key>
                        <ns1:value>yahoo</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id1</ns1:key>
                        <ns1:value>1234</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id2</ns1:key>
                        <ns1:value>a7h59A98yu</ns1:value>
                     </ns1:parameters>
                  </ns1:customParameters>
                  <ns1:advanced>TRUE</ns1:advanced>
                  <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                  <ns1:headline>Headline</ns1:headline>
                  <ns1:description>Cound down</ns1:description>
                  <ns1:description2>{=COUNTDOWN("2016/01/01 00:00:00","ja")}</ns1:description2>
               </ns1:ad>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:campaignId>100000001</ns1:campaignId>
               <ns1:adGroupId>100000003</ns1:adGroupId>
               <ns1:adName>App ad</ns1:adName>
               <ns1:userStatus>ACTIVE</ns1:userStatus>
               <ns1:ad xsi:type="ns1:AppAd">
                  <ns1:type>APP_AD</ns1:type>
                  <ns1:advancedUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedUrl>
                  <ns1:advancedMobileUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedMobileUrl>
                  <ns1:trackingUrl><![CDATA[http://yahoo.co.jp?url={lpurl}&c={campaignid}&g={adgroupid}&a={creative}&type={site}&pid={id1}&vid={id2}]]></ns1:trackingUrl>
                  <ns1:customParameters>
                     <ns1:isRemove>FALSE</ns1:isRemove>
                     <ns1:parameters>
                        <ns1:key>site</ns1:key>
                        <ns1:value>yahoo</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id1</ns1:key>
                        <ns1:value>1234</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id2</ns1:key>
                        <ns1:value>a7h59A98yu</ns1:value>
                     </ns1:parameters>
                  </ns1:customParameters>
                  <ns1:advanced>TRUE</ns1:advanced>
                  <ns1:headline>App ad headline</ns1:headline>
                  <ns1:description>App ad description1</ns1:description>
                  <ns1:description2>App ad description2</ns1:description2>
                  <ns1:appStore>IOS</ns1:appStore>
                  <ns1:appId>appid1234567890</ns1:appId>
                  <ns1:devicePreference>SMART_PHONE</ns1:devicePreference>
               </ns1:ad>
            </ns1:operand>
            <ns1:operand>
               <ns1:campaignId>100000001</ns1:campaignId>
               <ns1:adGroupId>100000001</ns1:adGroupId>
               <ns1:adName>Text ad</ns1:adName>
               <ns1:userStatus>ACTIVE</ns1:userStatus>
               <ns1:ad xsi:type="ns1:TextAd2">
                  <ns1:type>TEXT_AD2</ns1:type>
                  <ns1:advancedUrl>http://yahoo.co.jp/url</ns1:advancedUrl>
                  <ns1:additionalAdvancedUrls>
                     <ns1:advancedUrl>http://yahoo.co.jp/url1</ns1:advancedUrl>
                  </ns1:additionalAdvancedUrls>
                  <ns1:additionalAdvancedUrls>
                     <ns1:advancedUrl>http://yahoo.co.jp/url2</ns1:advancedUrl>
                  </ns1:additionalAdvancedUrls>
                  <ns1:additionalAdvancedUrls>
                     <ns1:advancedUrl>http://yahoo.co.jp/url3</ns1:advancedUrl>
                  </ns1:additionalAdvancedUrls>
                  <ns1:advancedMobileUrl>http://yahoo.co.jp/mobile/url</ns1:advancedMobileUrl>
                  <ns1:additionalAdvancedMobileUrls>
                     <ns1:advancedMobileUrl>http://yahoo.co.jp/mobile/url1</ns1:advancedMobileUrl>
                  </ns1:additionalAdvancedMobileUrls>
                  <ns1:additionalAdvancedMobileUrls>
                     <ns1:advancedMobileUrl>http://yahoo.co.jp/mobile/url2</ns1:advancedMobileUrl>
                  </ns1:additionalAdvancedMobileUrls>
                  <ns1:trackingUrl><![CDATA[http://yahoo.co.jp?url={lpurl}&c={campaignid}&g={adgroupid}&a={creative}&type={site}&pid={id1}&vid={id2}]]></ns1:trackingUrl>
                  <ns1:customParameters>
                     <ns1:isRemove>FALSE</ns1:isRemove>
                     <ns1:parameters>
                        <ns1:key>site</ns1:key>
                        <ns1:value>yahoo</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id1</ns1:key>
                        <ns1:value>1234</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id2</ns1:key>
                        <ns1:value>a7h59A98yu</ns1:value>
                     </ns1:parameters>
                  </ns1:customParameters>
                  <ns1:advanced>TRUE</ns1:advanced>
                  <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                  <ns1:headline>Headline</ns1:headline>
                  <ns1:description>Count down</ns1:description>
                  <ns1:description2>{=COUNTDOWN("2016/01/01 00:00:00","ja")}</ns1:description2>
               </ns1:ad>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [AdGroupAdReturnValue](../data/AdGroupAdReturnValue.md) | Container of ad information including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns1="http://ss.yahooapis.jp/V6"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupAdService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
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
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>Campaign</ns1:campaignName>
                        <ns1:adGroupId>100000001</ns1:adGroupId>
                        <ns1:adGroupTrackId>222222</ns1:adGroupTrackId>
                        <ns1:adGroupName>Text ad group</ns1:adGroupName>
                        <ns1:adId>100000002</ns1:adId>
                        <ns1:adTrackId>333333</ns1:adTrackId>
                        <ns1:adName>Text ad2</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:TextAd2">
                            <ns1:type>TEXT_AD2</ns1:type>
                            <ns1:advancedUrl>http://aaaa.jp</ns1:advancedUrl>
                            <ns1:advancedMobileUrl>http://aaaa.jp/mb</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
                            <ns1:customParameters>
                              <ns1:isRemove>FALSE</ns1:isRemove>
                              <ns1:parameters>
                                <ns1:key>site</ns1:key>
                                <ns1:value>yahoo</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id1</ns1:key>
                                <ns1:value>1234</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id2</ns1:key>
                                <ns1:value>a7h59A98yu</ns1:value>
                              </ns1:parameters>
                            </ns1:customParameters>
                            <ns1:advanced>TRUE</ns1:advanced>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>Headline</ns1:headline>
                            <ns1:description>Count down</ns1:description>
                            <ns1:description2>{=COUNTDOWN("2016/01/01 00:00:00","ja")}</ns1:description2>
                        </ns1:ad>
                        <ns1:feedFolderId>100000001</ns1:feedFolderId>
                    </ns1:adGroupAd>
                </ns1:values>
               <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>Campaign</ns1:campaignName>
                        <ns1:adGroupId>100000003</ns1:adGroupId>
                        <ns1:adGroupTrackId>444444</ns1:adGroupTrackId>
                        <ns1:adGroupName>App ad group</ns1:adGroupName>
                        <ns1:adId>100000004</ns1:adId>
                        <ns1:adTrackId>555555</ns1:adTrackId>
                        <ns1:adName>App ad</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:AppAd">
                            <ns1:type>APP_AD</ns1:type>
                            <ns1:advancedUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedUrl>
                            <ns1:advancedMobileUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
                            <ns1:customParameters>
                              <ns1:isRemove>FALSE</ns1:isRemove>
                              <ns1:parameters>
                                <ns1:key>site</ns1:key>
                                <ns1:value>yahoo</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id1</ns1:key>
                                <ns1:value>1234</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id2</ns1:key>
                                <ns1:value>a7h59A98yu</ns1:value>
                              </ns1:parameters>
                            </ns1:customParameters>
                            <ns1:advanced>TRUE</ns1:advanced>
                            <ns1:headline>App ad headline</ns1:headline>
                            <ns1:description>App ad description1</ns1:description>
                            <ns1:description2>App ad description2</ns1:description2>
                            <ns1:appStore>IOS</ns1:appStore>
                            <ns1:appId>appid1234567890</ns1:appId>
                            <ns1:devicePreference>SMART_PHONE</ns1:devicePreference>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>Campaign</ns1:campaignName>
                        <ns1:adGroupId>100000003</ns1:adGroupId>
                        <ns1:adGroupTrackId>444444</ns1:adGroupTrackId>
                        <ns1:adGroupName>Ad group</ns1:adGroupName>
                        <ns1:adId>100000004</ns1:adId>
                        <ns1:adTrackId>555555</ns1:adTrackId>
                        <ns1:adName>Ad</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:TextAd2">
                            <ns1:type>TEXT_AD2</ns1:type>
                            <ns1:advancedUrl>http://yahoo.co.jp/sample/lpo</ns1:advancedUrl>
                            <ns1:additionalAdvancedUrls>
                               <ns1:advancedUrl>http://yahoo.co.jp/sample/lpo1</ns1:advancedUrl>
                            </ns1:additionalAdvancedUrls>
                            <ns1:additionalAdvancedUrls>
                               <ns1:advancedUrl>http://yahoo.co.jp/sample/lpo2</ns1:advancedUrl>
                            </ns1:additionalAdvancedUrls>
                             <ns1:additionalAdvancedUrls>
                               <ns1:advancedUrl>http://yahoo.co.jp/sample/lpo3</ns1:advancedUrl>
                            </ns1:additionalAdvancedUrls>                          
                            <ns1:advancedMobileUrl>http://yahoo.co.jp/sample/mobile/lpo</ns1:advancedMobileUrl>
                            <ns1:additionalAdvancedMobileUrls>
                               <ns1:advancedMobileUrl>http://yahoo.co.jp/sample/mobile/lpo1</ns1:advancedMobileUrl>
                            </ns1:additionalAdvancedMobileUrls>
                             <ns1:additionalAdvancedMobileUrls>
                               <ns1:advancedMobileUrl>http://yahoo.co.jp/sample/mobile/lpo2</ns1:advancedMobileUrl>
                            </ns1:additionalAdvancedMobileUrls>                          
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
                            <ns1:customParameters>
                              <ns1:isRemove>FALSE</ns1:isRemove>
                              <ns1:parameters>
                                <ns1:key>site</ns1:key>
                                <ns1:value>yahoo</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id1</ns1:key>
                                <ns1:value>1234</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id2</ns1:key>
                                <ns1:value>a7h59A98yu</ns1:value>
                              </ns1:parameters>
                            </ns1:customParameters>
                            <ns1:advanced>TRUE</ns1:advanced>
                            <ns1:headline>Headline</ns1:headline>
                            <ns1:description>Count down</ns1:description>
                            <ns1:description2>{=COUNTDOWN("2016/01/01 00:00:00","ja")}</ns1:description2>
                            <ns1:devicePreference>SMART_PHONE</ns1:devicePreference>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>               
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (SET)
Updates ad information.

### Request

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [AdGroupAdOperation](../data/AdGroupAdOperation.md) | Ad and operation list for the operation. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
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
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:adGroupId>100000001</ns1:adGroupId>
                    <ns1:adId>100000002</ns1:adId>
                    <ns1:adName>Text ad 2 update</ns1:adName>
                    <ns1:userStatus>PAUSED</ns1:userStatus>
                </ns1:operand>
                <ns1:operand>
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:adGroupId>100000002</ns1:adGroupId>
                    <ns1:adId>100000003</ns1:adId>
                    <ns1:adName>Mobile ad update</ns1:adName>
                    <ns1:userStatus>PAUSED</ns1:userStatus>
                </ns1:operand>
                <ns1:operand>
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:adGroupId>100000003</ns1:adGroupId>
                    <ns1:adId>100000003</ns1:adId>
                    <ns1:adName>App ad update</ns1:adName>
                    <ns1:userStatus>PAUSED</ns1:userStatus>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [AdGroupAdReturnValue](../data/AdGroupAdReturnValue.md) | Container of ad information including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns1="http://ss.yahooapis.jp/V6"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupAdService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupAdReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>Campaign</ns1:campaignName>
                        <ns1:adGroupId>100000001</ns1:adGroupId>
                        <ns1:adGroupTrackId>222222</ns1:adGroupTrackId>
                        <ns1:adGroupName>Text ad group</ns1:adGroupName>
                        <ns1:adId>100000002</ns1:adId>
                        <ns1:adTrackId>333333</ns1:adTrackId>
                        <ns1:adName>Text ad update</ns1:adName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:TextAd2">
                            <ns1:type>TEXT_AD2</ns1:type>
                            <ns1:advancedUrl>http://aaaa.jp</ns1:advancedUrl>
                            <ns1:advancedMobileUrl>http://aaaa.jp/mb</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
                            <ns1:customParameters>
                              <ns1:isRemove>FALSE</ns1:isRemove>
                              <ns1:parameters>
                                <ns1:key>site</ns1:key>
                                <ns1:value>yahoo</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id1</ns1:key>
                                <ns1:value>1234</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id2</ns1:key>
                                <ns1:value>a7h59A98yu</ns1:value>
                              </ns1:parameters>
                            </ns1:customParameters>
                            <ns1:advanced>TRUE</ns1:advanced>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>Headline</ns1:headline>
                            <ns1:description>Count down</ns1:description>
                            <ns1:description2>{=COUNTDOWN("2016/01/01 00:00:00","ja")}</ns1:description2>
                        </ns1:ad>
                        <ns1:feedFolderId>100000001</ns1:feedFolderId>
                    </ns1:adGroupAd>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>Campaign</ns1:campaignName>
                        <ns1:adGroupId>100000002</ns1:adGroupId>
                        <ns1:adGroupTrackId>333333</ns1:adGroupTrackId>
                        <ns1:adGroupName>Mobile ad group</ns1:adGroupName>
                        <ns1:adId>100000003</ns1:adId>
                        <ns1:adTrackId>444444</ns1:adTrackId>
                        <ns1:adName>Mobile ad update</ns1:adName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:MobileAd">
                            <ns1:type>MOBILE_AD</ns1:type>
                            <ns1:advanced>FALSE</ns1:advanced>
                            <ns1:url>http://www.yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>Headline</ns1:headline>
                            <ns1:description>Test description</ns1:description>
                            <ns1:markupLanguages>HTML</ns1:markupLanguages>
                            <ns1:markupLanguages>CHTML</ns1:markupLanguages>
                            <ns1:markupLanguages>XHTML</ns1:markupLanguages>
                            <ns1:mobileCarriers>DOCOMO</ns1:mobileCarriers>
                            <ns1:mobileCarriers>KDDI</ns1:mobileCarriers>
                            <ns1:mobileCarriers>SOFTBANK</ns1:mobileCarriers>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>Campaign</ns1:campaignName>
                        <ns1:adGroupId>100000003</ns1:adGroupId>
                        <ns1:adGroupTrackId>444444</ns1:adGroupTrackId>
                        <ns1:adGroupName>App ad group</ns1:adGroupName>
                        <ns1:adId>1000000004</ns1:adId>
                        <ns1:adTrackId>555555</ns1:adTrackId>
                        <ns1:adName>App ad update</ns1:adName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:AppAd">
                            <ns1:type>APP_AD</ns1:type>
                            <ns1:advancedUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedUrl>
                            <ns1:advancedMobileUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
                            <ns1:customParameters>
                              <ns1:isRemove>FALSE</ns1:isRemove>
                              <ns1:parameters>
                                <ns1:key>site</ns1:key>
                                <ns1:value>yahoo</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id1</ns1:key>
                                <ns1:value>1234</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id2</ns1:key>
                                <ns1:value>a7h59A98yu</ns1:value>
                              </ns1:parameters>
                            </ns1:customParameters>
                            <ns1:advanced>TRUE</ns1:advanced>
                            <ns1:headline>App ad headline</ns1:headline>
                            <ns1:description>App ad description1</ns1:description>
                            <ns1:description2>App ad description2</ns1:description2>
                            <ns1:appStore>IOS</ns1:appStore>
                            <ns1:appId>appid1234567890</ns1:appId>
                            <ns1:devicePreference>SMART_PHONE</ns1:devicePreference>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (REMOVE)
Remove ad information.

### Request

| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [AdGroupAdOperation](../data/AdGroupAdOperation.md) | Ad and operation list of the operation. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:adGroupId>100000001</ns1:adGroupId>
                    <ns1:adId>100000002</ns1:adId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:adGroupId>100000002</ns1:adGroupId>
                    <ns1:adId>100000003</ns1:adId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:adGroupId>100000003</ns1:adGroupId>
                    <ns1:adId>100000004</ns1:adId>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [AdGroupAdReturnValue](../data/AdGroupAdReturnValue.md) | Container of ad information including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupAdService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupAdReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>Campaign</ns1:campaignName>
                        <ns1:adGroupId>100000001</ns1:adGroupId>
                        <ns1:adGroupTrackId>222222</ns1:adGroupTrackId>
                        <ns1:adGroupName>Text ad group</ns1:adGroupName>
                        <ns1:adId>100000002</ns1:adId>
                        <ns1:adTrackId>333333</ns1:adTrackId>
                        <ns1:adName>Text ad 2 update</ns1:adName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:TextAd2">
                            <ns1:type>TEXT_AD2</ns1:type>
                            <ns1:advancedUrl>http://aaaa.jp</ns1:advancedUrl>
                            <ns1:advancedMobileUrl>http://aaaa.jp/mb</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
                            <ns1:customParameters>
                              <ns1:isRemove>FALSE</ns1:isRemove>
                              <ns1:parameters>
                                <ns1:key>site</ns1:key>
                                <ns1:value>yahoo</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id1</ns1:key>
                                <ns1:value>1234</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id2</ns1:key>
                                <ns1:value>a7h59A98yu</ns1:value>
                              </ns1:parameters>
                            </ns1:customParameters>
                            <ns1:advanced>TRUE</ns1:advanced>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>Headline</ns1:headline>
                            <ns1:description>Count down</ns1:description>
                            <ns1:description2>{=COUNTDOWN("2016/01/01 00:00:00","ja")}</ns1:description2>
                        </ns1:ad>
                        <ns1:feedFolderId>100000001</ns1:feedFolderId>
                    </ns1:adGroupAd>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>Campaign</ns1:campaignName>
                        <ns1:adGroupId>100000002</ns1:adGroupId>
                        <ns1:adGroupTrackId>333333</ns1:adGroupTrackId>
                        <ns1:adGroupName>Mobile ad group</ns1:adGroupName>
                        <ns1:adId>100000003</ns1:adId>
                        <ns1:adTrackId>444444</ns1:adTrackId>
                        <ns1:adName>Mobile ad update</ns1:adName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:MobileAd">
                            <ns1:type>MOBILE_AD</ns1:type>
                            <ns1:advanced>FALSE</ns1:advanced>
                            <ns1:url>http://www.yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>Healine test</ns1:headline>
                            <ns1:description>Test description</ns1:description>
                            <ns1:markupLanguages>HTML</ns1:markupLanguages>
                            <ns1:markupLanguages>CHTML</ns1:markupLanguages>
                            <ns1:markupLanguages>XHTML</ns1:markupLanguages>
                            <ns1:mobileCarriers>DOCOMO</ns1:mobileCarriers>
                            <ns1:mobileCarriers>KDDI</ns1:mobileCarriers>
                            <ns1:mobileCarriers>SOFTBANK</ns1:mobileCarriers>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>Campaign</ns1:campaignName>
                        <ns1:adGroupId>100000003</ns1:adGroupId>
                        <ns1:adGroupTrackId>444444</ns1:adGroupTrackId>
                        <ns1:adGroupName>App ad group</ns1:adGroupName>
                        <ns1:adId>1000000004</ns1:adId>
                        <ns1:adTrackId>555555</ns1:adTrackId>
                        <ns1:adName>App ad update</ns1:adName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:AppAd">
                            <ns1:type>APP_AD</ns1:type>
                            <ns1:advancedUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedUrl>
                            <ns1:advancedMobileUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
                            <ns1:customParameters>
                              <ns1:isRemove>FALSE</ns1:isRemove>
                              <ns1:parameters>
                                <ns1:key>site</ns1:key>
                                <ns1:value>yahoo</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id1</ns1:key>
                                <ns1:value>1234</ns1:value>
                              </ns1:parameters>
                              <ns1:parameters>
                                <ns1:key>id2</ns1:key>
                                <ns1:value>a7h59A98yu</ns1:value>
                              </ns1:parameters>
                            </ns1:customParameters>
                            <ns1:advanced>TRUE</ns1:advanced>
                            <ns1:headline>App ad headline</ns1:headline>
                            <ns1:description>App ad description1</ns1:description>
                            <ns1:description2>App ad description2</ns1:description2>
                            <ns1:appStore>IOS</ns1:appStore>
                            <ns1:appId>appid1234567890</ns1:appId>
                            <ns1:devicePreference>SMART_PHONE</ns1:devicePreference>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
