# AdGroupRetargetingListService
AdGroupRetargetingListService is to get, add, update, or delete information of target list setting in ad group level.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201901/AdGroupRetargetingListService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201901/AdGroupRetargetingListService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201901/AdGroupRetargetingList

#### Service Overview
AdGroupRetargetingListService provides operation of target list setting in ad group level.

#### Operation
Describe the operation which provides at AdGroupRetargetingListService.
+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

#### Object
[AdGroupRetargetingList](../data/AdGroupRetargetingList)

## get
Retreive the target list setting in ad group level.

#### Request
| name | req? | type | description |
|---|---|---|---|
| selector | Req| [AdGroupRetargetingListSelector](../data/AdGroupRetargetingList/AdGroupRetargetingListSelector.md) | Target list deliver information relate to the operations to apply. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201901/AdGroupRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <selector>
        <accountId>1111</accountId>
        <campaignIds>1</campaignIds>
        <campaignIds>2</campaignIds>
        <targetListIds>100000001</targetListIds>
        <targetListIds>100000002</targetListIds>
        <adGroupIds>3</adGroupIds>
        <adGroupIds>4</adGroupIds>
        <excludedType>INCLUDED</excludedType>
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

| field | data | description |
|---|---|---|
| rval | [AdGroupRetargetingListPage](../data/AdGroupRetargetingList/AdGroupRetargetingListPage.md) | The acquired target list deliver related entry.|

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>AdGroupRetargetingList</ns2:service>
      <ns2:requestTime>1547793058106</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/AdGroupRetargetingList">
      <ns2:rval>
        <totalNumEntries>4</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupRetargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:campaignId>1</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>3</ns2:adGroupId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:criterionTargetList>
              <ns2:targetListId>100000001</ns2:targetListId>
              <ns2:targetListName>test1</ns2:targetListName>
              <ns2:retargetingTrackId>0</ns2:retargetingTrackId>
            </ns2:criterionTargetList>
            <ns2:excludedType>INCLUDED</ns2:excludedType>
            <ns2:bidMultiplier>1.0</ns2:bidMultiplier>
          </ns2:adGroupRetargetingList>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
Create the target list setting in ad group level.。

#### Request
| name | req? | type | description |
|---|---|---|---|
| operations | Req | [AdGroupRetargetingListOperation](../data/AdGroupRetargetingList/AdGroupRetargetingListOperation.md) | Target list deliver information relate to the operations to apply. |

##### Request

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/AdGroupRetargetingList">
      <operations>
        <operator>ADD</operator>
        <accountId>1111111</accountId>
        <operand>
          <campaignId>22222</campaignId>
          <adGroupId>33333</adGroupId>
          <criterionTargetList>
            <targetListId>44444</targetListId>
          </criterionTargetList>
          <excludedType>INCLUDED</excludedType>
          <bidMultiplier>1.5</bidMultiplier>
        </operand>
        <operand>
          <campaignId>55555</campaignId>
          <adGroupId>66666</adGroupId>
          <criterionTargetList>
            <targetListId>7777</targetListId>
          </criterionTargetList>
          <excludedType>EXCLUDED</excludedType>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response

| field | data | description |
|---|---|---|
| rval | [AdGroupRetargetingListReturnValue](../data/AdGroupRetargetingList/AdGroupRetargetingListReturnValue.md) |Container for target list deliver information including operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>AdGroupRetargetingList</ns2:service>
      <ns2:requestTime>1547793058155</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/AdGroupRetargetingList">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupRetargetingListReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupRetargetingList>
            <ns2:accountId>1111111</ns2:accountId>
            <ns2:campaignId>22222</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>33333</ns2:adGroupId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:criterionTargetList>
              <ns2:targetListId>44444</ns2:targetListId>
              <ns2:targetListName>test1</ns2:targetListName>
              <ns2:retargetingTrackId>0</ns2:retargetingTrackId>
            </ns2:criterionTargetList>
            <ns2:excludedType>INCLUDED</ns2:excludedType>
            <ns2:bidMultiplier>1.5</ns2:bidMultiplier>
          </ns2:adGroupRetargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupRetargetingList>
            <ns2:accountId>1111111</ns2:accountId>
            <ns2:campaignId>55555</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>66666</ns2:adGroupId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:criterionTargetList>
              <ns2:targetListId>7777</ns2:targetListId>
              <ns2:targetListName>test2</ns2:targetListName>
              <ns2:retargetingTrackId>0</ns2:retargetingTrackId>
            </ns2:criterionTargetList>
            <ns2:excludedType>EXCLUDED</ns2:excludedType>
          </ns2:adGroupRetargetingList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
Update the target list setting in ad group level.

#### Request

| name | req? | type | description |
|---|---|---|---|
| operations | Req | [AdGroupRetargetingListOperation](../data/AdGroupRetargetingList/AdGroupRetargetingListOperation.md) | Target list deliver information relate to the operations to apply. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/AdGroupRetargetingList">
      <operations>
        <operator>SET</operator>
        <accountId>1111111</accountId>
        <operand>
          <campaignId>22222</campaignId>
          <adGroupId>55555</adGroupId>
          <criterionTargetList>
            <targetListId>3333</targetListId>
          </criterionTargetList>
          <excludedType>INCLUDED</excludedType>
          <bidMultiplier>1.5</bidMultiplier>
        </operand>
        <operand>
          <campaignId>3333</campaignId>
          <adGroupId>6666</adGroupId>
          <criterionTargetList>
            <targetListId>4444</targetListId>
          </criterionTargetList>
          <excludedType>EXCLUDED</excludedType>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response

| field | data | description |
|---|---|---|
| rval | [AdGroupRetargetingListReturnValue](../data/AdGroupRetargetingList/AdGroupRetargetingListReturnValue.md) | Container for target list deliver information including operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>AdGroupRetargetingList</ns2:service>
      <ns2:requestTime>1547793058183</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/AdGroupRetargetingList">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupRetargetingListReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupRetargetingList>
            <ns2:accountId>1111111</ns2:accountId>
            <ns2:campaignId>22222</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>55555</ns2:adGroupId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:criterionTargetList>
              <ns2:targetListId>3333</ns2:targetListId>
              <ns2:targetListName>test1</ns2:targetListName>
              <ns2:retargetingTrackId>0</ns2:retargetingTrackId>
            </ns2:criterionTargetList>
            <ns2:excludedType>INCLUDED</ns2:excludedType>
            <ns2:bidMultiplier>1.5</ns2:bidMultiplier>
          </ns2:adGroupRetargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupRetargetingList>
            <ns2:accountId>1111111</ns2:accountId>
            <ns2:campaignId>22222</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>66666</ns2:adGroupId>
            <ns2:adGroupName>sample adGroup</ns2:adGroupName>
            <ns2:criterionTargetList>
              <ns2:targetListId>4444</ns2:targetListId>
              <ns2:targetListName>test2</ns2:targetListName>
              <ns2:retargetingTrackId>0</ns2:retargetingTrackId>
            </ns2:criterionTargetList>
            <ns2:excludedType>EXCLUDED</ns2:excludedType>
          </ns2:adGroupRetargetingList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
Delete the target list setting in ad group level.

#### Request

| name | req? | type | description |
|---|---|---|---|
| operations | Req | [AdGroupRetargetingListOperation](../data/AdGroupRetargetingList/AdGroupRetargetingListOperation.md) | Target list deliver information relate to the operations to apply. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/AdGroupRetargetingList">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1111111</accountId>
        <operand>
          <campaignId>22222</campaignId>
          <adGroupId>99999</adGroupId>
          <criterionTargetList>
            <targetListId>3333</targetListId>
          </criterionTargetList>
          <excludedType>INCLUDED</excludedType>
        </operand>
        <operand>
          <campaignId>3333</campaignId>
          <adGroupId>8888</adGroupId>
          <criterionTargetList>
            <targetListId>4444</targetListId>
          </criterionTargetList>
          <excludedType>EXCLUDED</excludedType>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response

| field | type | description |
|---|---|---|
| rval | [AdGroupRetargetingListReturnValue](../data/AdGroupRetargetingList/AdGroupRetargetingListReturnValue.md) | Container for target list deliver information including operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>AdGroupRetargetingList</ns2:service>
      <ns2:requestTime>1547793058202</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/AdGroupRetargetingList">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupRetargetingListReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupRetargetingList>
            <ns2:accountId>1111111</ns2:accountId>
            <ns2:campaignId>22222</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>9999</ns2:adGroupId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:criterionTargetList>
              <ns2:targetListId>3333</ns2:targetListId>
              <ns2:targetListName>test1</ns2:targetListName>
              <ns2:retargetingTrackId>0</ns2:retargetingTrackId>
            </ns2:criterionTargetList>
            <ns2:excludedType>INCLUDED</ns2:excludedType>
            <ns2:bidMultiplier>1.5</ns2:bidMultiplier>
          </ns2:adGroupRetargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupRetargetingList>
            <ns2:accountId>1111111</ns2:accountId>
            <ns2:campaignId>22222</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>8888</ns2:adGroupId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:criterionTargetList>
              <ns2:targetListId>4444</ns2:targetListId>
              <ns2:targetListName>test2</ns2:targetListName>
              <ns2:retargetingTrackId>0</ns2:retargetingTrackId>
            </ns2:criterionTargetList>
            <ns2:excludedType>EXCLUDED</ns2:excludedType>
          </ns2:adGroupRetargetingList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
