# CampaignTargetService
CampaignTargetService is to get or update target setting information.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201805/CampaignTargetService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201805/CampaignTargetService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201805/CampaignTarget
#### Overview
Get, add, update or delete campaign informations related to targeting setting.<br>
* Bid Adjustment (bidmultiplier) is only modifiable for each targeting.<br>
* The available operations vary depending on the target. Please refer to the chart below for details.<br>
* Cannot mutate(SET) for Network Targeting. For the change, delete first using mutate(REMOVE), then create the new target using mutate(ADD).

| Target | mutate(ADD) | mutate(SET) | mutate(REMOVE) | Notes |
|---|---|---|---|---|
| Day of Week / Hours targeting | OK | OK | OK | |
| Geo targeting | OK | OK | OK | |
| Device targeting | NG | OK | NG | New registration and deletion of Device Targeting is not available.<br>Device Targeting which is automatically registered at the time of campaign new creation is only modifiable (bidMultiplier will be set “1”). |
| Network targeting | OK | NG | OK | Registration of "bidmultiplier" is not available. |

#### Operation
Describes the operation which provides at CampaignTargetService.

+ [get](#get)
+ [mutate(ADD)](#mutate-add)
+ [mutate(SET)](#mutate-set)
+ [mutate(REMOVE)](#mutate-remove)

#### Object
[CampaignTarget](../data/CampaignTarget)

## get

### Request
Gets campaign informations related to targeting setting.

| Field | Restrictions | Data Type | Description |
|---|---|---|---|
| selector | Req | [CampaignTargetSelector](../data/CampaignTarget/CampaignTargetSelector.md) | Operation elements for targeting setting of campaign. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201805/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <selector>
        <accountId>1234567890</accountId>
        <campaignIds>10001</campaignIds>
        <campaignIds>10002</campaignIds>
        <campaignIds>10003</campaignIds>
        <campaignIds>10004</campaignIds>
        <campaignIds>10005</campaignIds>
        <targetIds>20001</targetIds>
        <targetIds>20002</targetIds>
        <targetIds>20003</targetIds>
        <targetIds>20004</targetIds>
        <targetIds>20005</targetIds>
        <targetIds>JP-01-0010</targetIds>
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
Response Field

| Parameter | Data Type | Description |
|---|---|---|
| rval | [CampaignTargetPage](../data/CampaignTarget/CampaignTargetPage.md) | Page of lists of the requested campaign targets. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>CampaignTarget</ns2:service>
      <ns2:requestTime>1523506332854</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/CampaignTarget">
      <ns2:rval>
        <totalNumEntries>6</totalNumEntries>
        <Page.Type>CampaignTargetPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ScheduleTarget">
              <ns2:targetId>20001</ns2:targetId>
              <ns2:targetType>SCHEDULE</ns2:targetType>
              <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
              <ns2:startHour>10</ns2:startHour>
              <ns2:startMinute>ZERO</ns2:startMinute>
              <ns2:endHour>19</ns2:endHour>
              <ns2:endMinute>ZERO</ns2:endMinute>
            </ns2:target>
            <ns2:bidMultiplier>5.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:LocationTarget">
              <ns2:targetId>JP-01-0010</ns2:targetId>
              <ns2:targetType>LOCATION</ns2:targetType>
              <ns2:provinceNameJA>北海道</ns2:provinceNameJA>
              <ns2:provinceNameEN>Hokkaido</ns2:provinceNameEN>
              <ns2:cityNameJA>伊達市</ns2:cityNameJA>
              <ns2:cityNameEN>Date</ns2:cityNameEN>
              <ns2:excludedType>INCLUDED</ns2:excludedType>
              <ns2:targetingStatus>ACTIVE</ns2:targetingStatus>
            </ns2:target>
            <ns2:bidMultiplier>5.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:NetworkTarget">
              <ns2:targetId>20002</ns2:targetId>
              <ns2:targetType>NETWORK</ns2:targetType>
              <ns2:networkCoverageType>YAHOO_SEARCH</ns2:networkCoverageType>
            </ns2:target>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PlatformTarget">
              <ns2:targetId>20003</ns2:targetId>
              <ns2:targetType>PLATFORM</ns2:targetType>
              <ns2:platformType>SMART_PHONE</ns2:platformType>
            </ns2:target>
            <ns2:bidMultiplier>1.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PlatformTarget">
              <ns2:targetId>20004</ns2:targetId>
              <ns2:targetType>PLATFORM</ns2:targetType>
              <ns2:platformType>TABLET</ns2:platformType>
            </ns2:target>
            <ns2:bidMultiplier>1.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PlatformTarget">
              <ns2:targetId>20005</ns2:targetId>
              <ns2:targetType>PLATFORM</ns2:targetType>
              <ns2:platformType>DESKTOP</ns2:platformType>
            </ns2:target>
            <ns2:bidMultiplier>1.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (ADD)

### Request
Adds campaign informations related to targeting setting.

| Field | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [CampaignTargetOperation](../data/CampaignTarget/CampaignTargetOperation.md) | Operation elements for targeting setting of campaign |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/CampaignTarget">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ScheduleTarget">
            <targetType>SCHEDULE</targetType>
            <dayOfWeek>FRIDAY</dayOfWeek>
            <startHour>10</startHour>
            <startMinute>ZERO</startMinute>
            <endHour>19</endHour>
            <endMinute>ZERO</endMinute>
          </target>
          <bidMultiplier>5.0</bidMultiplier>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="LocationTarget">
            <targetId>JP-01-0010</targetId>
            <targetType>LOCATION</targetType>
            <excludedType>INCLUDED</excludedType>
          </target>
          <bidMultiplier>5.0</bidMultiplier>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="NetworkTarget">
            <targetType>NETWORK</targetType>
            <networkCoverageType>YAHOO_SEARCH</networkCoverageType>
          </target>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Field | Requirement | Data Type |
|---|---|---|
| rval | [CampaignTargetReturnValue](../data/CampaignTarget/CampaignTargetReturnValue.md) | Page of lists of the requested campaign targets. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>CampaignTarget</ns2:service>
      <ns2:requestTime>1523506332876</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/CampaignTarget">
      <ns2:rval>
        <ListReturnValue.Type>CampaignTargetReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ScheduleTarget">
              <ns2:targetId>20001</ns2:targetId>
              <ns2:targetType>SCHEDULE</ns2:targetType>
              <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
              <ns2:startHour>10</ns2:startHour>
              <ns2:startMinute>ZERO</ns2:startMinute>
              <ns2:endHour>19</ns2:endHour>
              <ns2:endMinute>ZERO</ns2:endMinute>
            </ns2:target>
            <ns2:bidMultiplier>5.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:LocationTarget">
              <ns2:targetId>JP-01-0010</ns2:targetId>
              <ns2:targetType>LOCATION</ns2:targetType>
              <ns2:provinceNameJA>北海道</ns2:provinceNameJA>
              <ns2:provinceNameEN>Hokkaido</ns2:provinceNameEN>
              <ns2:cityNameJA>伊達市</ns2:cityNameJA>
              <ns2:cityNameEN>Date</ns2:cityNameEN>
              <ns2:excludedType>INCLUDED</ns2:excludedType>
              <ns2:targetingStatus>ACTIVE</ns2:targetingStatus>
            </ns2:target>
            <ns2:bidMultiplier>5.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:NetworkTarget">
              <ns2:targetId>20002</ns2:targetId>
              <ns2:targetType>NETWORK</ns2:targetType>
              <ns2:networkCoverageType>YAHOO_SEARCH</ns2:networkCoverageType>
            </ns2:target>
          </ns2:campaignTarget>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (SET)

### Request
Update campaign informations related to targeting setting.
* Bid Adjustment (bidmultiplier) is only modifiable.

| Field | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [CampaignTargetOperation](../data/CampaignTarget/CampaignTargetOperation.md) | Operation elements for targeting setting of campaign. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/CampaignTarget">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ScheduleTarget">
            <targetId>20001</targetId>
            <targetType>SCHEDULE</targetType>
          </target>
          <bidMultiplier>10.0</bidMultiplier>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="LocationTarget">
            <targetId>JP-01-0010</targetId>
            <targetType>LOCATION</targetType>
          </target>
          <bidMultiplier>10.0</bidMultiplier>
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
| rval | [CampaignTargetReturnValue](../data/CampaignTarget/CampaignTargetReturnValue.md) | Page of lists of the requested campaign targets. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>CampaignTarget</ns2:service>
      <ns2:requestTime>1523506332894</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/CampaignTarget">
      <ns2:rval>
        <ListReturnValue.Type>CampaignTargetReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ScheduleTarget">
              <ns2:targetId>20001</ns2:targetId>
              <ns2:targetType>SCHEDULE</ns2:targetType>
              <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
              <ns2:startHour>10</ns2:startHour>
              <ns2:startMinute>ZERO</ns2:startMinute>
              <ns2:endHour>19</ns2:endHour>
              <ns2:endMinute>ZERO</ns2:endMinute>
            </ns2:target>
            <ns2:bidMultiplier>10.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:LocationTarget">
              <ns2:targetId>JP-01-0010</ns2:targetId>
              <ns2:targetType>LOCATION</ns2:targetType>
              <ns2:provinceNameJA>北海道</ns2:provinceNameJA>
              <ns2:provinceNameEN>Hokkaido</ns2:provinceNameEN>
              <ns2:cityNameJA>伊達市</ns2:cityNameJA>
              <ns2:cityNameEN>Date</ns2:cityNameEN>
              <ns2:excludedType>INCLUDED</ns2:excludedType>
              <ns2:targetingStatus>ACTIVE</ns2:targetingStatus>
            </ns2:target>
            <ns2:bidMultiplier>10.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (REMOVE)

### Request
Delete campaign informations related to targeting setting.

| Field | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [CampaignTargetOperation](../data/CampaignTarget/CampaignTargetOperation.md) | Operation elements for targeting setting of campaign. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/CampaignTarget">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ScheduleTarget">
            <targetId>20001</targetId>
            <targetType>SCHEDULE</targetType>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="LocationTarget">
            <targetId>JP-01-0010</targetId>
            <targetType>LOCATION</targetType>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="LocationTarget">
            <targetId>JP-01-0010</targetId>
            <targetType>LOCATION</targetType>
          </target>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
##### Response Fields

| Field | Requirement | Data Type |
|---|---|---|
| rval | [CampaignTargetReturnValue](../data/CampaignTarget/CampaignTargetReturnValue.md) | Page of lists of the requested campaign targets. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>CampaignTarget</ns2:service>
      <ns2:requestTime>1523506332920</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/CampaignTarget">
      <ns2:rval>
        <ListReturnValue.Type>CampaignTargetReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ScheduleTarget">
              <ns2:targetId>20001</ns2:targetId>
              <ns2:targetType>SCHEDULE</ns2:targetType>
              <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
              <ns2:startHour>10</ns2:startHour>
              <ns2:startMinute>ZERO</ns2:startMinute>
              <ns2:endHour>19</ns2:endHour>
              <ns2:endMinute>ZERO</ns2:endMinute>
            </ns2:target>
            <ns2:bidMultiplier>5.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:LocationTarget">
              <ns2:targetId>JP-01-0010</ns2:targetId>
              <ns2:targetType>LOCATION</ns2:targetType>
              <ns2:provinceNameJA>北海道</ns2:provinceNameJA>
              <ns2:provinceNameEN>Hokkaido</ns2:provinceNameEN>
              <ns2:cityNameJA>伊達市</ns2:cityNameJA>
              <ns2:cityNameEN>Date</ns2:cityNameEN>
              <ns2:excludedType>INCLUDED</ns2:excludedType>
              <ns2:targetingStatus>ACTIVE</ns2:targetingStatus>
            </ns2:target>
            <ns2:bidMultiplier>5.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:NetworkTarget">
              <ns2:targetId>20002</ns2:targetId>
              <ns2:targetType>NETWORK</ns2:targetType>
              <ns2:networkCoverageType>YAHOO_SEARCH</ns2:networkCoverageType>
            </ns2:target>
          </ns2:campaignTarget>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
