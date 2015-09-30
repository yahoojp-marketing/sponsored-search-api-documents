# CampaignTargetService
CampaignTargetServiceでは、キャンペーンのターゲティング設定に関する情報の取得および更新を行います。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.2/CampaignTargetService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.2/CampaignTargetService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V5
#### サービス概要
キャンペーンのターゲティング設定に関する情報の取得および更新を行います。<br>
※各種ターゲティングは入札調整率（bidmultiplier）のみ変更可能です。<br>
※ターゲティングごとに利用できる操作が異なります。詳しくは下の表をご覧ください。<br>
※ネットワークターゲティングの場合はmutate(SET)ができません。<br>
　変更する場合は一旦mutate(REMOVE)を行い、その後mutate(ADD)を行う必要があります。

| ターゲット | mutate(ADD) | mutate(SET) | mutate(REMOVE) | 備考 |
|---|---|---|---|---|
| 曜日・時間帯ターゲティング | OK | OK | OK | |
| 地域ターゲティング | OK | OK | OK | |
| デバイスターゲティング | NG | OK | NG | 新規登録および削除は実施できません。<br>キャンペーン新規作成時に自動で登録されるデバイスターゲティング<br>(bidMultiplierは"1"に設定)の変更のみ可能です。 |
| ネットワークターゲティング | OK | NG | OK | bidmultiplierの登録はできません。 |

#### 操作
CampaignTargetServiceで提供される操作を説明します。
## get
キャンペーンのターゲティング設定に関する情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [CampaignTargetSelector](../data/CampaignTargetSelector.md) | 操作の対象とするキャンペーンのターゲティング設定です。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope
 xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V5" 
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:get>
         <ns1:selector>
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:campaignIds>00000003</ns1:campaignIds>
            <ns1:campaignIds>00000004</ns1:campaignIds>
            <ns1:campaignIds>00000005</ns1:campaignIds>
            <ns1:targetIds>JP-0001-0010</ns1:targetIds>
            <ns1:targetIds>011112222</ns1:targetIds>
            <ns1:targetIds>911112222</ns1:targetIds>
            <ns1:targetTypes>SCHEDULE</ns1:targetTypes>
            <ns1:targetTypes>LOCATION</ns1:targetTypes>
            <ns1:targetTypes>PLATFORM</ns1:targetTypes>
            <ns1:targetTypes>NETWORK</ns1:targetTypes>
            <ns1:paging>
               <ns1:startIndex>1</ns1:startIndex>
               <ns1:numberResults>500</ns1:numberResults>
            </ns1:paging>
         </ns1:selector>
      </ns1:get>
   </soapenv:Body>
</soapenv:Envelope>
```
#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [CampaignTargetPage](../data/CampaignTargetPage.md) | 取得されるキャンペーンのターゲティング設定に関するエントリーです。 | 
##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignTargetService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:Page.Type>CampaignTargetPage</ns1:Page.Type>
                <ns1:totalNumEntries>4</ns1:totalNumEntries>
                <ns1:values>
                  <ns1:operationSucceeded>true</ns1:operationSucceeded>
                  <ns1:campaignTarget>
                     <ns1:accountId>00000001</ns1:accountId>
                     <ns1:campaignId>00000003</ns1:campaignId>
                     <ns1:campaignName>Sample2</ns1:campaignName>
                     <ns1:target xsi:type="ns1:LocationTarget">
                     <ns1:targetId>JP-0001-0010</ns1:targetId>
                        <ns1:targetType>LOCATION</ns1:targetType>
                        <ns1:provinceNameJA>東京都</ns1:provinceNameJA>
                        <ns1:provinceNameEN>Tokyo</ns1:provinceNameEN>
                        <ns1:cityNameJA>港区</ns1:cityNameJA>
                        <ns1:cityNameEN>Minatoku</ns1:cityNameEN>
                        <ns1:excludedType>INCLUDED</ns1:excludedType>
                        <ns1:targetingStatus>ACTIVE</ns1:targetingStatus>
                     </ns1:target>
                     <ns1:bidMultiplier>0.95</ns1:bidMultiplier>
                  </ns1:campaignTarget>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000003</ns1:campaignId>
                        <ns1:target xsi:type="ns1:ScheduleTarget">
                           <ns1:targetType>SCHEDULE</ns1:targetType>
                           <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                           <ns1:startHour>21</ns1:startHour>
                           <ns1:startMinute>ZERO</ns1:startMinute>
                           <ns1:endHour>24</ns1:endHour>
                           <ns1:endMinute>ZERO</ns1:endMinute>
                        </ns1:target>
                        <ns1:bidMultiplier>1</ns1:bidMultiplier>
                    </ns1:campaignTarget>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000004</ns1:campaignId>
                        <ns1:target xsi:type="ns1:PlatformTarget">
                            <ns1:targetType>PLATFORM</ns1:targetType>
                            <ns1:platformType>SMART_PHONE</ns1:platformType>
                        </ns1:target>
                        <ns1:bidMultiplier>1</ns1:bidMultiplier>
                    </ns1:campaignTarget>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000005</ns1:campaignId>
                        <ns1:target xsi:type="ns1:NetworkTarget">
                            <ns1:targetType>NETWORK</ns1:targetType>
                            <ns1:networkCoverageType>YAHOO_SEARCH</ns1:networkCoverageType>
                        </ns1:target>
                    </ns1:campaignTarget>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate(ADD)
キャンペーンのターゲティング設定に関する情報を追加します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [CampaignTargetOperation](../data/CampaignTargetOperation.md) | 操作の対象となるキャンペーンのターゲティング設定および操作の内容を表します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope 
xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" 
xmlns:ns1="http://ss.yahooapis.jp/V5" 
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000003</ns1:campaignId>
               <ns1:target xsi:type="ns1:ScheduleTarget">
                  <ns1:targetType>SCHEDULE</ns1:targetType>
                  <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                  <ns1:startHour>21</ns1:startHour>
                  <ns1:startMinute>ZERO</ns1:startMinute>
                  <ns1:endHour>24</ns1:endHour>
                  <ns1:endMinute>ZERO</ns1:endMinute>
               </ns1:target>
               <ns1:bidMultiplier>1</ns1:bidMultiplier>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000003</ns1:campaignId>
               <ns1:target xsi:type="ns1:LocationTarget">
                  <ns1:targetId>JP-0001-0010</ns1:targetId>
                  <ns1:targetType>LOCATION</ns1:targetType>
                  <ns1:excludedType>INCLUDED</ns1:excludedType>
               </ns1:target>
               <ns1:bidMultiplier>1</ns1:bidMultiplier>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000004</ns1:campaignId>
               <ns1:target xsi:type="ns1:PlatformTarget">
                  <ns1:targetType>PLATFORM</ns1:targetType>
                  <ns1:platformType>SMART_PHONE</ns1:platformType>
               </ns1:target>
               <ns1:bidMultiplier>1</ns1:bidMultiplier>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000005</ns1:campaignId>
               <ns1:target xsi:type="ns1:NetworkTarget">
                  <ns1:targetType>NETWORK</ns1:targetType>
                  <ns1:networkCoverageType>YAHOO_SEARCH</ns1:networkCoverageType>
               </ns1:target>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```
#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [CampaignTargetReturnValue](../data/CampaignTargetReturnValue.md) | 操作結果を含むキャンペーンのターゲット設定に関する情報のコンテナです。 | 
##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignTargetService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignTargetReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
               <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000003</ns1:campaignId>
                        <ns1:campaignName>Sample</ns1:campaignName>
                        <ns1:target xsi:type="ns1:ScheduleTarget">
                           <ns1:targetId>011112222</ns1:targetId>
                           <ns1:targetType>SCHEDULE</ns1:targetType>
                           <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                           <ns1:startHour>21</ns1:startHour>
                           <ns1:startMinute>ZERO</ns1:startMinute>
                           <ns1:endHour>24</ns1:endHour>
                           <ns1:endMinute>ZERO</ns1:endMinute>
                        </ns1:target>
                        <ns1:bidMultiplier>1</ns1:bidMultiplier>
                    </ns1:campaignTarget>
                </ns1:values>
                 <ns1:values>
                  <ns1:operationSucceeded>true</ns1:operationSucceeded>
                  <ns1:campaignTarget>
                     <ns1:accountId>00000001</ns1:accountId>
                     <ns1:campaignId>00000003</ns1:campaignId>
                     <ns1:campaignName>Sample2</ns1:campaignName>
                     <ns1:target xsi:type="ns1:LocationTarget">
                     <ns1:targetId>JP-0001-0010</ns1:targetId>
                        <ns1:targetType>LOCATION</ns1:targetType>
                        <ns1:provinceNameJA>東京都</ns1:provinceNameJA>
                        <ns1:provinceNameEN>Tokyo</ns1:provinceNameEN>
                        <ns1:cityNameJA>港区</ns1:cityNameJA>
                        <ns1:cityNameEN>Minatoku</ns1:cityNameEN>
                        <ns1:excludedType>INCLUDED</ns1:excludedType>
                        <ns1:targetingStatus>ACTIVE</ns1:targetingStatus>
                     </ns1:target>
                     <ns1:bidMultiplier>0.95</ns1:bidMultiplier>
                  </ns1:campaignTarget>
                </ns1:values>                
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000004</ns1:campaignId>
                        <ns1:campaignName>Sample</ns1:campaignName>
                        <ns1:target xsi:type="ns1:NetworkTarget">
                            <ns1:targetId>00000010</ns1:targetId>
                            <ns1:targetType>NETWORK</ns1:targetType>
                            <ns1:networkCoverageType>YAHOO_SEARCH</ns1:networkCoverageType>
                        </ns1:target>
                    </ns1:campaignTarget>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate(SET)

キャンペーンのターゲティング設定に関する情報を変更します。<br>
※入札調整率（bidmultiplier）のみ変更可能です。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [CampaignTargetOperation](../data/CampaignTargetOperation.md) | 操作の対象とするキャンペーンのターゲティング設定です。 | 
##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope 
 xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V5" 
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000006</ns1:campaignId>
               <ns1:target xsi:type="ns1:ScheduleTarget">
                  <ns1:targetId>011112222</ns1:targetId>
                  <ns1:targetType>SCHEDULE</ns1:targetType>
               </ns1:target>
               <ns1:bidMultiplier>1.5</ns1:bidMultiplier>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000006</ns1:campaignId>
               <ns1:target xsi:type="ns1:LocationTarget">
                  <ns1:targetId>JP-0001-0010</ns1:targetId>
                  <ns1:targetType>LOCATION</ns1:targetType>
               </ns1:target>
               <ns1:bidMultiplier>0.95</ns1:bidMultiplier>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000006</ns1:campaignId>
               <ns1:target xsi:type="ns1:PlatformTarget">
                  <ns1:targetId>0124534</ns1:targetId>
                  <ns1:targetType>PLATFORM</ns1:targetType>
               </ns1:target>
               <ns1:bidMultiplier>3</ns1:bidMultiplier>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```
#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [CampaignTargetReturnValue](../data/CampaignTargetReturnValue.md) | 取得されるキャンペーンのターゲティング設定に関するエントリーです。 | 
##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignTargetService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignTargetReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
               <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000003</ns1:campaignId>
                        <ns1:campaignName>Sample</ns1:campaignName>
                        <ns1:target xsi:type="ns1:ScheduleTarget">
                           <ns1:targetId>00000011</ns1:targetId>
                           <ns1:targetType>SCHEDULE</ns1:targetType>
                           <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                           <ns1:startHour>21</ns1:startHour>
                           <ns1:startMinute>ZERO</ns1:startMinute>
                           <ns1:endHour>24</ns1:endHour>
                           <ns1:endMinute>ZERO</ns1:endMinute>
                        </ns1:target>
                        <ns1:bidMultiplier>1</ns1:bidMultiplier>
                    </ns1:campaignTarget>
                </ns1:values>
                 <ns1:values>
                  <ns1:operationSucceeded>true</ns1:operationSucceeded>
                  <ns1:campaignTarget>
                     <ns1:accountId>00000001</ns1:accountId>
                     <ns1:campaignId>00000003</ns1:campaignId>
                     <ns1:campaignName>Sample2</ns1:campaignName>
                     <ns1:target xsi:type="ns1:LocationTarget">
                     <ns1:targetId>JP-0001-0010</ns1:targetId>
                        <ns1:targetType>LOCATION</ns1:targetType>
                        <ns1:provinceNameJA>東京都</ns1:provinceNameJA>
                        <ns1:provinceNameEN>Tokyo</ns1:provinceNameEN>
                        <ns1:cityNameJA>港区</ns1:cityNameJA>
                        <ns1:cityNameEN>Minatoku</ns1:cityNameEN>
                        <ns1:excludedType>INCLUDED</ns1:excludedType>
                        <ns1:targetingStatus>ACTIVE</ns1:targetingStatus>
                     </ns1:target>
                     <ns1:bidMultiplier>0.95</ns1:bidMultiplier>
                  </ns1:campaignTarget>
                </ns1:values>                
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>14201</ns1:accountId>
                        <ns1:campaignId>7262</ns1:campaignId>
                        <ns1:campaignName>Sample</ns1:campaignName>
                        <ns1:target xsi:type="ns1:NetworkTarget">
                            <ns1:targetId>00000012</ns1:targetId>
                            <ns1:targetType>NETWORK</ns1:targetType>
                            <ns1:networkCoverageType>YAHOO_SEARCH</ns1:networkCoverageType>
                        </ns1:target>
                    </ns1:campaignTarget>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate(REMOVE)
キャンペーンのターゲティング設定に関する情報を削除します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [CampaignTargetOperation](../data/CampaignTargetOperation.md) | 操作の対象とするキャンペーンのターゲティング設定です。 | 
##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope 
 xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V5" 
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>REMOVE</ns1:operator>
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000003</ns1:campaignId>
               <ns1:target xsi:type="ns1:ScheduleTarget">
                  <ns1:targetId>011112222</ns1:targetId>
                  <ns1:targetType>SCHEDULE</ns1:targetType>
               </ns1:target>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000003</ns1:campaignId>
               <ns1:target xsi:type="ns1:LocationTarget">
                  <ns1:targetId>JP-0001-0010</ns1:targetId>
                  <ns1:targetType>LOCATION</ns1:targetType>
               </ns1:target>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000004</ns1:campaignId>
               <ns1:target xsi:type="ns1:NetworkTarget">
                  <ns1:targetId>811112222</ns1:targetId>
                  <ns1:targetType>NETWORK</ns1:targetType>
               </ns1:target>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```
#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [CampaignTargetReturnValue](../data/CampaignTargetReturnValue.md) | 取得されるキャンペーンのターゲティング設定に関するエントリーです。 | 
##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignTargetService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignTargetReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
               <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000003</ns1:campaignId>
                        <ns1:campaignName>Sample</ns1:campaignName>
                        <ns1:target xsi:type="ns1:ScheduleTarget">
                           <ns1:targetId>00000010</ns1:targetId>
                           <ns1:targetType>SCHEDULE</ns1:targetType>
                           <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                           <ns1:startHour>21</ns1:startHour>
                           <ns1:startMinute>ZERO</ns1:startMinute>
                           <ns1:endHour>24</ns1:endHour>
                           <ns1:endMinute>ZERO</ns1:endMinute>
                        </ns1:target>
                        <ns1:bidMultiplier>1</ns1:bidMultiplier>
                    </ns1:campaignTarget>
                </ns1:values>
                 <ns1:values>
                  <ns1:operationSucceeded>true</ns1:operationSucceeded>
                  <ns1:campaignTarget>
                     <ns1:accountId>00000001</ns1:accountId>
                     <ns1:campaignId>00000003</ns1:campaignId>
                     <ns1:campaignName>Sample2</ns1:campaignName>
                     <ns1:target xsi:type="ns1:LocationTarget">
                     <ns1:targetId>JP-0001-0010</ns1:targetId>
                        <ns1:targetType>LOCATION</ns1:targetType>
                        <ns1:provinceNameJA>東京都</ns1:provinceNameJA>
                        <ns1:provinceNameEN>Tokyo</ns1:provinceNameEN>
                        <ns1:cityNameJA>港区</ns1:cityNameJA>
                        <ns1:cityNameEN>Minatoku</ns1:cityNameEN>
                        <ns1:excludedType>INCLUDED</ns1:excludedType>
                        <ns1:targetingStatus>ACTIVE</ns1:targetingStatus>
                     </ns1:target>
                     <ns1:bidMultiplier>0.95</ns1:bidMultiplier>
                  </ns1:campaignTarget>
                </ns1:values>                
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000004</ns1:campaignId>
                        <ns1:campaignName>Sample</ns1:campaignName>
                        <ns1:target xsi:type="ns1:NetworkTarget">
                            <ns1:targetId>00000011</ns1:targetId>
                            <ns1:targetType>NETWORK</ns1:targetType>
                            <ns1:networkCoverageType>YAHOO_SEARCH</ns1:networkCoverageType>
                        </ns1:target>
                    </ns1:campaignTarget>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
