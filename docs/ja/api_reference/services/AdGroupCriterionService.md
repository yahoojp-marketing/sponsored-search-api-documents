# AdGroupCriterionService
AdGroupCriterionServiceでは、広告グループに関するターゲット条件（クライテリア）の取得および追加・更新・削除を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201901/AdGroupCriterionService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201901/AdGroupCriterionService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201901/AdGroupCriterion

#### サービス概要
広告グループに関するターゲット条件（クライテリア）の取得および追加・更新・削除を行います。

#### 操作
AdGroupCriterionServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

#### オブジェクト
[AdGroupCriterion](../data/AdGroupCriterion)

## get
広告グループに関するクライテリアを取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [AdGroupCriterionSelector](../data/AdGroupCriterion/AdGroupCriterionSelector.md) | 操作の対象とする広告グループのクライテリアです。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201901">
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
        <labelIds>40001</labelIds>
        <labelIds>40002</labelIds>
        <labelIds>40003</labelIds>
        <labelIds>40004</labelIds>
        <labelIds>40005</labelIds>
        <containsLabelId>TRUE</containsLabelId>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>100</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [AdGroupCriterionPage](../data/AdGroupCriterion/AdGroupCriterionPage.md) | 取得される広告グループのクライテリアのエントリーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>AdGroupCriterion</ns2:service>
      <ns2:requestTime>1547793434258</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/AdGroupCriterion">
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
            <ns2:labels>
              <ns2:labelId>40001</ns2:labelId>
              <ns2:labelName>sample label 1</ns2:labelName>
              <ns2:description>sample description 1</ns2:description>
              <ns2:color>#FFFFFF</ns2:color>
            </ns2:labels>
            <ns2:labels>
              <ns2:labelId>40002</ns2:labelId>
              <ns2:labelName>sample label 2</ns2:labelName>
              <ns2:description>sample description 2</ns2:description>
              <ns2:color>#000000</ns2:color>
            </ns2:labels>
            <ns2:labels>
              <ns2:labelId>40003</ns2:labelId>
              <ns2:labelName>sample label 3</ns2:labelName>
              <ns2:description>sample description 3</ns2:description>
              <ns2:color>#FF0000</ns2:color>
            </ns2:labels>
            <ns2:labels>
              <ns2:labelId>40004</ns2:labelId>
              <ns2:labelName>sample label 4</ns2:labelName>
              <ns2:description>sample description 4</ns2:description>
              <ns2:color>#00FF00</ns2:color>
            </ns2:labels>
            <ns2:labels>
              <ns2:labelId>40005</ns2:labelId>
              <ns2:labelName>sample label 5</ns2:labelName>
              <ns2:description>sample description 5</ns2:description>
              <ns2:color>#0000FF</ns2:color>
            </ns2:labels>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:bid>
              <ns2:maxCpc>100</ns2:maxCpc>
              <ns2:bidSource>CRITERION</ns2:bidSource>
              <ns2:adGroupMaxCpc>1</ns2:adGroupMaxCpc>
              <ns2:keywordMaxCpc>100</ns2:keywordMaxCpc>
            </ns2:bid>
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

## mutate(ADD)
広告グループに関するクライテリアを追加します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [AdGroupCriterionOperation](../data/AdGroupCriterion/AdGroupCriterionOperation.md) | 操作の対象となる広告グループのクライテリアと処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterion">
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
          <bid>
            <maxCpc>100</maxCpc>
          </bid>
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

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [AdGroupCriterionReturnValue](../data/AdGroupCriterion/AdGroupCriterionReturnValue.md) | 操作結果を含む広告グループのクライテリアに関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>AdGroupCriterion</ns2:service>
      <ns2:requestTime>1547793434297</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/AdGroupCriterion">
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
            <ns2:bid>
              <ns2:maxCpc>100</ns2:maxCpc>
              <ns2:bidSource>CRITERION</ns2:bidSource>
              <ns2:adGroupMaxCpc>1</ns2:adGroupMaxCpc>
              <ns2:keywordMaxCpc>100</ns2:keywordMaxCpc>
            </ns2:bid>
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

## mutate(SET)
広告グループに関するクライテリアを更新します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [AdGroupCriterionOperation](../data/AdGroupCriterion/AdGroupCriterionOperation.md) | 操作の対象となる広告グループのクライテリアと処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterion">
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
          <bid>
            <maxCpc>200</maxCpc>
          </bid>
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

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [AdGroupCriterionReturnValue](../data/AdGroupCriterion/AdGroupCriterionReturnValue.md) | 操作結果を含む広告グループのクライテリアに関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>AdGroupCriterion</ns2:service>
      <ns2:requestTime>1547793434339</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/AdGroupCriterion">
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
            <ns2:bid>
              <ns2:maxCpc>50</ns2:maxCpc>
              <ns2:bidSource>CRITERION</ns2:bidSource>
              <ns2:adGroupMaxCpc>1</ns2:adGroupMaxCpc>
              <ns2:keywordMaxCpc>50</ns2:keywordMaxCpc>
            </ns2:bid>
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

## mutate(REMOVE)
広告グループに関するクライテリアを削除します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [AdGroupCriterionOperation](../data/AdGroupCriterion/AdGroupCriterionOperation.md) | 操作の対象となる広告グループのクライテリアと処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterion">
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

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [AdGroupCriterionReturnValue](../data/AdGroupCriterion/AdGroupCriterionReturnValue.md) | 操作結果を含む広告グループのクライテリアに関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>AdGroupCriterion</ns2:service>
      <ns2:requestTime>1547793434396</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/AdGroupCriterion">
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
            <ns2:bid>
              <ns2:maxCpc>100</ns2:maxCpc>
              <ns2:bidSource>CRITERION</ns2:bidSource>
              <ns2:adGroupMaxCpc>1</ns2:adGroupMaxCpc>
              <ns2:keywordMaxCpc>100</ns2:keywordMaxCpc>
            </ns2:bid>
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
