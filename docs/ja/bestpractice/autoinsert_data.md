# アドカスタマイザー機能（データの自動挿入）
## アドカスタマイザーとは
アドカスタマイザーとは、スポンサードサーチの広告文面を動的に変更できる機能です。<br>
広告のタイトルや説明文に任意のテキストを自動挿入できます。また、カウントダウン関数を使って、セール終了までの時間をカウントダウン表示できます。<br>
アドカスタマイザーについて、詳しくは以下のヘルプをご参照ください。<br>
・<a href="https://help.marketing.yahoo.co.jp/ja/?p=11385">アドカスタマイザーについて</a><br>

## スポンサードサーチAPI での実施方法
スポンサードサーチAPIではアドカスタマイザーを利用するために、以下の3つのServiceを使用します。
##### 1.	FeedFolderService
FeedFolderServiceでは、FeedFolder情報の追加・更新・削除が実施できます。<br>
FeedFolder情報とは、広告に挿入するデータを登録したデータ自動挿入リストを格納するコンポーネントです。

##### 2.	FeedItemService
FeedItemServiceでは、FeedFolder情報内の各データ自動挿入リストに、データを追加・更新・削除できます。

##### 3.	AdGroupAdService
AdGroupAdServiceでは、登録したデータを挿入する広告（データ挿入用の関数を使用した広告）を作成できます。

## シナリオ
A社は、販促施策の一環として、スポンサードサーチAPIを使い以下のデータセットを作成します。

##### セール商品リスト
<table class="standard">
                <tr>
                    <th valign="top" >
                        <p>商品 (String)</p>
                    </th>
                    <th valign="top" >
                        <p>価格 (Price)</p>
                    </th>
                    <th valign="top">
                        <p>セール終了日 (Date)</p>
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
                        <p>製品101</p>
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
                        <p>製品102</p>
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
                        <p>製品103</p>
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
※CampaignIdやAdGroupIdIDを設定することで、そのデータ行の利用対象とするキャンペーンや広告グループを指定できます。<br>
指定しない場合は、空白のままにします。

#### 1.	FeedFolderの登録
はじめに、FeedFolderServiceを使い、スポンサードサーチのアカウントにFeedFolder情報を登録します。<br>
ここでは、A社のスポンサードサーチのアカウント（ID:100000001）に、「セール商品リスト」という名前で登録します。

##### リクエストサンプル
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V201805/FeedFolder">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>XXXX-XXXX-XXXX-XXXX</ns1:license>
         <ns1:apiAccountId>XXXX-XXXX-XXXX-XXXX</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
         <ns1:accountId>100000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>XXXXX-XXXX-XXXXX-XXXX</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:feedFolderName>セール商品リスト</ns1:feedFolderName>
               <ns1:feedAttribute>
                  <ns1:feedAttributeName>商品名</ns1:feedAttributeName>
                  <ns1:placeholderField>AD_CUSTOMIZER_STRING</ns1:placeholderField>
               </ns1:feedAttribute>
               <ns1:feedAttribute>
                  <ns1:feedAttributeName>価格</ns1:feedAttributeName>
                  <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
               </ns1:feedAttribute>
               <ns1:feedAttribute>
                  <ns1:feedAttributeName>セール終了日</ns1:feedAttributeName>
                  <ns1:placeholderField>AD_CUSTOMIZER_DATE</ns1:placeholderField>
               </ns1:feedAttribute>
               <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

##### レスポンスサンプル
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V201805/FeedFolder">
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
                  <ns1:feedFolderName>セール商品リスト</ns1:feedFolderName>
                  <ns1:feedAttribute>
                     <ns1:feedAttributeId>1</ns1:feedAttributeId>
                     <ns1:feedAttributeName>商品名</ns1:feedAttributeName>
                     <ns1:placeholderField>AD_CUSTOMIZER_STRING</ns1:placeholderField>
                  </ns1:feedAttribute>
                  <ns1:feedAttribute>
                     <ns1:feedAttributeId>2</ns1:feedAttributeId>
                     <ns1:feedAttributeName>価格</ns1:feedAttributeName>
                     <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                  </ns1:feedAttribute>
                  <ns1:feedAttribute>
                     <ns1:feedAttributeId>3</ns1:feedAttributeId>
                     <ns1:feedAttributeName>セール終了日</ns1:feedAttributeName>
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

#### 2.	FeedItemの登録
次にFeedItemServiceを使い、登録したFeedFolder情報に、広告に挿入・設定するデータを設定します。

##### リクエストサンプル
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V201805/FeedItem">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>XXXX-XXXX-XXXX-XXXX</ns1:license>
         <ns1:apiAccountId>XXXX-XXXX-XXXX-XXXX</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
         <ns1:accountId>100000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>XXXXX-XXXX-XXXXX-XXXX</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:feedFolderId>20001</ns1:feedFolderId>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>AD_CUSTOMIZER_STRING</ns1:placeholderField>
                  <ns1:feedAttributeId>1</ns1:feedAttributeId>
                  <ns1:feedAttributeValue>製品101</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                  <ns1:feedAttributeId>2</ns1:feedAttributeId>
                  <ns1:feedAttributeValue>100</ns1:feedAttributeValue>
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
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:feedFolderId>20001</ns1:feedFolderId>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>AD_CUSTOMIZER_STRING</ns1:placeholderField>
                  <ns1:feedAttributeId>1</ns1:feedAttributeId>
                  <ns1:feedAttributeValue>製品102</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                  <ns1:feedAttributeId>2</ns1:feedAttributeId>
                  <ns1:feedAttributeValue>300</ns1:feedAttributeValue>
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
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:feedFolderId>53161</ns1:feedFolderId>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>AD_CUSTOMIZER_STRING</ns1:placeholderField>
                  <ns1:feedAttributeId>1</ns1:feedAttributeId>
                  <ns1:feedAttributeValue>製品103</ns1:feedAttributeValue>
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
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

##### レスポンスサンプル
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V201805/FeedItem">
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
                     <ns1:feedAttributeValue>製品101</ns1:feedAttributeValue>
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
                     <ns1:feedAttributeValue>製品102</ns1:feedAttributeValue>
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
                     <ns1:feedAttributeValue>製品103</ns1:feedAttributeValue>
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

#### 3.	AdGroupAdの登録
続いて登録したデータを挿入する広告を、AdGroupAdServiceを使用して登録します。<br>
アドカスタマイザーでデータを自動挿入した広告を配信するには、通常の広告も有効にしておく必要があるため、この例では同時に登録を行っています。<br>
※BulkServiceを利用して広告を入稿することはできません。<br>

<b>■ヒント</b><br>
カウントダウン関数を使用すると、広告内にセールやキャンペーンなどの終了までの残り時間を表示できます。また、カウントダウンの終了とともに、広告配信を停止できます。詳しくは以下のヘルプをご参照ください。<br>
・<a href="https://help.marketing.yahoo.co.jp/ja/?p=11374">カウントダウン関数について</a>

##### リクエストサンプル
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns1="http://ss.yahooapis.jp/V201805/AdGroupAd">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>XXXX-XXXX-XXXX-XXXX</ns1:license>
         <ns1:apiAccountId>XXXX-XXXX-XXXX-XXXX</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
         <ns1:accountId>100000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>XXXXX-XXXX-XXXXX-XXXX</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <!--1 or more repetitions:-->
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:campaignId>1001</ns1:campaignId>
               <ns1:adGroupId>10001</ns1:adGroupId>
               <ns1:adName>Best Practice Ad</ns1:adName>
               <ns1:userStatus>ACTIVE</ns1:userStatus>
               <ns1:ad xsi:type="ns1:TextAd2">
                  <ns1:type>TEXT_AD2</ns1:type>
                  <ns1:url>http://www.example.jp</ns1:url>
                  <ns1:displayUrl>www.example.jp</ns1:displayUrl>
                  <ns1:headline>人気の{=セール商品リスト.商品名}が大特価</ns1:headline>
                  <ns1:description>{=セール商品リスト.価格}円で販売。</ns1:description>
                  <ns1:description2>終了まであと{=COUNTDOWN(セール商品リスト.セール終了日,"ja")}</ns1:description2>
               </ns1:ad>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:campaignId>1002</ns1:campaignId>
               <ns1:adName>Best Practice Normal Ad</ns1:adName>
               <ns1:userStatus>ACTIVE</ns1:userStatus>
               <ns1:ad xsi:type="ns1:TextAd2">
                  <ns1:type>TEXT_AD2</ns1:type>
                  <ns1:url>http://www.example.jp</ns1:url>
                  <ns1:displayUrl>www.example.jp</ns1:displayUrl>
                  <ns1:headline>人気の商品が大特価</ns1:headline>
                  <ns1:description>期間限定特別価格で販売。</ns1:description>
                  <ns1:description2>１２月３１日まで</ns1:description2>
               </ns1:ad>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

##### レスポンスサンプル
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V201805/AdGroupAd" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
                     <ns1:headline>人気の{=セール商品リスト.商品名}が大特価</ns1:headline>
                     <ns1:description>{=セール商品リスト.価格}円で販売。</ns1:description>
                     <ns1:description2>終了まであと{=COUNTDOWN(セール商品リスト.セール終了日,"ja")}</ns1:description2>
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

#### 4.	キャンペーンのFeedItem変更
広告入稿後に価格の変動があったため、以下のデータに変更する必要があります。<br>
アドカスタマイザーではFeedItemServiceを使用し、データを更新するだけで広告文面を自動で変更できます。

##### セール商品リスト（変更後）
<table class="standard">
                <tr>
                    <th valign="top" >
                        <p>商品 (String)</p>
                    </th>
                    <th valign="top" >
                        <p>価格 (Price)</p>
                    </th>
                    <th valign="top">
                        <p>セール終了日 (Date)</p>
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
                        <p>製品101</p>
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
                        <p>製品102</p>
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
                        <p>製品103</p>
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

##### リクエストサンプル
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V201805/FeedItem">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>XXXX-XXXX-XXXX-XXXX</ns1:license>
         <ns1:apiAccountId>XXXX-XXXX-XXXX-XXXX</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
         <ns1:accountId>100000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>XXXXX-XXXX-XXXXX-XXXX</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:feedFolderId>200001</ns1:feedFolderId>
               <ns1:feedItemId>300001</ns1:feedItemId>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                  <ns1:feedAttributeId>2</ns1:feedAttributeId>
                  <ns1:feedAttributeValue>90</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
               <ns1:targetingCampaign>
                  <ns1:targetingCampaignId>500001</ns1:targetingCampaignId>
               </ns1:targetingCampaign>
               <ns1:targetingAdGroup>
                  <ns1:targetingAdGroupId>600001</ns1:targetingAdGroupId>
               </ns1:targetingAdGroup>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:feedFolderId>200001</ns1:feedFolderId>
               <ns1:feedItemId>300001</ns1:feedItemId>
               <ns1:feedItemAttribute>
                  <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                  <ns1:feedAttributeId>2</ns1:feedAttributeId>
                  <ns1:feedAttributeValue>350</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
               <ns1:targetingCampaign>
                  <ns1:targetingCampaignId>500001</ns1:targetingCampaignId>
               </ns1:targetingCampaign>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:feedFolderId>200001</ns1:feedFolderId>
               <ns1:feedItemId>300001</ns1:feedItemId>
               <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
               <ns1:targetingCampaign>
                  <ns1:targetingCampaignId>500001</ns1:targetingCampaignId>
               </ns1:targetingCampaign>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

##### レスポンスサンプル
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V201805/FeedItem">
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
                     <ns1:feedAttributeValue>製品101</ns1:feedAttributeValue>
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
                     <ns1:feedAttributeValue>製品102</ns1:feedAttributeValue>
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
                     <ns1:feedAttributeValue>製品103</ns1:feedAttributeValue>
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
