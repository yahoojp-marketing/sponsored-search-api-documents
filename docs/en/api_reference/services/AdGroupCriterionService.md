# AdGroupCriterionService
Use this service to get, add, update, or remove targeting conditions (criteria) of ad group.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201808/AdGroupCriterionService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201808/AdGroupCriterionService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201808/AdGroupCriterion

#### Overview
Use this service to get, add, update, or remove targeting conditions (criteria) of ad group.

#### Operation
Explains the operation which provides at AdGroupCriterionService.
+ [get](#get)
+ [mutate(ADD)](#mutate-add)
+ [mutate(SET)](#mutate-set)
+ [mutate(REMOVE)](#mutate-remove)

#### Object
[AdGroupCriterion](../data/AdGroupCriterion)

## get
Get criteria of Ad group.

### Request
| Field | Restrictions | Data Type | Description |
|---|---|---|---|
| selector | Req | [AdGroupCriterionSelector](../data/AdGroupCriterion/AdGroupCriterionSelector.md) | Selector the adgroup criteria for operation. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201808/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <selector>
        <accountId>1234567890</accountId>
        <campaignIds>10001</campaignIds>
        <campaignIds>10002</campaignIds>
        <campaignIds>10003</campaignIds>
        <campaignIds>10004</campaignIds>
        <campaignIds>10005</campaignIds>
        <adGroupIds>20001</adGroupIds>
        <adGroupIds>20002</adGroupIds>
        <adGroupIds>20003</adGroupIds>
        <adGroupIds>20004</adGroupIds>
        <adGroupIds>20005</adGroupIds>
        <criterionIds>30001</criterionIds>
        <criterionIds>30002</criterionIds>
        <criterionIds>30003</criterionIds>
        <criterionIds>30004</criterionIds>
        <criterionIds>30005</criterionIds>
        <criterionUse>BIDDABLE</criterionUse>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>100</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [AdGroupCriterionPage](../data/AdGroupCriterion/AdGroupCriterionPage.md) | Entry of ad group criteria to get. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>AdGroupCriterion</ns2:service>
      <ns2:requestTime>1523506329448</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/AdGroupCriterion">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>AdGroupCriterionPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupCriterion xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:BiddableAdGroupCriterion">
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10002</ns2:campaignId>
            <ns2:campaignTrackId>100000002</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>20002</ns2:adGroupId>
            <ns2:adGroupTrackId>200000002</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adgroup.</ns2:adGroupName>
            <ns2:criterionUse>BIDDABLE</ns2:criterionUse>
            <ns2:criterion xsi:type="ns2:Keyword">
              <ns2:criterionId>30002</ns2:criterionId>
              <ns2:criterionTrackId>0</ns2:criterionTrackId>
              <ns2:type>KEYWORD</ns2:type>
              <ns2:text>test keyword2.</ns2:text>
              <ns2:matchType>PHRASE</ns2:matchType>
            </ns2:criterion>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:biddingStrategyConfiguration>
              <ns2:biddingStrategyType>MANUAL_CPC</ns2:biddingStrategyType>
              <ns2:biddingStrategySource>CAMPAIGN</ns2:biddingStrategySource>
              <ns2:biddingScheme xsi:type="ns2:ManualCpcBiddingScheme">
                <ns2:biddingStrategyType>MANUAL_CPC</ns2:biddingStrategyType>
              </ns2:biddingScheme>
              <ns2:bid>
                <ns2:maxCpc>100</ns2:maxCpc>
                <ns2:bidSource>CRITERION</ns2:bidSource>
                <ns2:adGroupMaxCpc>1</ns2:adGroupMaxCpc>
                <ns2:keywordMaxCpc>100</ns2:keywordMaxCpc>
              </ns2:bid>
            </ns2:biddingStrategyConfiguration>
            <ns2:advancedUrl>http://yahoo.co.jp</ns2:advancedUrl>
            <ns2:additionalAdvancedUrls>
              <ns2:additionalAdvancedUrl>
                <ns2:url>http://yahoo.co.jp/url1</ns2:url>
              </ns2:additionalAdvancedUrl>
              <ns2:additionalAdvancedUrl>
                <ns2:url>http://yahoo.co.jp/url2</ns2:url>
              </ns2:additionalAdvancedUrl>
              <ns2:additionalAdvancedUrl>
                <ns2:url>http://yahoo.co.jp/url3</ns2:url>
              </ns2:additionalAdvancedUrl>
            </ns2:additionalAdvancedUrls>
            <ns2:advancedMobileUrl>http://mobile.yahoo.co.jp</ns2:advancedMobileUrl>
            <ns2:additionalAdvancedMobileUrls>
              <ns2:additionalAdvancedMobileUrl>
                <ns2:url>http://mobile.yahoo.co.jp/url1</ns2:url>
              </ns2:additionalAdvancedMobileUrl>
              <ns2:additionalAdvancedMobileUrl>
                <ns2:url>http://mobile.yahoo.co.jp/url2</ns2:url>
              </ns2:additionalAdvancedMobileUrl>
              <ns2:additionalAdvancedMobileUrl>
                <ns2:url>http://mobile.yahoo.co.jp/url3</ns2:url>
              </ns2:additionalAdvancedMobileUrl>
            </ns2:additionalAdvancedMobileUrls>
            <ns2:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:trackingUrl>
            <ns2:customParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:customParameters>
          </ns2:adGroupCriterion>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (ADD)
Add Ad group criteria.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [AdGroupCriterionOperation](../data/AdGroupCriterion/AdGroupCriterionOperation.md) | Criteria of ad group for operation and process details.|

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201808/AdGroupCriterion">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="NegativeAdGroupCriterion">
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <criterionUse>NEGATIVE</criterionUse>
          <criterion xsi:type="Keyword">
            <type>KEYWORD</type>
            <text>test keyword.</text>
            <matchType>PHRASE</matchType>
          </criterion>
        </operand>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="BiddableAdGroupCriterion">
          <campaignId>10002</campaignId>
          <adGroupId>20002</adGroupId>
          <criterionUse>BIDDABLE</criterionUse>
          <criterion xsi:type="Keyword">
            <type>KEYWORD</type>
            <text>test keyword2.</text>
            <matchType>PHRASE</matchType>
          </criterion>
          <userStatus>ACTIVE</userStatus>
          <biddingStrategyConfiguration>
            <bid>
              <maxCpc>100</maxCpc>
            </bid>
          </biddingStrategyConfiguration>
          <advancedUrl>http://yahoo.co.jp</advancedUrl>
          <additionalAdvancedUrls>
            <additionalAdvancedUrl>
              <url>http://yahoo.co.jp/url1</url>
            </additionalAdvancedUrl>
            <additionalAdvancedUrl>
              <url>http://yahoo.co.jp/url2</url>
            </additionalAdvancedUrl>
            <additionalAdvancedUrl>
              <url>http://yahoo.co.jp/url3</url>
            </additionalAdvancedUrl>
          </additionalAdvancedUrls>
          <advancedMobileUrl>http://mobile.yahoo.co.jp</advancedMobileUrl>
          <additionalAdvancedMobileUrls>
            <additionalAdvancedMobileUrl>
              <url>http://mobile.yahoo.co.jp/url1</url>
            </additionalAdvancedMobileUrl>
            <additionalAdvancedMobileUrl>
              <url>http://mobile.yahoo.co.jp/url2</url>
            </additionalAdvancedMobileUrl>
            <additionalAdvancedMobileUrl>
              <url>http://mobile.yahoo.co.jp/url3</url>
            </additionalAdvancedMobileUrl>
          </additionalAdvancedMobileUrls>
          <trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</trackingUrl>
          <customParameters>
            <parameters>
              <key>site</key>
              <value>yahoo</value>
            </parameters>
            <parameters>
              <key>id1</key>
              <value>1234</value>
            </parameters>
            <parameters>
              <key>id2</key>
              <value>a7h59A98yu</value>
            </parameters>
          </customParameters>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [AdGroupCriterionReturnValue](../data/AdGroupCriterion/AdGroupCriterionReturnValue.md) | Container of ad group criteria information including operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>AdGroupCriterion</ns2:service>
      <ns2:requestTime>1523506329502</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/AdGroupCriterion">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupCriterionReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupCriterion xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:NegativeAdGroupCriterion">
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignTrackId>100000001</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:adGroupTrackId>200000001</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adgroup.</ns2:adGroupName>
            <ns2:criterionUse>NEGATIVE</ns2:criterionUse>
            <ns2:criterion xsi:type="ns2:Keyword">
              <ns2:criterionId>30001</ns2:criterionId>
              <ns2:criterionTrackId>0</ns2:criterionTrackId>
              <ns2:type>KEYWORD</ns2:type>
              <ns2:text>test keyword.</ns2:text>
              <ns2:matchType>PHRASE</ns2:matchType>
            </ns2:criterion>
          </ns2:adGroupCriterion>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupCriterion xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:BiddableAdGroupCriterion">
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10002</ns2:campaignId>
            <ns2:campaignTrackId>100000002</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>20002</ns2:adGroupId>
            <ns2:adGroupTrackId>200000002</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adgroup.</ns2:adGroupName>
            <ns2:criterionUse>BIDDABLE</ns2:criterionUse>
            <ns2:criterion xsi:type="ns2:Keyword">
              <ns2:criterionId>30002</ns2:criterionId>
              <ns2:criterionTrackId>0</ns2:criterionTrackId>
              <ns2:type>KEYWORD</ns2:type>
              <ns2:text>test keyword2.</ns2:text>
              <ns2:matchType>PHRASE</ns2:matchType>
            </ns2:criterion>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:biddingStrategyConfiguration>
              <ns2:biddingStrategyType>MANUAL_CPC</ns2:biddingStrategyType>
              <ns2:biddingStrategySource>CAMPAIGN</ns2:biddingStrategySource>
              <ns2:biddingScheme xsi:type="ns2:ManualCpcBiddingScheme">
                <ns2:biddingStrategyType>MANUAL_CPC</ns2:biddingStrategyType>
              </ns2:biddingScheme>
              <ns2:bid>
                <ns2:maxCpc>100</ns2:maxCpc>
                <ns2:bidSource>CRITERION</ns2:bidSource>
                <ns2:adGroupMaxCpc>1</ns2:adGroupMaxCpc>
                <ns2:keywordMaxCpc>100</ns2:keywordMaxCpc>
              </ns2:bid>
            </ns2:biddingStrategyConfiguration>
            <ns2:reviewAdvancedUrl>http://yahoo.co.jp</ns2:reviewAdvancedUrl>
            <ns2:additionalAdvancedUrls>
              <ns2:additionalAdvancedUrl>
                <ns2:url>http://yahoo.co.jp/url1</ns2:url>
              </ns2:additionalAdvancedUrl>
              <ns2:additionalAdvancedUrl>
                <ns2:url>http://yahoo.co.jp/url2</ns2:url>
              </ns2:additionalAdvancedUrl>
              <ns2:additionalAdvancedUrl>
                <ns2:url>http://yahoo.co.jp/url3</ns2:url>
              </ns2:additionalAdvancedUrl>
            </ns2:additionalAdvancedUrls>
            <ns2:reviewAdvancedMobileUrl>http://mobile.yahoo.co.jp</ns2:reviewAdvancedMobileUrl>
            <ns2:additionalAdvancedMobileUrls>
              <ns2:additionalAdvancedMobileUrl>
                <ns2:url>http://mobile.yahoo.co.jp/url1</ns2:url>
              </ns2:additionalAdvancedMobileUrl>
              <ns2:additionalAdvancedMobileUrl>
                <ns2:url>http://mobile.yahoo.co.jp/url2</ns2:url>
              </ns2:additionalAdvancedMobileUrl>
              <ns2:additionalAdvancedMobileUrl>
                <ns2:url>http://mobile.yahoo.co.jp/url3</ns2:url>
              </ns2:additionalAdvancedMobileUrl>
            </ns2:additionalAdvancedMobileUrls>
            <ns2:reviewTrackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:reviewTrackingUrl>
            <ns2:reviewCustomParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:reviewCustomParameters>
          </ns2:adGroupCriterion>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (SET)
Update or change Ad group criteria.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [AdGroupCriterionOperation](../data/AdGroupCriterion/AdGroupCriterionOperation.md) | Criteria of ad group for operation and process details. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201808/AdGroupCriterion">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="BiddableAdGroupCriterion">
          <campaignId>10002</campaignId>
          <adGroupId>20002</adGroupId>
          <criterionUse>BIDDABLE</criterionUse>
          <criterion xsi:type="Keyword">
            <criterionId>30002</criterionId>
            <type>KEYWORD</type>
          </criterion>
          <userStatus>ACTIVE</userStatus>
          <biddingStrategyConfiguration>
            <bid>
              <maxCpc>200</maxCpc>
            </bid>
          </biddingStrategyConfiguration>
          <advancedUrl>http://www.yahoo.co.jp</advancedUrl>
          <additionalAdvancedUrls>
            <additionalAdvancedUrl>
              <url>http://www.yahoo.co.jp/url1</url>
            </additionalAdvancedUrl>
            <additionalAdvancedUrl>
              <url>http://www.yahoo.co.jp/url2</url>
            </additionalAdvancedUrl>
            <additionalAdvancedUrl>
              <url>http://www.yahoo.co.jp/url3</url>
            </additionalAdvancedUrl>
          </additionalAdvancedUrls>
          <advancedMobileUrl>http://portal.mobile.yahoo.co.jp</advancedMobileUrl>
          <additionalAdvancedMobileUrls>
            <additionalAdvancedMobileUrl>
              <url>http://portal.mobile.yahoo.co.jp/url1</url>
            </additionalAdvancedMobileUrl>
            <additionalAdvancedMobileUrl>
              <url>http://portal.mobile.yahoo.co.jp/url2</url>
            </additionalAdvancedMobileUrl>
            <additionalAdvancedMobileUrl>
              <url>http://portal.mobile.yahoo.co.jp/url3</url>
            </additionalAdvancedMobileUrl>
          </additionalAdvancedMobileUrls>
          <trackingUrl>http://www.yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id3}&amp;vid={_id4}</trackingUrl>
          <customParameters>
            <parameters>
              <key>id3</key>
              <value>5678</value>
            </parameters>
            <parameters>
              <key>id4</key>
              <value>bve46t67</value>
            </parameters>
          </customParameters>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [AdGroupCriterionReturnValue](../data/AdGroupCriterion/AdGroupCriterionReturnValue.md) | Container of ad group criteria information including operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>AdGroupCriterion</ns2:service>
      <ns2:requestTime>1523506329550</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/AdGroupCriterion">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupCriterionReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupCriterion xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:BiddableAdGroupCriterion">
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10002</ns2:campaignId>
            <ns2:campaignTrackId>100000002</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>20002</ns2:adGroupId>
            <ns2:adGroupTrackId>200000002</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adgroup.</ns2:adGroupName>
            <ns2:criterionUse>BIDDABLE</ns2:criterionUse>
            <ns2:criterion xsi:type="ns2:Keyword">
              <ns2:criterionId>30002</ns2:criterionId>
              <ns2:criterionTrackId>300000002</ns2:criterionTrackId>
              <ns2:type>KEYWORD</ns2:type>
              <ns2:text>test keyword2.</ns2:text>
              <ns2:matchType>PHRASE</ns2:matchType>
            </ns2:criterion>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:biddingStrategyConfiguration>
              <ns2:biddingStrategyType>MANUAL_CPC</ns2:biddingStrategyType>
              <ns2:biddingStrategySource>CAMPAIGN</ns2:biddingStrategySource>
              <ns2:biddingScheme xsi:type="ns2:ManualCpcBiddingScheme">
                <ns2:biddingStrategyType>MANUAL_CPC</ns2:biddingStrategyType>
              </ns2:biddingScheme>
              <ns2:bid>
                <ns2:maxCpc>50</ns2:maxCpc>
                <ns2:bidSource>CRITERION</ns2:bidSource>
                <ns2:adGroupMaxCpc>1</ns2:adGroupMaxCpc>
                <ns2:keywordMaxCpc>50</ns2:keywordMaxCpc>
              </ns2:bid>
            </ns2:biddingStrategyConfiguration>
            <ns2:advancedUrl>http://yahoo.co.jp</ns2:advancedUrl>
            <ns2:reviewAdvancedUrl>http://www.yahoo.co.jp</ns2:reviewAdvancedUrl>
            <ns2:additionalAdvancedUrls>
              <ns2:additionalAdvancedUrl>
                <ns2:url>http://yahoo.co.jp/url1</ns2:url>
                <ns2:reviewUrl>http://www.yahoo.co.jp/url1</ns2:reviewUrl>
              </ns2:additionalAdvancedUrl>
              <ns2:additionalAdvancedUrl>
                <ns2:url>http://yahoo.co.jp/url2</ns2:url>
                <ns2:reviewUrl>http://www.yahoo.co.jp/url2</ns2:reviewUrl>
              </ns2:additionalAdvancedUrl>
              <ns2:additionalAdvancedUrl>
                <ns2:url>http://yahoo.co.jp/url3</ns2:url>
                <ns2:reviewUrl>http://www.yahoo.co.jp/url3</ns2:reviewUrl>
              </ns2:additionalAdvancedUrl>
            </ns2:additionalAdvancedUrls>
            <ns2:advancedMobileUrl>http://mobile.yahoo.co.jp</ns2:advancedMobileUrl>
            <ns2:reviewAdvancedMobileUrl>http://portal.mobile.yahoo.co.jp</ns2:reviewAdvancedMobileUrl>
            <ns2:additionalAdvancedMobileUrls>
              <ns2:additionalAdvancedMobileUrl>
                <ns2:url>http://mobile.yahoo.co.jp/url1</ns2:url>
                <ns2:reviewUrl>http://portal.mobile.yahoo.co.jp/url1</ns2:reviewUrl>
              </ns2:additionalAdvancedMobileUrl>
              <ns2:additionalAdvancedMobileUrl>
                <ns2:url>http://mobile.yahoo.co.jp/url2</ns2:url>
                <ns2:reviewUrl>http://portal.mobile.yahoo.co.jp/url2</ns2:reviewUrl>
              </ns2:additionalAdvancedMobileUrl>
              <ns2:additionalAdvancedMobileUrl>
                <ns2:url>http://mobile.yahoo.co.jp/url3</ns2:url>
                <ns2:reviewUrl>http://portal.mobile.yahoo.co.jp/url3</ns2:reviewUrl>
              </ns2:additionalAdvancedMobileUrl>
            </ns2:additionalAdvancedMobileUrls>
            <ns2:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:trackingUrl>
            <ns2:reviewTrackingUrl>http://www.yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id3}&amp;vid={_id4}</ns2:reviewTrackingUrl>
            <ns2:customParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:customParameters>
            <ns2:reviewCustomParameters>
              <ns2:parameters>
                <ns2:key>id3</ns2:key>
                <ns2:value>5678</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id4</ns2:key>
                <ns2:value>bve46t67</ns2:value>
              </ns2:parameters>
            </ns2:reviewCustomParameters>
          </ns2:adGroupCriterion>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (REMOVE)
Removes Ad group criteria.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [AdGroupCriterionOperation](../data/AdGroupCriterion/AdGroupCriterionOperation.md) | Criteria of ad group for operation and process details. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201808/AdGroupCriterion">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="NegativeAdGroupCriterion">
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <criterionUse>NEGATIVE</criterionUse>
          <criterion xsi:type="Keyword">
            <criterionId>30001</criterionId>
            <type>KEYWORD</type>
          </criterion>
        </operand>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="BiddableAdGroupCriterion">
          <campaignId>10002</campaignId>
          <adGroupId>20002</adGroupId>
          <criterionUse>BIDDABLE</criterionUse>
          <criterion xsi:type="Keyword">
            <criterionId>30002</criterionId>
            <type>KEYWORD</type>
          </criterion>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [AdGroupCriterionReturnValue](../data/AdGroupCriterion/AdGroupCriterionReturnValue.md) | Ad group criteria (without optional parts). |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>AdGroupCriterion</ns2:service>
      <ns2:requestTime>1523506329599</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/AdGroupCriterion">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupCriterionReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupCriterion xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:NegativeAdGroupCriterion">
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignTrackId>100000001</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:adGroupTrackId>200000001</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adgroup.</ns2:adGroupName>
            <ns2:criterionUse>NEGATIVE</ns2:criterionUse>
            <ns2:criterion xsi:type="ns2:Keyword">
              <ns2:criterionId>30001</ns2:criterionId>
              <ns2:criterionTrackId>0</ns2:criterionTrackId>
              <ns2:type>KEYWORD</ns2:type>
              <ns2:text>test keyword.</ns2:text>
              <ns2:matchType>PHRASE</ns2:matchType>
            </ns2:criterion>
          </ns2:adGroupCriterion>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupCriterion xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:BiddableAdGroupCriterion">
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10002</ns2:campaignId>
            <ns2:campaignTrackId>100000002</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>20002</ns2:adGroupId>
            <ns2:adGroupTrackId>200000002</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adgroup.</ns2:adGroupName>
            <ns2:criterionUse>BIDDABLE</ns2:criterionUse>
            <ns2:criterion xsi:type="ns2:Keyword">
              <ns2:criterionId>30002</ns2:criterionId>
              <ns2:criterionTrackId>0</ns2:criterionTrackId>
              <ns2:type>KEYWORD</ns2:type>
              <ns2:text>test keyword2.</ns2:text>
              <ns2:matchType>PHRASE</ns2:matchType>
            </ns2:criterion>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:biddingStrategyConfiguration>
              <ns2:biddingStrategyType>MANUAL_CPC</ns2:biddingStrategyType>
              <ns2:biddingStrategySource>CAMPAIGN</ns2:biddingStrategySource>
              <ns2:biddingScheme xsi:type="ns2:ManualCpcBiddingScheme">
                <ns2:biddingStrategyType>MANUAL_CPC</ns2:biddingStrategyType>
              </ns2:biddingScheme>
              <ns2:bid>
                <ns2:maxCpc>100</ns2:maxCpc>
                <ns2:bidSource>CRITERION</ns2:bidSource>
                <ns2:adGroupMaxCpc>1</ns2:adGroupMaxCpc>
                <ns2:keywordMaxCpc>100</ns2:keywordMaxCpc>
              </ns2:bid>
            </ns2:biddingStrategyConfiguration>
            <ns2:advancedUrl>http://yahoo.co.jp</ns2:advancedUrl>
            <ns2:additionalAdvancedUrls>
              <ns2:additionalAdvancedUrl>
                <ns2:url>http://yahoo.co.jp/url1</ns2:url>
              </ns2:additionalAdvancedUrl>
              <ns2:additionalAdvancedUrl>
                <ns2:url>http://yahoo.co.jp/url2</ns2:url>
              </ns2:additionalAdvancedUrl>
              <ns2:additionalAdvancedUrl>
                <ns2:url>http://yahoo.co.jp/url3</ns2:url>
              </ns2:additionalAdvancedUrl>
            </ns2:additionalAdvancedUrls>
            <ns2:advancedMobileUrl>http://mobile.yahoo.co.jp</ns2:advancedMobileUrl>
            <ns2:additionalAdvancedMobileUrls>
              <ns2:additionalAdvancedMobileUrl>
                <ns2:url>http://mobile.yahoo.co.jp/url1</ns2:url>
              </ns2:additionalAdvancedMobileUrl>
              <ns2:additionalAdvancedMobileUrl>
                <ns2:url>http://mobile.yahoo.co.jp/url2</ns2:url>
              </ns2:additionalAdvancedMobileUrl>
              <ns2:additionalAdvancedMobileUrl>
                <ns2:url>http://mobile.yahoo.co.jp/url3</ns2:url>
              </ns2:additionalAdvancedMobileUrl>
            </ns2:additionalAdvancedMobileUrls>
            <ns2:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:trackingUrl>
            <ns2:customParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:customParameters>
          </ns2:adGroupCriterion>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
