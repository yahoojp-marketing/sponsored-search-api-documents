# RetargetingListService
RetargetingListService is to get, add, or update information of target list.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201805/RetargetingListService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201805/RetargetingListService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201805/RetargetingList

#### Overview
RetargetingListService provides operation of target list.

#### Operation
Describe the operation which provides at RetargetingListService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)

#### Object
[RetargetingList](../data/RetargetingList)

## get
Retrieves the target list information.

#### Request
| Parameter | Restrictions | Data type | Description |
|---|---|---|---|
| selector | Req | [RetargetingListSelector](../data/RetargetingList/RetargetingListSelector.md) | Retrieve target list information for site retargeting. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/RetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201805/RetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <selector>
        <accountId>1111</accountId>
        <targetListIds>100000001</targetListIds>
        <targetListIds>100000002</targetListIds>
        <targetListTypes>LOGICAL</targetListTypes>
        <targetListTypes>RULE</targetListTypes>
        <targetListTypes>DEFAULT</targetListTypes>
        <owner>SHARED</owner>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
Response fields in normal cases.

| Field | Data type | Description |
|---|---|---|
| rval | [RetargetingListPage](../data/RetargetingList/RetargetingListPage.md) | Container holding the target list entries. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/RetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>RetargetingList</ns2:service>
      <ns2:requestTime>1523506337133</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/RetargetingList">
      <ns2:rval>
        <totalNumEntries>4</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:DefaultTargetList">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:owner>OWNER</ns2:owner>
            <ns2:retargetingAccountStatus>
              <ns2:agreeDate>20170529</ns2:agreeDate>
              <ns2:reviewStatus>APPROVED</ns2:reviewStatus>
            </ns2:retargetingAccountStatus>
            <ns2:targetListId>2222</ns2:targetListId>
            <ns2:targetListTrackId>3333</ns2:targetListTrackId>
            <ns2:targetListType>DEFAULT</ns2:targetListType>
            <ns2:targetListName>TargetList Default</ns2:targetListName>
            <ns2:targetListDescription>TargetList Default</ns2:targetListDescription>
            <ns2:reachStorageStatus>OPEN</ns2:reachStorageStatus>
            <ns2:reachStorageSpan>180</ns2:reachStorageSpan>
            <ns2:reach>0</ns2:reach>
            <ns2:tag>
              <ns2:snippet>&amp;lt;!-- Yahoo Code for your Target List --&amp;gt;
&amp;lt;script type="text/javascript"&amp;gt;
/* &amp;lt;![CDATA[ */
var yahoo_ss_retargeting_id = 1000136832;
var yahoo_sstag_custom_params = window.yahoo_sstag_params;
var yahoo_ss_retargeting = true;
/* ]]&amp;gt; */
&amp;lt;/script&amp;gt;
&amp;lt;script type="text/javascript" src="https://s.yimg.jp/images/listing/tool/cv/conversion.js"&amp;gt;
&amp;lt;/script&amp;gt;
&amp;lt;noscript&amp;gt;
&amp;lt;div style="display:inline;"&amp;gt;
&amp;lt;img height="1" width="1" style="border-style:none;" alt="" src="https://b97.yahoo.co.jp/pagead/conversion/1000136832/?guid=ON&amp;amp;amp;script=0&amp;amp;amp;disvt=false"/&amp;gt;
&amp;lt;/div&amp;gt;
&amp;lt;/noscript&amp;gt;</ns2:snippet>
            </ns2:tag>
          </ns2:targetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:RuleBaseTargetList">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:owner>SHARED</ns2:owner>
            <ns2:retargetingAccountStatus>
              <ns2:agreeDate>20170629</ns2:agreeDate>
              <ns2:reviewStatus>APPROVED</ns2:reviewStatus>
            </ns2:retargetingAccountStatus>
            <ns2:targetListId>12222</ns2:targetListId>
            <ns2:targetListTrackId>13333</ns2:targetListTrackId>
            <ns2:targetListType>RULE</ns2:targetListType>
            <ns2:targetListName>TargetList RULE</ns2:targetListName>
            <ns2:targetListDescription>TargetList RULE</ns2:targetListDescription>
            <ns2:reachStorageStatus>OPEN</ns2:reachStorageStatus>
            <ns2:reachStorageSpan>180</ns2:reachStorageSpan>
            <ns2:reach>0</ns2:reach>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>EQUALS</ns2:operator>
                <ns2:value>http://yahoo.co.jp</ns2:value>
                <ns2:urlKey>URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>NOT_EQUAL</ns2:operator>
                <ns2:value>http://not.equal.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>CONTAINS</ns2:operator>
                <ns2:value>http://contains.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>NOT_CONTAIN</ns2:operator>
                <ns2:value>http://not.contain.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>STARTS_WITH</ns2:operator>
                <ns2:value>http://starts.with.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>NOT_START_WITH</ns2:operator>
                <ns2:value>http://not.start.with.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>ENDS_WITH</ns2:operator>
                <ns2:value>http://ends.with.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>NOT_END_WITH</ns2:operator>
                <ns2:value>http://not.end.with.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:isAllVisitor>TRUE</ns2:isAllVisitor>
            <ns2:isDateSpecific>FALSE</ns2:isDateSpecific>
          </ns2:targetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:LogicalTargetList">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:owner>SHARED</ns2:owner>
            <ns2:retargetingAccountStatus>
              <ns2:agreeDate>20170629</ns2:agreeDate>
              <ns2:reviewStatus>APPROVED</ns2:reviewStatus>
            </ns2:retargetingAccountStatus>
            <ns2:targetListId>912222</ns2:targetListId>
            <ns2:targetListTrackId>913333</ns2:targetListTrackId>
            <ns2:targetListType>LOGICAL</ns2:targetListType>
            <ns2:targetListName>TargetList LOGICAL</ns2:targetListName>
            <ns2:targetListDescription>TargetList LOGICAL</ns2:targetListDescription>
            <ns2:reachStorageStatus>OPEN</ns2:reachStorageStatus>
            <ns2:reachStorageSpan>180</ns2:reachStorageSpan>
            <ns2:reach>0</ns2:reach>
            <ns2:logicalGroup>
              <ns2:condition>AND</ns2:condition>
              <ns2:logicalOperand>
                <ns2:targetListId>1111111</ns2:targetListId>
              </ns2:logicalOperand>
              <ns2:logicalOperand>
                <ns2:targetListId>1111112</ns2:targetListId>
              </ns2:logicalOperand>
              <ns2:logicalOperand>
                <ns2:targetListId>1111113</ns2:targetListId>
              </ns2:logicalOperand>
            </ns2:logicalGroup>
            <ns2:logicalGroup>
              <ns2:condition>OR</ns2:condition>
              <ns2:logicalOperand>
                <ns2:targetListId>2111111</ns2:targetListId>
              </ns2:logicalOperand>
              <ns2:logicalOperand>
                <ns2:targetListId>2111112</ns2:targetListId>
              </ns2:logicalOperand>
            </ns2:logicalGroup>
            <ns2:logicalGroup>
              <ns2:condition>NOT</ns2:condition>
              <ns2:logicalOperand>
                <ns2:targetListId>3111111</ns2:targetListId>
              </ns2:logicalOperand>
            </ns2:logicalGroup>
          </ns2:targetList>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
Adds target list.

#### Request
| Parameter | Restrictions | Data type | Description |
|---|---|---|---|
| operations | Req | [RetargetingListOperation](../data/RetargetingList/RetargetingListOperation.md) |The target list selector for operations and list of operations. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/RetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/RetargetingList">
      <operations>
        <operator>ADD</operator>
        <accountId>0</accountId>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="DefaultTargetList">
          <accountId>1111</accountId>
          <targetListType>DEFAULT</targetListType>
          <targetListName>TargetList Default</targetListName>
          <targetListDescription>TargetList Default</targetListDescription>
          <reachStorageStatus>OPEN</reachStorageStatus>
          <reachStorageSpan>180</reachStorageSpan>
        </operand>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RuleBaseTargetList">
          <accountId>1111</accountId>
          <targetListType>RULE</targetListType>
          <targetListName>TargetList RULE</targetListName>
          <targetListDescription>TargetList RULE</targetListDescription>
          <reachStorageStatus>OPEN</reachStorageStatus>
          <reachStorageSpan>180</reachStorageSpan>
          <rules>
            <ruleItems xsi:type="UrlRuleItem">
              <ruleType>URL_RULE</ruleType>
              <operator>EQUALS</operator>
              <value>http://yahoo.co.jp</value>
              <urlKey>URL</urlKey>
            </ruleItems>
          </rules>
          <rules>
            <ruleItems xsi:type="UrlRuleItem">
              <ruleType>URL_RULE</ruleType>
              <operator>NOT_EQUAL</operator>
              <value>http://not.equal.yahoo.co.jp</value>
              <urlKey>REFFER_URL</urlKey>
            </ruleItems>
          </rules>
          <rules>
            <ruleItems xsi:type="UrlRuleItem">
              <ruleType>URL_RULE</ruleType>
              <operator>CONTAINS</operator>
              <value>http://contains.yahoo.co.jp</value>
              <urlKey>REFFER_URL</urlKey>
            </ruleItems>
          </rules>
          <rules>
            <ruleItems xsi:type="UrlRuleItem">
              <ruleType>URL_RULE</ruleType>
              <operator>NOT_CONTAIN</operator>
              <value>http://not.contain.yahoo.co.jp</value>
              <urlKey>REFFER_URL</urlKey>
            </ruleItems>
          </rules>
          <rules>
            <ruleItems xsi:type="UrlRuleItem">
              <ruleType>URL_RULE</ruleType>
              <operator>STARTS_WITH</operator>
              <value>http://starts.with.yahoo.co.jp</value>
              <urlKey>REFFER_URL</urlKey>
            </ruleItems>
          </rules>
          <rules>
            <ruleItems xsi:type="UrlRuleItem">
              <ruleType>URL_RULE</ruleType>
              <operator>NOT_START_WITH</operator>
              <value>http://not.start.with.yahoo.co.jp</value>
              <urlKey>REFFER_URL</urlKey>
            </ruleItems>
          </rules>
          <rules>
            <ruleItems xsi:type="UrlRuleItem">
              <ruleType>URL_RULE</ruleType>
              <operator>ENDS_WITH</operator>
              <value>http://ends.with.yahoo.co.jp</value>
              <urlKey>REFFER_URL</urlKey>
            </ruleItems>
          </rules>
          <rules>
            <ruleItems xsi:type="UrlRuleItem">
              <ruleType>URL_RULE</ruleType>
              <operator>NOT_END_WITH</operator>
              <value>http://not.end.with.yahoo.co.jp</value>
              <urlKey>REFFER_URL</urlKey>
            </ruleItems>
          </rules>
          <isAllVisitor>TRUE</isAllVisitor>
          <isDateSpecific>FALSE</isDateSpecific>
        </operand>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="LogicalTargetList">
          <accountId>1111</accountId>
          <targetListType>LOGICAL</targetListType>
          <targetListName>TargetList LOGICAL</targetListName>
          <targetListDescription>TargetList LOGICAL</targetListDescription>
          <reachStorageStatus>OPEN</reachStorageStatus>
          <reachStorageSpan>180</reachStorageSpan>
          <logicalGroup>
            <condition>AND</condition>
            <logicalOperand>
              <targetListId>1111111</targetListId>
            </logicalOperand>
            <logicalOperand>
              <targetListId>1111112</targetListId>
            </logicalOperand>
            <logicalOperand>
              <targetListId>1111113</targetListId>
            </logicalOperand>
          </logicalGroup>
          <logicalGroup>
            <condition>OR</condition>
            <logicalOperand>
              <targetListId>2111111</targetListId>
            </logicalOperand>
            <logicalOperand>
              <targetListId>2111112</targetListId>
            </logicalOperand>
          </logicalGroup>
          <logicalGroup>
            <condition>NOT</condition>
            <logicalOperand>
              <targetListId>3111111</targetListId>
            </logicalOperand>
          </logicalGroup>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
Response fields in normal cases.

| Field | Data type | Description |
|---|---|---|
| rval | [RetargetingListReturnValue](../data/RetargetingList/RetargetingListReturnValue.md) | Container holding information related to the target list including operation result.|

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/RetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>RetargetingList</ns2:service>
      <ns2:requestTime>1523506337160</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/RetargetingList">
      <ns2:rval>
        <ListReturnValue.Type>RetargetingListReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:DefaultTargetList">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:owner>OWNER</ns2:owner>
            <ns2:retargetingAccountStatus>
              <ns2:agreeDate>20170529</ns2:agreeDate>
              <ns2:reviewStatus>APPROVED</ns2:reviewStatus>
            </ns2:retargetingAccountStatus>
            <ns2:targetListId>2222</ns2:targetListId>
            <ns2:targetListTrackId>3333</ns2:targetListTrackId>
            <ns2:targetListType>DEFAULT</ns2:targetListType>
            <ns2:targetListName>TargetList Default</ns2:targetListName>
            <ns2:targetListDescription>TargetList Default</ns2:targetListDescription>
            <ns2:reachStorageStatus>OPEN</ns2:reachStorageStatus>
            <ns2:reachStorageSpan>180</ns2:reachStorageSpan>
            <ns2:reach>0</ns2:reach>
            <ns2:tag/>
          </ns2:targetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:RuleBaseTargetList">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:owner>SHARED</ns2:owner>
            <ns2:retargetingAccountStatus>
              <ns2:agreeDate>20170629</ns2:agreeDate>
              <ns2:reviewStatus>APPROVED</ns2:reviewStatus>
            </ns2:retargetingAccountStatus>
            <ns2:targetListId>12222</ns2:targetListId>
            <ns2:targetListTrackId>13333</ns2:targetListTrackId>
            <ns2:targetListType>RULE</ns2:targetListType>
            <ns2:targetListName>TargetList RULE</ns2:targetListName>
            <ns2:targetListDescription>TargetList RULE</ns2:targetListDescription>
            <ns2:reachStorageStatus>OPEN</ns2:reachStorageStatus>
            <ns2:reachStorageSpan>180</ns2:reachStorageSpan>
            <ns2:reach>0</ns2:reach>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>EQUALS</ns2:operator>
                <ns2:value>http://yahoo.co.jp</ns2:value>
                <ns2:urlKey>URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>NOT_EQUAL</ns2:operator>
                <ns2:value>http://not.equal.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>CONTAINS</ns2:operator>
                <ns2:value>http://contains.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>NOT_CONTAIN</ns2:operator>
                <ns2:value>http://not.contain.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>STARTS_WITH</ns2:operator>
                <ns2:value>http://starts.with.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>NOT_START_WITH</ns2:operator>
                <ns2:value>http://not.start.with.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>ENDS_WITH</ns2:operator>
                <ns2:value>http://ends.with.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>NOT_END_WITH</ns2:operator>
                <ns2:value>http://not.end.with.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:isAllVisitor>TRUE</ns2:isAllVisitor>
            <ns2:isDateSpecific>FALSE</ns2:isDateSpecific>
          </ns2:targetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:LogicalTargetList">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:owner>SHARED</ns2:owner>
            <ns2:retargetingAccountStatus>
              <ns2:agreeDate>20170629</ns2:agreeDate>
              <ns2:reviewStatus>APPROVED</ns2:reviewStatus>
            </ns2:retargetingAccountStatus>
            <ns2:targetListId>912222</ns2:targetListId>
            <ns2:targetListTrackId>913333</ns2:targetListTrackId>
            <ns2:targetListType>LOGICAL</ns2:targetListType>
            <ns2:targetListName>TargetList LOGICAL</ns2:targetListName>
            <ns2:targetListDescription>TargetList LOGICAL</ns2:targetListDescription>
            <ns2:reachStorageStatus>OPEN</ns2:reachStorageStatus>
            <ns2:reachStorageSpan>180</ns2:reachStorageSpan>
            <ns2:reach>0</ns2:reach>
            <ns2:logicalGroup>
              <ns2:condition>AND</ns2:condition>
              <ns2:logicalOperand>
                <ns2:targetListId>1111111</ns2:targetListId>
              </ns2:logicalOperand>
              <ns2:logicalOperand>
                <ns2:targetListId>1111112</ns2:targetListId>
              </ns2:logicalOperand>
              <ns2:logicalOperand>
                <ns2:targetListId>1111113</ns2:targetListId>
              </ns2:logicalOperand>
            </ns2:logicalGroup>
            <ns2:logicalGroup>
              <ns2:condition>OR</ns2:condition>
              <ns2:logicalOperand>
                <ns2:targetListId>2111111</ns2:targetListId>
              </ns2:logicalOperand>
              <ns2:logicalOperand>
                <ns2:targetListId>2111112</ns2:targetListId>
              </ns2:logicalOperand>
            </ns2:logicalGroup>
            <ns2:logicalGroup>
              <ns2:condition>NOT</ns2:condition>
              <ns2:logicalOperand>
                <ns2:targetListId>3111111</ns2:targetListId>
              </ns2:logicalOperand>
            </ns2:logicalGroup>
          </ns2:targetList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
Updates the target list.

#### Request
| Parameter | Restrictions | Data type | Description |
|---|---|---|---|
| operations | Req | [RetargetingListOperation](../data/RetargetingList/RetargetingListOperation.md) | Updates the target list for site retargeting. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/RetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/RetargetingList">
      <operations>
        <operator>ADD</operator>
        <accountId>0</accountId>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="DefaultTargetList">
          <accountId>1111</accountId>
          <targetListId>2222</targetListId>
          <targetListType>DEFAULT</targetListType>
          <targetListName>TargetList Default</targetListName>
          <targetListDescription>TargetList Default</targetListDescription>
          <reachStorageStatus>OPEN</reachStorageStatus>
          <reachStorageSpan>180</reachStorageSpan>
        </operand>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RuleBaseTargetList">
          <accountId>1111</accountId>
          <targetListId>12222</targetListId>
          <targetListType>RULE</targetListType>
          <targetListName>TargetList RULE</targetListName>
          <targetListDescription>TargetList RULE</targetListDescription>
          <reachStorageStatus>OPEN</reachStorageStatus>
          <reachStorageSpan>180</reachStorageSpan>
          <rules>
            <ruleItems xsi:type="UrlRuleItem">
              <ruleType>URL_RULE</ruleType>
              <operator>EQUALS</operator>
              <value>http://yahoo.co.jp</value>
              <urlKey>URL</urlKey>
            </ruleItems>
          </rules>
          <rules>
            <ruleItems xsi:type="UrlRuleItem">
              <ruleType>URL_RULE</ruleType>
              <operator>NOT_EQUAL</operator>
              <value>http://not.equal.yahoo.co.jp</value>
              <urlKey>REFFER_URL</urlKey>
            </ruleItems>
          </rules>
          <rules>
            <ruleItems xsi:type="UrlRuleItem">
              <ruleType>URL_RULE</ruleType>
              <operator>CONTAINS</operator>
              <value>http://contains.yahoo.co.jp</value>
              <urlKey>REFFER_URL</urlKey>
            </ruleItems>
          </rules>
          <rules>
            <ruleItems xsi:type="UrlRuleItem">
              <ruleType>URL_RULE</ruleType>
              <operator>NOT_CONTAIN</operator>
              <value>http://not.contain.yahoo.co.jp</value>
              <urlKey>REFFER_URL</urlKey>
            </ruleItems>
          </rules>
          <rules>
            <ruleItems xsi:type="UrlRuleItem">
              <ruleType>URL_RULE</ruleType>
              <operator>STARTS_WITH</operator>
              <value>http://starts.with.yahoo.co.jp</value>
              <urlKey>REFFER_URL</urlKey>
            </ruleItems>
          </rules>
          <rules>
            <ruleItems xsi:type="UrlRuleItem">
              <ruleType>URL_RULE</ruleType>
              <operator>NOT_START_WITH</operator>
              <value>http://not.start.with.yahoo.co.jp</value>
              <urlKey>REFFER_URL</urlKey>
            </ruleItems>
          </rules>
          <rules>
            <ruleItems xsi:type="UrlRuleItem">
              <ruleType>URL_RULE</ruleType>
              <operator>ENDS_WITH</operator>
              <value>http://ends.with.yahoo.co.jp</value>
              <urlKey>REFFER_URL</urlKey>
            </ruleItems>
          </rules>
          <rules>
            <ruleItems xsi:type="UrlRuleItem">
              <ruleType>URL_RULE</ruleType>
              <operator>NOT_END_WITH</operator>
              <value>http://not.end.with.yahoo.co.jp</value>
              <urlKey>REFFER_URL</urlKey>
            </ruleItems>
          </rules>
          <isAllVisitor>TRUE</isAllVisitor>
          <isDateSpecific>FALSE</isDateSpecific>
        </operand>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="LogicalTargetList">
          <accountId>1111</accountId>
          <targetListId>912222</targetListId>
          <targetListType>LOGICAL</targetListType>
          <targetListName>TargetList LOGICAL</targetListName>
          <targetListDescription>TargetList LOGICAL</targetListDescription>
          <reachStorageStatus>OPEN</reachStorageStatus>
          <reachStorageSpan>180</reachStorageSpan>
          <logicalGroup>
            <condition>AND</condition>
            <logicalOperand>
              <targetListId>1111111</targetListId>
            </logicalOperand>
            <logicalOperand>
              <targetListId>1111112</targetListId>
            </logicalOperand>
            <logicalOperand>
              <targetListId>1111113</targetListId>
            </logicalOperand>
          </logicalGroup>
          <logicalGroup>
            <condition>OR</condition>
            <logicalOperand>
              <targetListId>2111111</targetListId>
            </logicalOperand>
            <logicalOperand>
              <targetListId>2111112</targetListId>
            </logicalOperand>
          </logicalGroup>
          <logicalGroup>
            <condition>NOT</condition>
            <logicalOperand>
              <targetListId>3111111</targetListId>
            </logicalOperand>
          </logicalGroup>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
Response fields in normal cases.

| Field | Data type | Description |
|---|---|---|
| rval | [RetargetingListReturnValue](../data/RetargetingList/RetargetingListReturnValue.md) |Container holding the information related to target list including operation result. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/RetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>RetargetingList</ns2:service>
      <ns2:requestTime>1523506337191</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/RetargetingList">
      <ns2:rval>
        <ListReturnValue.Type>RetargetingListReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:DefaultTargetList">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:owner>OWNER</ns2:owner>
            <ns2:retargetingAccountStatus>
              <ns2:agreeDate>20170529</ns2:agreeDate>
              <ns2:reviewStatus>APPROVED</ns2:reviewStatus>
            </ns2:retargetingAccountStatus>
            <ns2:targetListId>2222</ns2:targetListId>
            <ns2:targetListTrackId>3333</ns2:targetListTrackId>
            <ns2:targetListType>DEFAULT</ns2:targetListType>
            <ns2:targetListName>TargetList Default</ns2:targetListName>
            <ns2:targetListDescription>TargetList Default</ns2:targetListDescription>
            <ns2:reachStorageStatus>OPEN</ns2:reachStorageStatus>
            <ns2:reachStorageSpan>180</ns2:reachStorageSpan>
            <ns2:reach>0</ns2:reach>
            <ns2:tag/>
          </ns2:targetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:RuleBaseTargetList">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:owner>SHARED</ns2:owner>
            <ns2:retargetingAccountStatus>
              <ns2:agreeDate>20170629</ns2:agreeDate>
              <ns2:reviewStatus>APPROVED</ns2:reviewStatus>
            </ns2:retargetingAccountStatus>
            <ns2:targetListId>12222</ns2:targetListId>
            <ns2:targetListTrackId>13333</ns2:targetListTrackId>
            <ns2:targetListType>RULE</ns2:targetListType>
            <ns2:targetListName>TargetList RULE</ns2:targetListName>
            <ns2:targetListDescription>TargetList RULE</ns2:targetListDescription>
            <ns2:reachStorageStatus>OPEN</ns2:reachStorageStatus>
            <ns2:reachStorageSpan>180</ns2:reachStorageSpan>
            <ns2:reach>0</ns2:reach>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>EQUALS</ns2:operator>
                <ns2:value>http://yahoo.co.jp</ns2:value>
                <ns2:urlKey>URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>NOT_EQUAL</ns2:operator>
                <ns2:value>http://not.equal.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>CONTAINS</ns2:operator>
                <ns2:value>http://contains.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>NOT_CONTAIN</ns2:operator>
                <ns2:value>http://not.contain.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>STARTS_WITH</ns2:operator>
                <ns2:value>http://starts.with.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>NOT_START_WITH</ns2:operator>
                <ns2:value>http://not.start.with.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>ENDS_WITH</ns2:operator>
                <ns2:value>http://ends.with.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:rules>
              <ns2:ruleItems xsi:type="ns2:UrlRuleItem">
                <ns2:ruleType>URL_RULE</ns2:ruleType>
                <ns2:operator>NOT_END_WITH</ns2:operator>
                <ns2:value>http://not.end.with.yahoo.co.jp</ns2:value>
                <ns2:urlKey>REFFER_URL</ns2:urlKey>
              </ns2:ruleItems>
            </ns2:rules>
            <ns2:isAllVisitor>TRUE</ns2:isAllVisitor>
            <ns2:isDateSpecific>FALSE</ns2:isDateSpecific>
          </ns2:targetList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:targetList xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:LogicalTargetList">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:owner>SHARED</ns2:owner>
            <ns2:retargetingAccountStatus>
              <ns2:agreeDate>20170629</ns2:agreeDate>
              <ns2:reviewStatus>APPROVED</ns2:reviewStatus>
            </ns2:retargetingAccountStatus>
            <ns2:targetListId>912222</ns2:targetListId>
            <ns2:targetListTrackId>913333</ns2:targetListTrackId>
            <ns2:targetListType>LOGICAL</ns2:targetListType>
            <ns2:targetListName>TargetList LOGICAL</ns2:targetListName>
            <ns2:targetListDescription>TargetList LOGICAL</ns2:targetListDescription>
            <ns2:reachStorageStatus>OPEN</ns2:reachStorageStatus>
            <ns2:reachStorageSpan>180</ns2:reachStorageSpan>
            <ns2:reach>0</ns2:reach>
            <ns2:logicalGroup>
              <ns2:condition>AND</ns2:condition>
              <ns2:logicalOperand>
                <ns2:targetListId>1111111</ns2:targetListId>
              </ns2:logicalOperand>
              <ns2:logicalOperand>
                <ns2:targetListId>1111112</ns2:targetListId>
              </ns2:logicalOperand>
              <ns2:logicalOperand>
                <ns2:targetListId>1111113</ns2:targetListId>
              </ns2:logicalOperand>
            </ns2:logicalGroup>
            <ns2:logicalGroup>
              <ns2:condition>OR</ns2:condition>
              <ns2:logicalOperand>
                <ns2:targetListId>2111111</ns2:targetListId>
              </ns2:logicalOperand>
              <ns2:logicalOperand>
                <ns2:targetListId>2111112</ns2:targetListId>
              </ns2:logicalOperand>
            </ns2:logicalGroup>
            <ns2:logicalGroup>
              <ns2:condition>NOT</ns2:condition>
              <ns2:logicalOperand>
                <ns2:targetListId>3111111</ns2:targetListId>
              </ns2:logicalOperand>
            </ns2:logicalGroup>
          </ns2:targetList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
