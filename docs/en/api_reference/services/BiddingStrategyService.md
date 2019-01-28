# BiddingStrategyService
Use this service to get, add, update, or delete auto bidding information.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201901/BiddingStrategyService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201901/BiddingStrategyService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201901/BiddingStrategy
#### Overview
Use this service to create, update and remove auto bidding information.
#### Operation
Describe the operation which provides at BiddingStrategyService.

+ [get](#get)
+ [mutate(ADD)](#mutate-add)
+ [mutate(SET)](#mutate-set)
+ [mutate(REMOVE)](#mutate-remove)

#### Object
[BiddingStrategy](../data/BiddingStrategy)

## get
Returns auto bidding information.

### Request
| Field | Restrictions | Data Type | Description |
|---|---|---|---|
| selector | Req | [BiddingStrategySelector](../data/BiddingStrategy/BiddingStrategySelector.md) | This object is a container for auto bidding information. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201901/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <selector>
        <accountId>1234567890</accountId>
        <biddingStrategyIds>20001</biddingStrategyIds>
        <biddingStrategyIds>20002</biddingStrategyIds>
        <biddingStrategyIds>20003</biddingStrategyIds>
        <biddingStrategyIds>20004</biddingStrategyIds>
        <biddingStrategyIds>20005</biddingStrategyIds>
        <biddingStrategyTypes>PAGE_ONE_PROMOTED</biddingStrategyTypes>
        <biddingStrategyTypes>TARGET_CPA</biddingStrategyTypes>
        <biddingStrategyTypes>TARGET_SPEND</biddingStrategyTypes>
        <biddingStrategyTypes>TARGET_ROAS</biddingStrategyTypes>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>1000</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description |
|---|---|---|
| rval | [BiddingStrategyPage](../data/BiddingStrategy/BiddingStrategyPage.md) | Entry of acquired ad group. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>BiddingStrategy</ns2:service>
      <ns2:requestTime>1547792998941</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/BiddingStrategy">
      <ns2:rval>
        <totalNumEntries>5</totalNumEntries>
        <Page.Type>BiddingStrategyPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20002</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>PageOnePromotedBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>PAGE_ONE_PROMOTED</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PageOnePromotedBiddingScheme">
              <ns2:biddingStrategyType>PAGE_ONE_PROMOTED</ns2:biddingStrategyType>
              <ns2:targetPositionType>PAGE_ONE</ns2:targetPositionType>
              <ns2:bidCeiling>1</ns2:bidCeiling>
              <ns2:bidMultiplier>0.1</ns2:bidMultiplier>
              <ns2:bidChangesForRaisesOnly>ACTIVE</ns2:bidChangesForRaisesOnly>
              <ns2:raiseBidWhenBudgetConstrained>ACTIVE</ns2:raiseBidWhenBudgetConstrained>
              <ns2:raiseBidWhenLowQualityScore>ACTIVE</ns2:raiseBidWhenLowQualityScore>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20003</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetCpaBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_CPA</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetCpaBiddingScheme">
              <ns2:biddingStrategyType>TARGET_CPA</ns2:biddingStrategyType>
              <ns2:targetCpa>99999999</ns2:targetCpa>
              <ns2:bidCeiling>500</ns2:bidCeiling>
              <ns2:bidFloor>1</ns2:bidFloor>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20004</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetSpendBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetSpendBiddingScheme">
              <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
              <ns2:bidCeiling>1</ns2:bidCeiling>
              <ns2:spendTarget>100</ns2:spendTarget>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20005</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetRoasBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_ROAS</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetRoasBiddingScheme">
              <ns2:biddingStrategyType>TARGET_ROAS</ns2:biddingStrategyType>
              <ns2:targetRoas>1000.0</ns2:targetRoas>
              <ns2:bidCeiling>5000</ns2:bidCeiling>
              <ns2:bidFloor>10</ns2:bidFloor>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (ADD)
Creates the Auto bidding.

### Request
| Field | Req | Data Type | Description |
|---|---|---|---|
| operations | ○ | [BiddingStrategyOperation](../data/BiddingStrategy/BiddingStrategyOperation.md) | Create the auto bidding settings. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/BiddingStrategy">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <biddingStrategyName>PageOnePromotedBiddingScheme</biddingStrategyName>
          <biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="PageOnePromotedBiddingScheme">
            <biddingStrategyType>PAGE_ONE_PROMOTED</biddingStrategyType>
            <targetPositionType>PAGE_ONE</targetPositionType>
            <bidCeiling>1</bidCeiling>
            <bidMultiplier>0.1</bidMultiplier>
            <bidChangesForRaisesOnly>ACTIVE</bidChangesForRaisesOnly>
            <raiseBidWhenBudgetConstrained>ACTIVE</raiseBidWhenBudgetConstrained>
            <raiseBidWhenLowQualityScore>ACTIVE</raiseBidWhenLowQualityScore>
          </biddingScheme>
        </operand>
        <operand>
          <biddingStrategyName>TargetCpaBiddingScheme</biddingStrategyName>
          <biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetCpaBiddingScheme">
            <biddingStrategyType>TARGET_CPA</biddingStrategyType>
            <targetCpa>99999999</targetCpa>
            <bidCeiling>500</bidCeiling>
            <bidFloor>1</bidFloor>
          </biddingScheme>
        </operand>
        <operand>
          <biddingStrategyName>TargetSpendBiddingScheme</biddingStrategyName>
          <biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetSpendBiddingScheme">
            <biddingStrategyType>TARGET_SPEND</biddingStrategyType>
            <bidCeiling>1</bidCeiling>
            <spendTarget>100</spendTarget>
          </biddingScheme>
        </operand>
        <operand>
          <biddingStrategyName>TargetRoasBiddingScheme</biddingStrategyName>
          <biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetRoasBiddingScheme">
            <biddingStrategyType>TARGET_ROAS</biddingStrategyType>
            <targetRoas>1000.0</targetRoas>
            <bidCeiling>5000</bidCeiling>
            <bidFloor>10</bidFloor>
          </biddingScheme>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Field

| Field | Data Type | Description |
|---|---|---|
| rval | [BiddingStrategyReturnValue](../data/BiddingStrategy/BiddingStrategyReturnValue.md) | This object is a container for Auto bidding which includes operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>BiddingStrategy</ns2:service>
      <ns2:requestTime>1547792999053</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/BiddingStrategy">
      <ns2:rval>
        <ListReturnValue.Type>BiddingStrategyReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20002</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>PageOnePromotedBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>PAGE_ONE_PROMOTED</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PageOnePromotedBiddingScheme">
              <ns2:biddingStrategyType>PAGE_ONE_PROMOTED</ns2:biddingStrategyType>
              <ns2:targetPositionType>PAGE_ONE</ns2:targetPositionType>
              <ns2:bidCeiling>1</ns2:bidCeiling>
              <ns2:bidMultiplier>0.1</ns2:bidMultiplier>
              <ns2:bidChangesForRaisesOnly>ACTIVE</ns2:bidChangesForRaisesOnly>
              <ns2:raiseBidWhenBudgetConstrained>ACTIVE</ns2:raiseBidWhenBudgetConstrained>
              <ns2:raiseBidWhenLowQualityScore>ACTIVE</ns2:raiseBidWhenLowQualityScore>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20003</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetCpaBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_CPA</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetCpaBiddingScheme">
              <ns2:biddingStrategyType>TARGET_CPA</ns2:biddingStrategyType>
              <ns2:targetCpa>99999999</ns2:targetCpa>
              <ns2:bidCeiling>500</ns2:bidCeiling>
              <ns2:bidFloor>1</ns2:bidFloor>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20004</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetSpendBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetSpendBiddingScheme">
              <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
              <ns2:bidCeiling>1</ns2:bidCeiling>
              <ns2:spendTarget>100</ns2:spendTarget>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20005</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetRoasBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_ROAS</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetRoasBiddingScheme">
              <ns2:biddingStrategyType>TARGET_ROAS</ns2:biddingStrategyType>
              <ns2:targetRoas>1000.0</ns2:targetRoas>
              <ns2:bidCeiling>5000</ns2:bidCeiling>
              <ns2:bidFloor>10</ns2:bidFloor>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (SET)
Updates an auto bidding.

### Request
| Field | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [BiddingStrategyOperation](../data/BiddingStrategy/BiddingStrategyOperation.md) | Updates auto bidding information |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/BiddingStrategy">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <biddingStrategyId>20002</biddingStrategyId>
          <biddingStrategyName>set PageOnePromotedBiddingScheme</biddingStrategyName>
          <biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="PageOnePromotedBiddingScheme">
            <biddingStrategyType>PAGE_ONE_PROMOTED</biddingStrategyType>
            <targetPositionType>PAGE_ONE_PROMOTED</targetPositionType>
            <bidCeiling>2</bidCeiling>
            <bidMultiplier>0.2</bidMultiplier>
            <bidChangesForRaisesOnly>DEACTIVE</bidChangesForRaisesOnly>
            <raiseBidWhenBudgetConstrained>DEACTIVE</raiseBidWhenBudgetConstrained>
            <raiseBidWhenLowQualityScore>DEACTIVE</raiseBidWhenLowQualityScore>
          </biddingScheme>
        </operand>
        <operand>
          <biddingStrategyId>20003</biddingStrategyId>
          <biddingStrategyName>set TargetCpaBiddingScheme</biddingStrategyName>
          <biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetCpaBiddingScheme">
            <biddingStrategyType>TARGET_CPA</biddingStrategyType>
            <targetCpa>11111111</targetCpa>
            <bidCeiling>100</bidCeiling>
            <bidFloor>10</bidFloor>
          </biddingScheme>
        </operand>
        <operand>
          <biddingStrategyId>20004</biddingStrategyId>
          <biddingStrategyName>set TargetSpendBiddingScheme</biddingStrategyName>
          <biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetSpendBiddingScheme">
            <biddingStrategyType>TARGET_SPEND</biddingStrategyType>
            <bidCeiling>2</bidCeiling>
            <spendTarget>10</spendTarget>
          </biddingScheme>
        </operand>
        <operand>
          <biddingStrategyId>20005</biddingStrategyId>
          <biddingStrategyName>set TargetRoasBiddingScheme</biddingStrategyName>
          <biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetRoasBiddingScheme">
            <biddingStrategyType>TARGET_ROAS</biddingStrategyType>
            <targetRoas>100.0</targetRoas>
            <bidCeiling>3000</bidCeiling>
            <bidFloor>1</bidFloor>
          </biddingScheme>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description |
|---|---|---|
| rval | [BiddingStrategyReturnValue](../data/BiddingStrategy/BiddingStrategyReturnValue.md) | Container includes the information of Auto bidding with operation results.|

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>BiddingStrategy</ns2:service>
      <ns2:requestTime>1547792999092</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/BiddingStrategy">
      <ns2:rval>
        <ListReturnValue.Type>BiddingStrategyReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20002</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>set PageOnePromotedBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>PAGE_ONE_PROMOTED</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PageOnePromotedBiddingScheme">
              <ns2:biddingStrategyType>PAGE_ONE_PROMOTED</ns2:biddingStrategyType>
              <ns2:targetPositionType>PAGE_ONE_PROMOTED</ns2:targetPositionType>
              <ns2:bidCeiling>2</ns2:bidCeiling>
              <ns2:bidMultiplier>0.2</ns2:bidMultiplier>
              <ns2:bidChangesForRaisesOnly>DEACTIVE</ns2:bidChangesForRaisesOnly>
              <ns2:raiseBidWhenBudgetConstrained>DEACTIVE</ns2:raiseBidWhenBudgetConstrained>
              <ns2:raiseBidWhenLowQualityScore>DEACTIVE</ns2:raiseBidWhenLowQualityScore>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20003</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>set TargetCpaBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_CPA</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetCpaBiddingScheme">
              <ns2:biddingStrategyType>TARGET_CPA</ns2:biddingStrategyType>
              <ns2:targetCpa>11111111</ns2:targetCpa>
              <ns2:bidCeiling>100</ns2:bidCeiling>
              <ns2:bidFloor>10</ns2:bidFloor>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20004</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>set TargetSpendBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetSpendBiddingScheme">
              <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
              <ns2:bidCeiling>2</ns2:bidCeiling>
              <ns2:spendTarget>10</ns2:spendTarget>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20005</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>set TargetRoasBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_ROAS</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetRoasBiddingScheme">
              <ns2:biddingStrategyType>TARGET_ROAS</ns2:biddingStrategyType>
              <ns2:targetRoas>100.0</ns2:targetRoas>
              <ns2:bidCeiling>3000</ns2:bidCeiling>
              <ns2:bidFloor>1</ns2:bidFloor>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (REMOVE)
Remove the auto bidding setting.

### Request
| Fieled | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [BiddingStrategyOperation](../data/BiddingStrategy/BiddingStrategyOperation.md) | Removes the auto bidding information. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/BiddingStrategy">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <biddingStrategyId>20001</biddingStrategyId>
        </operand>
        <operand>
          <biddingStrategyId>20002</biddingStrategyId>
        </operand>
        <operand>
          <biddingStrategyId>20003</biddingStrategyId>
        </operand>
        <operand>
          <biddingStrategyId>20004</biddingStrategyId>
        </operand>
        <operand>
          <biddingStrategyId>20005</biddingStrategyId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description |
|---|---|---|
| rval | [BiddingStrategyReturnValue](../data/BiddingStrategy/BiddingStrategyReturnValue.md) | Container includes the information of Auto bidding with operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>BiddingStrategy</ns2:service>
      <ns2:requestTime>1547792999128</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/BiddingStrategy">
      <ns2:rval>
        <ListReturnValue.Type>BiddingStrategyReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20002</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>PageOnePromotedBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>PAGE_ONE_PROMOTED</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PageOnePromotedBiddingScheme">
              <ns2:biddingStrategyType>PAGE_ONE_PROMOTED</ns2:biddingStrategyType>
              <ns2:targetPositionType>PAGE_ONE_PROMOTED</ns2:targetPositionType>
              <ns2:bidCeiling>2</ns2:bidCeiling>
              <ns2:bidMultiplier>0.2</ns2:bidMultiplier>
              <ns2:bidChangesForRaisesOnly>DEACTIVE</ns2:bidChangesForRaisesOnly>
              <ns2:raiseBidWhenBudgetConstrained>DEACTIVE</ns2:raiseBidWhenBudgetConstrained>
              <ns2:raiseBidWhenLowQualityScore>DEACTIVE</ns2:raiseBidWhenLowQualityScore>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20003</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetCpaBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_CPA</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetCpaBiddingScheme">
              <ns2:biddingStrategyType>TARGET_CPA</ns2:biddingStrategyType>
              <ns2:targetCpa>11111111</ns2:targetCpa>
              <ns2:bidCeiling>100</ns2:bidCeiling>
              <ns2:bidFloor>10</ns2:bidFloor>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20004</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetSpendBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetSpendBiddingScheme">
              <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
              <ns2:bidCeiling>2</ns2:bidCeiling>
              <ns2:spendTarget>10</ns2:spendTarget>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20005</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetRoasBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_ROAS</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetRoasBiddingScheme">
              <ns2:biddingStrategyType>TARGET_ROAS</ns2:biddingStrategyType>
              <ns2:targetRoas>100.0</ns2:targetRoas>
              <ns2:bidCeiling>3000</ns2:bidCeiling>
              <ns2:bidFloor>1</ns2:bidFloor>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
