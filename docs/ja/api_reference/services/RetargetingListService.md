# RetargetingListService
RetargetingListServiceでは、ターゲットリストに関する情報の取得および追加・更新を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/RetargetingListService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/RetargetingListService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### サービス概要
ターゲットリストに関する情報の取得および追加・更新を行います。

#### 操作
RetargetingListServiceで提供される操作を説明します。

## get
ターゲットリストに関する情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [RetargetingListSelector](../data/RetargetingListSelector.md) | 操作の対象とするターゲットリストです。 | 

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
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
        <ns1:targetListIds>100000002</ns1:targetListIds>
        <ns1:targetListIds>100000003</ns1:targetListIds>
        <ns1:targetListIds>100000004</ns1:targetListIds>
        <ns1:targetListTypes>DEFAULT</ns1:targetListTypes>
        <ns1:targetListTypes>RULE</ns1:targetListTypes>
        <ns1:targetListTypes>LOGICAL</ns1:targetListTypes>
        <ns1:paging>
          <ns1:startIndex>1</ns1:startIndex>
          <ns1:numberResults>20</ns1:numberResults>
        </ns1:paging>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [RetargetingListPage](../data/RetargetingListPage.md) | 取得されるターゲットリストのエントリーです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>RetargetingListService</ns1:service>
      <ns1:remainingQuota>-1</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.2315</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>3</ns1:totalNumEntries>
        <ns1:Page.Type>RetargetingListPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:targetList xsi:type="ns1:DefaultTargetList">
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:retargetingAccountStatus>
              <ns1:agreeDate>20150612</ns1:agreeDate>
              <ns1:reviewStatus>APPROVED</ns1:reviewStatus>
            </ns1:retargetingAccountStatus>
            <ns1:targetListId>100000002</ns1:targetListId>
            <ns1:targetListType>DEFAULT</ns1:targetListType>
            <ns1:targetListName>デフォルトリスト</ns1:targetListName>
            <ns1:targetListDescription>デフォルトターゲットリスト</ns1:targetListDescription>
            <ns1:reachStorageStatus>OPEN</ns1:reachStorageStatus>
            <ns1:reachStorageSpan>180</ns1:reachStorageSpan>
            <ns1:reach>0</ns1:reach>
            <ns1:targetListTrackId>1234567890</ns1:targetListTrackId>
            <ns1:tag>
              <ns1:snippet>&lt;!-- Yahoo Code for your Target List --&gt;
                &lt;script type="text/javascript"&gt;
                /* &lt;![CDATA[ */
                var yahoo_ss_retargeting_id = 1000137350;
                var yahoo_sstag_custom_params =
                window.yahoo_sstag_params;
                var yahoo_ss_retargeting = true;
                /* ]]&gt; */
                &lt;/script&gt;
                &lt;script type="text/javascript" src="//s.yimg.jp/images/listing/tool/cv/conversion.js"&gt;
                &lt;/script&gt;
                &lt;noscript&gt;
                &lt;div style="display:inline;"&gt;
                &lt;img height="1" width="1" style="border-style:none;" alt=""
                src="//b97.yahoo.co.jp/pagead/conversion/1000137350/?guid=ON&amp;amp;script=0&amp;amp;disvt=false"/&gt;
                &lt;/div&gt;
                &lt;/noscript&gt;</ns1:snippet>
            </ns1:tag>
          </ns1:targetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:targetList xsi:type="ns1:RuleBaseTargetList">
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:retargetingAccountStatus>
              <ns1:agreeDate>20150612</ns1:agreeDate>
              <ns1:reviewStatus>APPROVED</ns1:reviewStatus>
            </ns1:retargetingAccountStatus>
            <ns1:targetListId>100000003</ns1:targetListId>
            <ns1:targetListType>RULE</ns1:targetListType>
            <ns1:targetListName>ルールベースリスト</ns1:targetListName>
            <ns1:targetListDescription>ルールベースターゲットリスト</ns1:targetListDescription>
            <ns1:reachStorageStatus>OPEN</ns1:reachStorageStatus>
            <ns1:reachStorageSpan>180</ns1:reachStorageSpan>
            <ns1:reach>0</ns1:reach>
            <ns1:targetListTrackId>1234567890</ns1:targetListTrackId>
            <ns1:rules>
              <ns1:ruleItems xsi:type="ns1:UrlRuleItem">
                <ns1:ruleType>URL_RULE</ns1:ruleType>
                <ns1:operator>EQUALS</ns1:operator>
                <ns1:value>http://yahoo.co.jp</ns1:value>
                <ns1:urlKey>URL</ns1:urlKey>
              </ns1:ruleItems>
              <ns1:ruleItems xsi:type="ns1:UrlRuleItem">
                <ns1:ruleType>URL_RULE</ns1:ruleType>
                <ns1:operator>NOT_EQUAL</ns1:operator>
                <ns1:value>http://not.equal.yahoo.co.jp</ns1:value>
                <ns1:urlKey>REFFER_URL</ns1:urlKey>
              </ns1:ruleItems>
              <ns1:ruleItems xsi:type="ns1:UrlRuleItem">
                <ns1:ruleType>URL_RULE</ns1:ruleType>
                <ns1:operator>CONTAINS</ns1:operator>
                <ns1:value>http://contains.yahoo.co.jp</ns1:value>
                <ns1:urlKey>REFFER_URL</ns1:urlKey>
              </ns1:ruleItems>
              <ns1:ruleItems xsi:type="ns1:UrlRuleItem">
                <ns1:ruleType>URL_RULE</ns1:ruleType>
                <ns1:operator>NOT_CONTAIN</ns1:operator>
                <ns1:value>http://not.contain.yahoo.co.jp</ns1:value>
                <ns1:urlKey>REFFER_URL</ns1:urlKey>
              </ns1:ruleItems>
              <ns1:ruleItems xsi:type="ns1:UrlRuleItem">
                <ns1:ruleType>URL_RULE</ns1:ruleType>
                <ns1:operator>STARTS_WITH</ns1:operator>
                <ns1:value>http://starts.with.yahoo.co.jp</ns1:value>
                <ns1:urlKey>REFFER_URL</ns1:urlKey>
              </ns1:ruleItems>
              <ns1:ruleItems xsi:type="ns1:UrlRuleItem">
                <ns1:ruleType>URL_RULE</ns1:ruleType>
                <ns1:operator>NOT_START_WITH</ns1:operator>
                <ns1:value>http://not.start.with.yahoo.co.jp</ns1:value>
                <ns1:urlKey>REFFER_URL</ns1:urlKey>
              </ns1:ruleItems>
              <ns1:ruleItems xsi:type="ns1:UrlRuleItem">
                <ns1:ruleType>URL_RULE</ns1:ruleType>
                <ns1:operator>ENDS_WITH</ns1:operator>
                <ns1:value>http://ends.with.yahoo.co.jp</ns1:value>
                <ns1:urlKey>REFFER_URL</ns1:urlKey>
              </ns1:ruleItems>
              <ns1:ruleItems xsi:type="ns1:UrlRuleItem">
                <ns1:ruleType>URL_RULE</ns1:ruleType>
                <ns1:operator>NOT_END_WITH</ns1:operator>
                <ns1:value>http://not.end.with.yahoo.co.jp</ns1:value>
                <ns1:urlKey>REFFER_URL</ns1:urlKey>
              </ns1:ruleItems>
            </ns1:rules>
            <ns1:rules>
              <ns1:ruleItems xsi:type="ns1:UrlRuleItem">
                <ns1:ruleType>URL_RULE</ns1:ruleType>
                <ns1:operator>EQUALS</ns1:operator>
                <ns1:value>http://equals2.yahoo.co.jp</ns1:value>
                <ns1:urlKey>REFFER_URL</ns1:urlKey>
              </ns1:ruleItems>
            </ns1:rules>
            <ns1:isAllVisitor>TRUE</ns1:isAllVisitor>
            <ns1:isDateSpecific>TRUE</ns1:isDateSpecific>
            <ns1:startDate>20150701</ns1:startDate>
            <ns1:endDate>20151231</ns1:endDate>
          </ns1:targetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:targetList xsi:type="ns1:LogicalTargetList">
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:retargetingAccountStatus>
              <ns1:agreeDate>20150612</ns1:agreeDate>
              <ns1:reviewStatus>APPROVED</ns1:reviewStatus>
            </ns1:retargetingAccountStatus>
            <ns1:targetListId>100000004</ns1:targetListId>
            <ns1:targetListType>LOGICAL</ns1:targetListType>
            <ns1:targetListName>ロジカルリスト</ns1:targetListName>
            <ns1:targetListDescription>ロジカルターゲットリスト</ns1:targetListDescription>
            <ns1:reachStorageStatus>OPEN</ns1:reachStorageStatus>
            <ns1:reachStorageSpan>180</ns1:reachStorageSpan>
            <ns1:reach>0</ns1:reach>
            <ns1:targetListTrackId>1234567890</ns1:targetListTrackId>
            <ns1:logicalGroup>
              <ns1:condition>AND</ns1:condition>
              <ns1:logicalOperand>
                <ns1:targetListId>100000002</ns1:targetListId>
              </ns1:logicalOperand>
              <ns1:logicalOperand>
                <ns1:targetListId>100000003</ns1:targetListId>
              </ns1:logicalOperand>
              <ns1:logicalOperand>
                <ns1:targetListId>100000005</ns1:targetListId>
              </ns1:logicalOperand>
            </ns1:logicalGroup>
            <ns1:logicalGroup>
              <ns1:condition>OR</ns1:condition>
              <ns1:logicalOperand>
                <ns1:targetListId>100000006</ns1:targetListId>
              </ns1:logicalOperand>
              <ns1:logicalOperand>
                <ns1:targetListId>100000007</ns1:targetListId>
              </ns1:logicalOperand>
              <ns1:logicalOperand>
                <ns1:targetListId>100000008</ns1:targetListId>
              </ns1:logicalOperand>
            </ns1:logicalGroup>
            <ns1:logicalGroup>
              <ns1:condition>NOT</ns1:condition>
              <ns1:logicalOperand>
                <ns1:targetListId>100000009</ns1:targetListId>
              </ns1:logicalOperand>
            </ns1:logicalGroup>
          </ns1:targetList>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
ターゲットリストを追加します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [RetargetingListOperation](../data/RetargetingListOperation.md) | 操作の対象となるターゲットリストと処理の内容です。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      <ns1:accountId>1000000001</ns1:accountId>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>ADD</ns1:operator>
        <ns1:accountId>100000001</ns1:accountId>
        <ns1:operand xsi:type="ns1:DefaultTargetList">
          <ns1:accountId>100000001</ns1:accountId>
          <ns1:targetListType>DEFAULT</ns1:targetListType>
          <ns1:targetListName>デフォルトリスト</ns1:targetListName>
          <ns1:targetListDescription>sample description</ns1:targetListDescription>
          <ns1:reachStorageStatus>OPEN</ns1:reachStorageStatus>
          <ns1:reachStorageSpan>180</ns1:reachStorageSpan>
        </ns1:operand>
        <ns1:operand xsi:type="ns1:RuleBaseTargetList">
          <ns1:accountId>100000001</ns1:accountId>
          <ns1:targetListType>RULE</ns1:targetListType>
          <ns1:targetListName>ルールベースターゲットリスト</ns1:targetListName>
          <ns1:targetListDescription>sample description</ns1:targetListDescription>
          <ns1:reachStorageStatus>OPEN</ns1:reachStorageStatus>
          <ns1:reachStorageSpan>180</ns1:reachStorageSpan>
          <ns1:rules>
            <ns1:ruleItems xsi:type="ns1:UrlRuleItem">
              <ns1:ruleType>URL_RULE</ns1:ruleType>
              <ns1:operator>EQUALS</ns1:operator>
              <ns1:value>http://yahoo.co.jp</ns1:value>
              <ns1:urlKey>URL</ns1:urlKey>
            </ns1:ruleItems>
            <ns1:ruleItems xsi:type="ns1:UrlRuleItem">
              <ns1:ruleType>URL_RULE</ns1:ruleType>
              <ns1:operator>EQUALS</ns1:operator>
              <ns1:value>http://yahoo.com</ns1:value>
              <ns1:urlKey>REFFER_URL</ns1:urlKey>
            </ns1:ruleItems>
          </ns1:rules>
          <ns1:rules>
            <ns1:ruleItems xsi:type="ns1:UrlRuleItem">
              <ns1:ruleType>URL_RULE</ns1:ruleType>
              <ns1:operator>NOT_EQUAL</ns1:operator>
              <ns1:value>http://google.com</ns1:value>
              <ns1:urlKey>URL</ns1:urlKey>
            </ns1:ruleItems>
          </ns1:rules>
          <ns1:isAllVisitor>TRUE</ns1:isAllVisitor>
          <ns1:isDateSpecific>TRUE</ns1:isDateSpecific>
          <ns1:startDate>20150701</ns1:startDate>
          <ns1:endDate>20151231</ns1:endDate>
        </ns1:operand>
        <ns1:operand xsi:type="ns1:LogicalTargetList">
          <ns1:accountId>100000001</ns1:accountId>
          <ns1:targetListType>LOGICAL</ns1:targetListType>
          <ns1:targetListName>ロジカルターゲットリスト</ns1:targetListName>
          <ns1:targetListDescription>sample description</ns1:targetListDescription>
          <ns1:reachStorageStatus>OPEN</ns1:reachStorageStatus>
          <ns1:reachStorageSpan>180</ns1:reachStorageSpan>
          <ns1:logicalGroup>
            <ns1:condition>AND</ns1:condition>
            <ns1:logicalOperand>
              <ns1:targetListId>100000002</ns1:targetListId>
            </ns1:logicalOperand>
            <ns1:logicalOperand>
              <ns1:targetListId>100000003</ns1:targetListId>
            </ns1:logicalOperand>
          </ns1:logicalGroup>
          <ns1:logicalGroup>
            <ns1:condition>OR</ns1:condition>
            <ns1:logicalOperand>
              <ns1:targetListId>100000004</ns1:targetListId>
            </ns1:logicalOperand>
            <ns1:logicalOperand>
              <ns1:targetListId>100000005</ns1:targetListId>
            </ns1:logicalOperand>
          </ns1:logicalGroup>
          <ns1:logicalGroup>
            <ns1:condition>NOT</ns1:condition>
            <ns1:logicalOperand>
              <ns1:targetListId>100000006</ns1:targetListId>
            </ns1:logicalOperand>
          </ns1:logicalGroup>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [RetargetingListReturnValue](../data/RetargetingListReturnValue.md) | 操作結果を含むターゲットリストに関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>RetargetingListService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>RetargetingListReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>ADD</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:targetList xsi:type="ns1:DefaultTargetList">
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:retargetingAccountStatus />
            <ns1:targetListId>200000001</ns1:targetListId>
            <ns1:targetListType>DEFAULT</ns1:targetListType>
            <ns1:targetListName>デフォルトリスト</ns1:targetListName>
            <ns1:targetListDescription>デフォルトターゲットリスト</ns1:targetListDescription>
            <ns1:reachStorageStatus>OPEN</ns1:reachStorageStatus>
            <ns1:reachStorageSpan>180</ns1:reachStorageSpan>
            <ns1:tag />
          </ns1:targetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:targetList xsi:type="ns1:RuleBaseTargetList">
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:retargetingAccountStatus>
              <ns1:agreeDate>20150612</ns1:agreeDate>
              <ns1:reviewStatus>APPROVED</ns1:reviewStatus>
            </ns1:retargetingAccountStatus>
            <ns1:targetListId>200000002</ns1:targetListId>
            <ns1:targetListType>RULE</ns1:targetListType>
            <ns1:targetListName>ルールベースターゲットリスト</ns1:targetListName>
            <ns1:targetListDescription>sample description</ns1:targetListDescription>
            <ns1:reachStorageStatus>OPEN</ns1:reachStorageStatus>
            <ns1:reachStorageSpan>180</ns1:reachStorageSpan>
            <ns1:reach>0</ns1:reach>
            <ns1:rules>
              <ns1:ruleItems xsi:type="ns1:UrlRuleItem">
                <ns1:ruleType>URL_RULE</ns1:ruleType>
                <ns1:operator>EQUALS</ns1:operator>
                <ns1:value>http://yahoo.co.jp</ns1:value>
                <ns1:urlKey>URL</ns1:urlKey>
              </ns1:ruleItems>
              <ns1:ruleItems xsi:type="ns1:UrlRuleItem">
                <ns1:ruleType>URL_RULE</ns1:ruleType>
                <ns1:operator>EQUALS</ns1:operator>
                <ns1:value>http://yahoo.com</ns1:value>
                <ns1:urlKey>REFFER_URL</ns1:urlKey>
              </ns1:ruleItems>
            </ns1:rules>
            <ns1:rules>
              <ns1:ruleItems xsi:type="ns1:UrlRuleItem">
                <ns1:ruleType>URL_RULE</ns1:ruleType>
                <ns1:operator>NOT_EQUAL</ns1:operator>
                <ns1:value>http://google.com</ns1:value>
                <ns1:urlKey>URL</ns1:urlKey>
              </ns1:ruleItems>
            </ns1:rules>
            <ns1:isAllVisitor>TRUE</ns1:isAllVisitor>
            <ns1:isDateSpecific>TRUE</ns1:isDateSpecific>
            <ns1:startDate>20150701</ns1:startDate>
            <ns1:endDate>20151231</ns1:endDate>
          </ns1:targetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:targetList xsi:type="ns1:LogicalTargetList">
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:retargetingAccountStatus>
              <ns1:agreeDate>20150612</ns1:agreeDate>
              <ns1:reviewStatus>APPROVED</ns1:reviewStatus>
            </ns1:retargetingAccountStatus>
            <ns1:targetListId>200000003</ns1:targetListId>
            <ns1:targetListType>LOGICAL</ns1:targetListType>
            <ns1:targetListName>ロジカルターゲットリスト</ns1:targetListName>
            <ns1:targetListDescription>sample description</ns1:targetListDescription>
            <ns1:reachStorageStatus>OPEN</ns1:reachStorageStatus>
            <ns1:reachStorageSpan>180</ns1:reachStorageSpan>
            <ns1:reach>0</ns1:reach>
            <ns1:logicalGroup>
              <ns1:condition>AND</ns1:condition>
              <ns1:logicalOperand>
                <ns1:targetListId>100000002</ns1:targetListId>
              </ns1:logicalOperand>
              <ns1:logicalOperand>
                <ns1:targetListId>100000003</ns1:targetListId>
              </ns1:logicalOperand>
            </ns1:logicalGroup>
            <ns1:logicalGroup>
              <ns1:condition>OR</ns1:condition>
              <ns1:logicalOperand>
                <ns1:targetListId>100000004</ns1:targetListId>
              </ns1:logicalOperand>
              <ns1:logicalOperand>
                <ns1:targetListId>100000005</ns1:targetListId>
              </ns1:logicalOperand>
            </ns1:logicalGroup>
            <ns1:logicalGroup>
              <ns1:condition>NOT</ns1:condition>
              <ns1:logicalOperand>
                <ns1:targetListId>100000006</ns1:targetListId>
              </ns1:logicalOperand>
            </ns1:logicalGroup>
          </ns1:targetList>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
ターゲットリストを更新します。

#### リクエスト

| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [RetargetingListOperation](../data/RetargetingListOperation.md) | 操作の対象となるターゲットリストと処理の内容です。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      <ns1:accountId>1000000001</ns1:accountId>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>SET</ns1:operator>
        <ns1:accountId>100000001</ns1:accountId>
        <ns1:operand xsi:type="ns1:DefaultTargetList">
          <ns1:accountId>100000001</ns1:accountId>
          <ns1:targetListId>200000001</ns1:targetListId>
          <ns1:targetListType>DEFAULT</ns1:targetListType>
          <ns1:targetListName>デフォルトターゲットリスト</ns1:targetListName>
          <ns1:targetListDescription>sample description</ns1:targetListDescription>
          <ns1:reachStorageStatus>OPEN</ns1:reachStorageStatus>
          <ns1:reachStorageSpan>1</ns1:reachStorageSpan>
        </ns1:operand>
        <ns1:operand xsi:type="ns1:RuleBaseTargetList">
          <ns1:accountId>100000001</ns1:accountId>
          <ns1:targetListId>200000002</ns1:targetListId>
          <ns1:targetListType>RULE</ns1:targetListType>
          <ns1:targetListName>ルールベースターゲットリスト(更新)</ns1:targetListName>
          <ns1:targetListDescription>sample description</ns1:targetListDescription>
          <ns1:reachStorageStatus>CLOSED</ns1:reachStorageStatus>
          <ns1:reachStorageSpan>1</ns1:reachStorageSpan>
          <ns1:rules>
            <ns1:ruleItems xsi:type="ns1:UrlRuleItem">
              <ns1:ruleType>URL_RULE</ns1:ruleType>
              <ns1:operator>CONTAINS</ns1:operator>
              <ns1:value>http://yahoo.com</ns1:value>
              <ns1:urlKey>REFFER_URL</ns1:urlKey>
            </ns1:ruleItems>
          </ns1:rules>
          <ns1:isAllVisitor>TRUE</ns1:isAllVisitor>
          <ns1:startDate>20160701</ns1:startDate>
          <ns1:endDate>20161231</ns1:endDate>
        </ns1:operand>
        <ns1:operand xsi:type="ns1:LogicalTargetList">
          <ns1:accountId>100000001</ns1:accountId>
          <ns1:targetListId>200000003</ns1:targetListId>
          <ns1:targetListType>LOGICAL</ns1:targetListType>
          <ns1:targetListName>ロジカルターゲットリスト(更新)</ns1:targetListName>
          <ns1:targetListDescription>sample description</ns1:targetListDescription>
          <ns1:reachStorageStatus>CLOSED</ns1:reachStorageStatus>
          <ns1:reachStorageSpan>1</ns1:reachStorageSpan>
          <ns1:logicalGroup>
            <ns1:logicalOperand>
              <ns1:targetListId>100000005</ns1:targetListId>
            </ns1:logicalOperand>
          </ns1:logicalGroup>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [RetargetingListReturnValue](../data/RetargetingListReturnValue.md) | 操作結果を含むターゲットリストに関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>RetargetingListService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>RetargetingListReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>SET</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:targetList xsi:type="ns1:DefaultTargetList">
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:retargetingAccountStatus>
              <ns1:agreeDate>20150626</ns1:agreeDate>
              <ns1:reviewStatus>APPROVED</ns1:reviewStatus>
            </ns1:retargetingAccountStatus>
            <ns1:targetListId>200000001</ns1:targetListId>
            <ns1:targetListType>DEFAULT</ns1:targetListType>
            <ns1:targetListName>デフォルトリスト</ns1:targetListName>
            <ns1:targetListDescription>sample description</ns1:targetListDescription>
            <ns1:reachStorageStatus>OPEN</ns1:reachStorageStatus>
            <ns1:reachStorageSpan>1</ns1:reachStorageSpan>
            <ns1:reach>0</ns1:reach>
            <ns1:tag />
          </ns1:targetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:targetList xsi:type="ns1:RuleBaseTargetList">
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:retargetingAccountStatus>
              <ns1:agreeDate>20150612</ns1:agreeDate>
              <ns1:reviewStatus>APPROVED</ns1:reviewStatus>
            </ns1:retargetingAccountStatus>
            <ns1:targetListId>200000002</ns1:targetListId>
            <ns1:targetListType>RULE</ns1:targetListType>
            <ns1:targetListName>ルールベースターゲットリスト(更新)</ns1:targetListName>
            <ns1:targetListDescription>sample description</ns1:targetListDescription>
            <ns1:reachStorageStatus>CLOSED</ns1:reachStorageStatus>
            <ns1:reachStorageSpan>1</ns1:reachStorageSpan>
            <ns1:reach>0</ns1:reach>
            <ns1:targetListTrackId>1234567890</ns1:targetListTrackId>
            <ns1:rules>
              <ns1:ruleItems xsi:type="ns1:UrlRuleItem">
                <ns1:ruleType>URL_RULE</ns1:ruleType>
                <ns1:operator>CONTAINS</ns1:operator>
                <ns1:value>http://yahoo.com</ns1:value>
                <ns1:urlKey>REFFER_URL</ns1:urlKey>
              </ns1:ruleItems>
            </ns1:rules>
            <ns1:isAllVisitor>TRUE</ns1:isAllVisitor>
            <ns1:isDateSpecific>TRUE</ns1:isDateSpecific>
            <ns1:startDate>20160701</ns1:startDate>
            <ns1:endDate>20161231</ns1:endDate>
          </ns1:targetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:targetList xsi:type="ns1:LogicalTargetList">
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:retargetingAccountStatus>
              <ns1:agreeDate>20150612</ns1:agreeDate>
              <ns1:reviewStatus>APPROVED</ns1:reviewStatus>
            </ns1:retargetingAccountStatus>
            <ns1:targetListId>200000003</ns1:targetListId>
            <ns1:targetListType>LOGICAL</ns1:targetListType>
            <ns1:targetListName>ロジカルターゲットリスト(更新)</ns1:targetListName>
            <ns1:targetListDescription>sample description</ns1:targetListDescription>
            <ns1:reachStorageStatus>CLOSED</ns1:reachStorageStatus>
            <ns1:reachStorageSpan>1</ns1:reachStorageSpan>
            <ns1:reach>0</ns1:reach>
            <ns1:targetListTrackId>1234567890</ns1:targetListTrackId>
            <ns1:logicalGroup>
              <ns1:condition>OR</ns1:condition>
              <ns1:logicalOperand>
                <ns1:targetListId>100000005</ns1:targetListId>
              </ns1:logicalOperand>
            </ns1:logicalGroup>
          </ns1:targetList>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
