# SOAPエラーコード
SOAPレスポンス時のエラーコードとメッセージの詳細リストです。

### エラー処理概要
SOAPリクエストが成功した場合、スポンサードサーチ APIは HTTP 200 OKというレスポンスコードとSOAPのレスポンスを返します。<br> SOAPリクエストの処理中にエラーが発生した場合、スポンサードサーチAPIはエラーコードが含まれるメッセージを返します。<br>詳しくは[Error](/docs/ja/api_reference/data/Error.md), [ErrorDetail](/docs/ja/api_reference/data/ErrorDetail.md)を確認してください。
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:error>
                <ns1:code>0011</ns1:code>
                <ns1:message>not login for apiAccountId</ns1:message>
                     <ns1:detail>
                         <ns1:requestKey>apiAccountId</ns1:requestKey>
                         <ns1:requestValue>xxxxxxxxxxxxxxxxx</ns1:requestValue>
                     </ns1:detail>
            </ns1:error>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### エラーコード
#### 認証エラー
##### Service
全サービス共通  

コード                   | メッセージ  | 説明 
------------------------ | ----------- | -------------------------------------------------------
0001 | Invalid Request.  | さまざまな要因が考えられます。<br>主な要因は、パラメータの値が不正か、誤りがあるためにオペレーションが完了できません。
0002 | An internal error has occurred.  |内部エラーが発生しました。再度操作を実行してください。 <br>もし、問題が解決しない場合は、お問い合わせページをご利用ください。<br>※お問合せの際は、必ずXML形式のSOAPリクエスト/レスポンスを含めて連絡ください。
0003 | Frequency limit exceeded. Please try your request again later | アクセス頻度が上限値に達しました。時間をおいて再度実行してください。
0004 | Invalid location.  | このlocationでは、アカウントにアクセスできません。<br>LocationServiceでアカウントに設定されているコロケーションのURL　prefixを取得してください。
0006 | required. | SOAPリクエストヘッダが不正です。
0007 | invalid number format. | 数値の指定の仕方が不正です。
0008 | invalid string format. | 文字列の指定の仕方が不正です。
0009 | invalid enum. | リクエストに不正な列挙された値が含まれています。
0010 | not a valid id. | 指定されたIDが見つかりませんでした。<br>onBehalfOfAccountIdが指定されたアカウントIDに紐づけられていない場合にもこのエラーが発生します。
0011 | not login for apiAccountId. | 要求されたapiAccountIdでログインできませんでした。 <br>ライセンスキー、APIアカウント、APIアカウントパスワードに誤りがないか確認してください。
0011 | not login for onBehalfOfAccountId. | 要求されたonBehalfOfAccountIdでログインできませんでした。<br>OnBehalfOfPasswordパスワードに誤りがあるか、要求されたアカウントIDに紐づけられていない可能性があります。
0012 | status is invalid. | 要求されたアカウントID、またはonBehalfOfAccountIdが無効です。
0013 | method is invalid. | 要求された操作は使用できないか、存在しない操作が要求されました。
0014 | selector is invalid.  | セレクターが無効です。セレクターが複数指定されている可能性があります。<br>リクエストのセレクターを確認してください。 
0015 | operations is invalid.  | オペレーションが無効です。オペレーションが複数指定されている可能性があります。<br>リクエストのオペレーションを確認してください。 
0016 | operator is invalid | 要求されたサービスでは、指定のMUTATE操作はサポートされていません。 
0017 | over list size.  | リクエストの要素数が制限を超えています。<br>要素の数を減らし再度リクエストしてください。 
0018 | The data size you requested is too large. Please try your request again with a smaller date range or reduce the size of your request.  | 生成されるデータのサイズが大きいため取得に失敗しました。<br>集計期間やパラメーターを調整し、再度リクエストを実施してください。
0050 | Too many items.  | 項目の数が多すぎます。
0051 | Too little items.  | 項目の数が少なすぎます。
0052 | Too many values.  | 値の数が多すぎます。
0053 | Too little values.  | 値の数が少なすぎます。
0054 | Too long values.  | 値が長すぎます。
0055 | Too short value.  | 値が短すぎます。
0056 | Too large value.  | 値が大きすぎます。
0057 | Too small value.  | 値が小さすぎます。
0058 | Duplicate values.  | 値が重複しています。
0059 | Same value has already been registered.  | 同じ値がすでに登録されています。
0060 | Invalid date format.	| 日付形式が無効です。
0061 | Out of range.	| 有効範囲ではありません。
0062 | Invalid relation.	| 関係が無効です。
0063 | Over limit.	| 制限を超えています。
0064 | Invalid url format.	| URL形式が無効です。
0065 | Invalid step value.  | 刻み値が無効です。
0066 | Date set before the available period.  | 設定可能の期間よりも、前の日付が指定されています。
0067 | Date set after the available period.  | 設定可能の期間よりも、後の日付が指定されています。
0099 | Out of service.  | APIがメンテナンス中、またはご利用できません。

#### アカウント管理に関連するエラー
##### Service
[AccountService](/docs/ja/api_reference/services/AccountService.md)

コード                     | メッセージ              | 説明   
-------------------------- | ----------------------- | -----------------------------------------------------------
20110005 | INVALID VALUE | 無効なアカウントIDです。
20110006 | TOO MANY VALUE | アカウントIDの数が上限を超えています。
20110007 | INVALID VALUE CONTENT | 無効なアカウントIDが含まれています。
20110011 | INVALID VALUE | 要求されたアカウントステータスが無効です。
20110012 | TOO MANY VALRUE | アカウントステータスの数が上限を超えています。
20110013 | INVALID VALUE CONTENT | 無効なアカウントステータスが含まれています。
20130008 | INVALID VALUE | 無効なアカウントです。
20130009 | INPUT REQUIRED | アカウントは必須です。
20130010 | TOO MANY VALUE | アカウントの数が上限を超えています。
20130011 | INVALID VALUE | 無効なアカウントIDです。
20130012 | INPUT REQUIRED | アカウントIDは必須です。
20130013 | DUPLICATE VALUE | アカウントIDが重複しています。
20130014 | NO ACCOUNT FOUND | 要求されたアカウントIDが見つかりませんでした。
20130015 | CANNOT SET TO ACCOUNT | 指定されたアカウントは更新できません。
20130019 | INVALID VALUE | リクエストで指定されたアカウント名は無効です。
20130020 | CANNOT SET EMPTY | リクエストで指定されたアカウント名が空です。<br>アカウント名は空にすることができません。
20130021 | TOO LONG VALUE | リクエストで指定されたアカウント名の文字数が超過しています。
20130022 | READ ONLY | アカウント種別は読み取り専用です。
20130027 | INVALID VALUE | リクエストで指定された配信ステータスは無効です。
20130028 | CANNOT SET VALUE | 配信ステータスをセットすることはできません。
20410003 | INPUT REQUIRED | アカウントIDは必須です。
20410004 | INVALID VALUE | 無効なアカウントIDです。
20410005 | TOO MANY VALUE | アカウントIDの数が上限を超えています。
20410006 | INVALID VALUE CONTENT | リクエストに1つ以上の無効なアカウントIDが含まれています。
20410007 | NO ACCOUNT FOUND | 要求されたアカウントIDが見つかりませんでした。
20410009 |GET BALANCE FAILED | アカウント残高の取得に失敗しました。

##### Service
[AccountTrackingUrlService](/docs/ja/api_reference/services/AccountTrackingUrlService.md)

コード                     | メッセージ              | 説明   
-------------------------- | ----------------------- | -----------------------------------------------------------
210903 | Invalid role. | アカウント操作権限が無効です。
210905 | Invalid status. | 審査中に審査項目の変更はできません。
210907 | url restriction. | 入稿できないURLが設定されました。
210909 | not account updatable. | アカウントの更新ができない状態です。


#### 請求に関連するエラー
##### Service
[BalanceService](/docs/ja/api_reference/services/BalanceService.md)  

 コード  | メッセージ | 説明              
-------- | ---------- | ------------------------  
20410003 | INPUT REQUIRED | アカウントIDは必須です。  
20410004 | INVALID VALUE | 無効なアカウントIDです。   
20410005 | TOO MANY VALUE | アカウントIDの数が上限を超えています。  
20410006 | INVALID VALUE CONTENT | リクエストに1つ以上の無効なアカウントIDが含まれています。  
20410007 | NO ACCOUNT FOUND | 要求されたアカウントIDが見つかりませんでした。  
20410009 | GET BALANCE FAILED | アカウント残高の取得に失敗しました。  

#### キャンペーン管理に関連するエラー
##### Service
[AccountSharedService](/docs/ja/api_reference/services/AccountSharedService.md),<br>
[AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md),<br>
[AdGroupBidMultiplierService](/docs/ja/api_reference/services/AdGroupBidMultiplierService.md),<br>
[CampaignExportService](/docs/ja/api_reference/services/CampaignExportService.md),<br> [CampaignCriterionService](/docs/ja/api_reference/services/CampaignCriterionService.md),<br>
[CampaignSharedSetService](/docs/ja/api_reference/services/CampaignSharedSetService.md),<br>
[CampaignTargetService](/docs/ja/api_reference/services/CampaignTargetService.md),<br> [CustomerSyncService](/docs/ja/api_reference/services/CustomerSyncService.md),<br> [SharedCriterionService](/docs/ja/api_reference/services/SharedCriterionService.md),<br>

コード                   | メッセージ  | 説明 
------------------------ | ----------- | -------------------------------------------------------
0018 | The data size you requested is too large. Please try your request again with a smaller date range or reduce the size of your request.  | 生成されるデータのサイズが大きいため取得に失敗しました。<br>集計期間やパラメーターを調整し、再度リクエストを実施してください。 
0103 | Exists same name. | キャンペーン、広告グループ、もしくは広告の名前が重複します。<br>ユニーク（一意的）な名前を指定してください。 
1003 | invalid download request. | ダウンロードURLの取得ホストと実行ホストが異なります。
1004 | download URL has expired. | ダウンロードURLの有効期限が切れました。<br />ダウンロードURLが改ざんされています。
10100 | DEACTIVATED | 削除済みとして登録されました。<br>アカウントステータスがアクティブでない、またはアカウントが存在しない場合にもこのエラーが発生する可能性があります。
10200 | INVALID_STATUS | カスタムURLを更新するためには、キーワードが"承認済み"になっている必要があります。
10300 | OVER_LIMIT | 上限値を超えています。リクエストのサイズを調整して、再度実行してください。
10501 | UNMATCH_BIDDING _STRATEGY_TYPE | 広告の配信方法が「ACCELERATED」の場合は、BudgetOptimizerを設定できません。<br>biddingStrategyTypeが、キャンペーンのiddingStrategyTypeと一致しない場合にもこのエラーが発生する可能性があります。
10601 | OVER_BUDGET_AMOUNT | キャンペーンよりも高い予算額は設定できません。
10602 | LOWER_BUDGET_AMOUNT | 予算額は、キャンペーン内の広告グループ・キーワードに設定されている予算よりも高く設定する必要があります。
10701 | EXISTS_DIFFERENT _CRITERION_USE_TYPE | 対象外キーワードに登録されているキーワードを入札キーワードとしては登録できません。<br>その逆も同様です。
10702 | EXISTS_SAME_TERM _WITH_MATCH_TYPE | 指定されたキーワード、マッチタイプはすでにキャンペーン/広告グループ内に存在します。
10900 | UNMATCH_PLATFORM_TYPE | 無効なプラットフォームタイプです。
10901 | UNMATCH_DEVICE _PREFERENCE | デバイス優先配信フラグの設定が不正です。 <br>ユニファイドキャンペーンで設定を行ってください。
20101 | REQUIRED | リクエストに必要なパラメーターが欠落、または空で指定されています。
20102 | NOT_LIST | 要求された操作は配列を必要とします。
20103 | OVER_LIST_SIZE | 指定した要素数が上限値を超えています。 <br>リクエストのサイズを調整して、再度実行してください。
20104 | LOWER_LIST_SIZE | 指定されたリスト/コンテナは、少なくとも1つ以上の有効なオブジェクトを提供する必要があります。
20105 | NOT_HASH | この操作は連想配列が必要です。
20401 | DUPLICATE | 追加するオブジェクトの内容が内容が重複しています。 <br>既に登録済みのキーワードを登録する場合にも発生する可能性があります。
20601 | INVALID_NUMBER_FORMAT | 数値の指定の仕方が不正です。
20602 | LOWER_NUMBER | 設定可能な予算額を下回っています。
20603 | OVER_NUMBER | 設定可能な予算額を超過しています。
20604 | INVALID_STEP_NUMBER | 予算額は100円単位で設定してください。 
20701 | INVALID_STRING_FORMAT | 文字列の指定の仕方が不正です。 
20702 | LOWER_STRING | 文字列が短すぎます。 
20703 | OVER_STRING | 文字列が超過しています。
20901 | INVALID_DATE_FORMAT | 日付の指定に誤りがあります。 <br>日付の形式は、YYYYMMDDで指定してください。
20902 | LOWER_DATE | 設定可能の期間よりも、前の日付が指定されています。
20903 | OVER_DATE | 設定可能の期間よりも、後の日付が指定されています。
21001 | INVALID_ENUM | リクエストに不正な列挙された値が含まれています。
21301 | INVALID_TARGET | 指定したターゲットタイプは対象のキャンペーンには適用できません。
21401 | INVAILD_RELATION | 指定したIDやcliterionUseが有効ではありません。<br>開始日より前の終了日を指定した場合にもこのエラーが発生する可能性があります。
21601 | INVALID_URL_FORMAT | クリックURL、または、キーワードのカスタムURLが不正です。
120001 | REQUIRED | リクエストに存在しません。 
120003 | INVALID NUMBER FORMAT | 数値の形式が不正です。
120016 | TOO LARGE VALUE | 数値が大きいです。 
120017 | TOO SMALL VALUE | 数値が小さいです。
120018 | DUPLICATE VALUE | 配列内に同一広告グループIDです。
120022 | DEACTIVATED | データが存在しません。
120027 | OVER LIST SIZE | 配列が2以上です。
211001 | Cannot set AdvancedMobileURL. | アプリダウンロードキャンペーンでは、advancedMobileUrlの設定はできません。
211003 | Domain does not match with DisplayURL.  | 	表示URLと最終リンク先URL（モバイル含む）のドメインが一致していません。
211004 | Cannot set under AndroidCampaign.  | 	Androidのアプリキャンペーンでは、以下の設定ができません：<br>・キャンペーン、広告グループ、広告、キーワードにTrackingUrlや CustomParameterを設定
211005| SharedList is used. | 削除しようとしている対象外キーワードリストは、キャンペーンに設定済みです。<br>（キャンペーンに設定されている対象外キーワードリストは削除できません）

##### Service
[CampaignService](/docs/ja/api_reference/services/CampaignService.md)  
  
コード                   | メッセージ  | 説明 
------------------------ | ----------- | -------------------------------------------------------
210300 | Double or no settings in Auto bidding.  | 入札タイプ、もしくは自動入札IDの指定がありません。 <br>または、入札タイプと自動入札IDの両方を指定しています。
210301 | Setting the disabled Auto bidding.  | 編集中（削除含む）の自動入札を指定しています。
210302 | Conversion related settings in Auto bidding.  | コンバージョン関連の自動入札を指定しています。
210303 | Invalid conversion tracking.  | コンバージョントラッキングが無効です。
210304 | Not enough conversions.  | コンバージョン数が不十分です。
210305 | Auto bidding is already set.  | キーワードに個別の入札価格や入札設定が指定されている状態で、キャンペーンに「コンバージョン数の最大化」、または「コンバージョン単価の目標値」の自動入札を設定しております。
210306 | Cannot use conversion optimizer.	| コンバージョンオプティマイザーが利用できません。
210307 | Budget is lower than ad group/keywords.	| 予算額は、キャンペーン内の広告グループ・キーワードに設定されている予算よりも高く設定してください。
210308 | Set campaign active.	| キャンペーンがACTIVEでないため、入札設定が利用できません。
210309 | Set campaign to Manual CPC.  | キャンペーンが「MANUAL_CPC」でないため、入札設定が利用できません。
210310 | Select the correct bid type.  | 入札最適化タイプと一致しません。
211000 | Cannot operate AdvancedURL.	| アドバンスドURLに移行済みのため、操作できません。
211001 | Cannot set AdvancedMobileURL. | アプリダウンロードキャンペーンでは、advancedMobileUrlの設定はできません。
211002 | Lpurl is required for ValueTrack.	| トラッキングURLにバリュートラックの{lpurl}を入れてください。
211003 | Domain does not match with DisplayURL.  | 	表示URLと最終リンク先URLのドメインが一致していません。
211004 | Cannot set under AndroidCampaign.  | 	Androidのアプリキャンペーンでは、以下の設定ができません：<br>・キャンペーン、広告グループ、広告、キーワードにTrackingUrlや CustomParameterを設定<br>・キーワードに最終リンク先URLやスマートフォン向けURLを設定

##### Service
[AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)  
  
コード                   | メッセージ  | 説明 
------------------------ | ----------- | -------------------------------------------------------
210301 | Setting the disabled Auto bidding.  | 編集中（削除含む）の自動入札を指定しています。
210400 | Double setting in Auto bidding.	| 入札タイプと自動入札IDの両方を指定しています。
210402 | Invalid conversion tracking.  | コンバージョントラッキングが無効です。
210403 | Not enough conversions.  | コンバージョン数が不十分です。
210404 | Auto bidding is already set.  | キーワードに個別の入札価格や入札設定が指定されている状態で、キャンペーンに「コンバージョン数の最大化」、または「コンバージョン単価の目標値」の自動入札を設定しています。
210405 | Budget has exceeded.  | 予算額を超過しています。
210406 | Cannot use conversion optimizer.  | 自動入札設定が利用できません。
210407 | Set campaign active.	| キャンペーンがACTIVEでないため、入札設定が利用できません。
210408 | Set campaign to Manual CPC.  | キャンペーンが「MANUAL_CPC」でないため、入札設定が利用できません。
210409 | Bid setting limit has exceed.  | キャンペーン配下の広告広告グループに設定した入札金額または自動入札設定数が上限を超えています。<br>※1キャンペーンに設定できる入札金額および自動入札設定は、配下の広告グループ合計で1000件までです。
211000 | Cannot operate AdvancedURL.	| アドバンスドURLに移行済みのため、操作できません。
211001 | Cannot set AdvancedMobileURL. | アプリダウンロードキャンペーンでは、advancedMobileUrlの設定はできません。
211002 | Lpurl is required for ValueTrack.	| トラッキングURLにバリュートラックの{lpurl}を入れてください。
211003 | Domain does not match with DisplayURL.  | 	表示URLと最終リンク先URLのドメインが一致していません。
211004 | Cannot set under AndroidCampaign.  | 	Androidのアプリキャンペーンでは、以下の設定ができません：<br>・キャンペーン、広告グループ、広告、キーワードにTrackingUrlや CustomParameterを設定<br>・キーワードに最終リンク先URLやスマートフォン向けURLを設定

##### Service
[AdGroupCriterionService](/docs/ja/api_reference/services/AdGroupCriterionService.md) 
  
コード                   | メッセージ  | 説明 
------------------------ | ----------- | -------------------------------------------------------
210500 | Double setting in Auto bidding.  | 入札タイプと自動入札IDの両方を指定しています。
210501 | Setting the disabled Auto bidding.  | 編集中（削除含む）の自動入札を指定しています。
210502 | Invalid conversion tracking.  | コンバージョントラッキングが無効です。
210503 | Not enough conversions.  | コンバージョン数が不十分です。
210504 | Invalid settings in Auto bidding of campaign.  | キャンペーンの入札設定に「コンバージョン数の最大化」、または「コンバージョン単価の目標値」が設定されています。
210505 | Invalid settings in Auto bidding of ad group.  | 広告グループの入札設定に「コンバージョン数の最大化」、または「コンバージョン単価の目標値」が設定されています。
210506 | Invalid keyword settings.  | キーワードに指定できない自動入札設定です。
210507 | Budget has exceeded.  | 予算額を超過しています。
210508 | Keyword is not approved yet.  | カスタムURLを更新するためには、キーワードが"承認済み"になっている必要があります。
210509 | Cannot set bidding keyword to negative keywords, or vice versa.  | 対象外キーワードに登録されているキーワードを入札キーワードとしては登録できません。その逆も同様です。
210510 | Setting already exists in campaign/ad group.  | 指定されたキーワード、マッチタイプはすでにキャンペーン/広告グループ内に存在します。
210511 | Cannot use conversion optimizer.  | コンバージョンオプティマイザーが利用できません。
210512 | Set campaign active.	| キャンペーンがACTIVEでないため、入札設定が利用できません。
210513 | Set campaign to Manual CPC.  | キャンペーンが「MANUAL_CPC」でないため、入札設定が利用できません。
210517 | Exceeds maximum word limit. | キーワードは最大10個までしか指定できません。
211000 | Cannot operate AdvancedURL.	| アドバンスドURLに移行済みのため、操作できません。
211001 | Cannot set AdvancedMobileURL. | アプリダウンロードキャンペーンでは、advancedMobileUrlの設定はできません。
211004 | Cannot set under AndroidCampaign.  | 	Androidのアプリキャンペーンでは、以下の設定ができません：<br>・キャンペーン、広告グループ、広告、キーワードにTrackingUrlや CustomParameterを設定<br>・キーワードに最終リンク先URLやスマートフォン向けURLを設定

##### Service
[BiddingStrategyService](/docs/ja/api_reference/services/BiddingStrategyService.md) 
  
コード                   | メッセージ  | 説明 
------------------------ | ----------- | -------------------------------------------------------
210200 | Auto bidding has been used.  | 自動入札がキャンペーン、広告グループ、キーワードのいずれかに設定されているため、削除できません。 
210201 | Minimum value is higher than maximum value.  | クリック単価の上限値より下限値の方が大きくなるため、設定することができません。
210202 | Auto bidding type does not match.  | 登録されている自動入札タイプとリクエストされた自動入札タイプが一致しません。


#### レポート処理に関連するエラー
##### Service
[ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)

コード                   | メッセージ  | 説明 
------------------------ | ----------- | -------------------------------------------------------
0002 | An internal error has occurred.  | 内部エラーが発生しました。再度操作を実行してください。 <br>もし、問題が解決しない場合は、お問い合わせページをご利用ください。<br>※お問合せの際は、必ずXML形式のSOAPリクエスト/レスポンスを含めて連絡ください。 
0108 | entity count limit exceeded.  | 登録できるテンプレートの上限数を超えています。<br>レポート定義のテンプレートが、標準認証と代行認証あわせて30件に達していないか確認してください。
20103 | OVER_LIST_SIZE| 指定した要素数が上限値を超えています。
40001 | REQUIRED | リクエストに必要なパラメーターが欠落、または空で指定されています。 
40002 | NOT_LIST | 要求された操作は配列が必要です。 
40003 | OVER_LIST_SIZE | 指定した要素数が上限値を超えています。 <br>リクエストのサイズを調整して、再度実行してください。
40004 | LOWER_LIST_SIZE | 指定されたリスト/コンテナは、少なくとも1つ以上の有効なオブジェクトを提供する必要があります。
40011 | INVALID_NUMBER_FORMAT | 数値の指定の仕方が不正です。
40012 | LOWER_NUMBER | 指定された値が小さすぎます。
40013 | OVER_NUMBER | 指定された値が大きすぎます。
40021 | INVALID_STRING_FORMAT | 文字列の指定の仕方が不正です。
40022 | LOWER_STRING | 文字列が短すぎます。
40023 | OVER_STRING | 文字列が超過しています。
40024 | INVALID_URL_FORMAT | クリックURL、またはキーワードのカスタムURLが不正です。
40026 | ILLEGAL_CHARACTER | オブジェクトの名称に、1つ以上の不正な文字が含まれています。
40031 | INVALID_DATE_FORMAT | 日付の指定に誤りがあります。 <br>このエラーには指定された日時の妥当性も含みます。
40032 | OVER_DATE_RANGE | 指定された日付が、設定できる期間を超えています。
40041 | INVALID_ENUM | リクエストに不正な列挙された値が含まれています。
40051 | INVALID_RELATION | このエラーは通常、終了日が開始日より前に設定されている場合に発生します。
40100 | JOB_IN_PROGRESS | レポート登録が進行中にレポート削除処理を実施されております。
60003 | DATA_NOT_FOUND | 指定したレポートIDが存在しない場合に発生します。 
60004 | JOB_IN_PROGRESS | ジョブ実行中のため、レポート定義が削除できませんでした。
240000 | Contains Invalid Character. | 入稿規定外の文字が含まれています。
240002 | Invalid sortFields Item. | sortFieldsに指定できない組み合わせ項目が含まれています。
240003 | Invalid Filters Item. | Filtersに指定できない項目が含まれています。
240004 | Can not Specify Date Range.| 期間指定の種類がCUSTOM_DATE以外に期間の指定はできません。
240007 | Is Not Template. | レポートのテンプレート指定がFALSEの時にレポート作成のタイミング時期をONETIME以外の指定はできません。
240008 | Interval Type Is Not SPECIFY_DAY. | レポート作成のタイミング時期をSPECIFYDAY以外に定期レポート作成日の設定はできません。


##### Service
[ReportService](/docs/ja/api_reference/services/ReportService.md)

コード                   | メッセージ  | 説明 
------------------------ | ----------- | -------------------------------------------------------
0002 | An internal error has occurred.  |内部エラーが発生しました。再度操作を実行してください。 <br>もし、問題が解決しない場合は、お問い合わせページをご利用ください。<br>※お問合せの際は、必ずXML形式のSOAPリクエスト/レスポンスを含めて連絡ください。
20103 | OVER_LIST_SIZE| 指定した要素数が上限値を超えています。
40001 | REQUIRED | リクエストに必要なパラメーターが欠落、または空で指定されています。
40002 | NOT_LIST | 要求された操作は配列を必要とします。
40003 | OVER_LIST_SIZE | 指定した要素数が上限値を超えています。<br>リクエストのサイズを調整して、再度実行してください。
40004 | LOWER_LIST_SIZE | 指定されたリスト/コンテナは、少なくとも1つ以上の有効なオブジェクトを提供する必要があります。
40011 | INVALID_NUMBER_FORMAT | 数値の指定の仕方が不正です。
40012 | LOWER_NUMBER | 指定された値が小さすぎます。
40013 | OVER_NUMBER | 指定された値が大きすぎます。

#### 提案機能・予測に関連するエラー
##### Service
[BidLandscapeService](/docs/ja/api_reference/services/BidLandscapeService.md),<br> [TargetingIdeaService](/docs/ja/api_reference/services/TargetingIdeaService.md),<br>
[KeywordEstimatorService](/docs/ja/api_reference/services/KeywordEstimatorService.md)

コード                   | メッセージ  | 説明 
------------------------ | ----------- | -------------------------------------------------------
20002 | INVALID VALUE | 無効なアカウントIDです。
20003 | TOO HIGH | 指定した値が上限値を超えています。
20004 | TOO LOW | 指定した値が下限値を下回っています。
30002 | INVALID VALUE | パラメータの値が不正です。 <br>指定したターゲットの値を確認してください
40002 | INVALID VALUE | パラメータの値が不正です。 <br>指定したキーワードの値を確認してください。
40003 | TO LONG | 指定したキーワードの文字が超過しています。
40004 | INVALID ENUM | リクエストに不正な列挙された値が含まれています。
50002 | MISSING REQUIRED FIELED | リクエストに必要なパラメーターが欠落、または空で指定されています。
50004 | SIIZE LIMIT OVER | リクエストで指定できる数を超えています、
80001 | DUPULICATED VALUE | 重複したデータを指定しています。
80003 | ADGROUP NOT FOUND | 広告グループが見つかりません。
80004 | CRITERION NOT FOUND | キーワードが見つかりません。
80006 | TOO MANY WORDS | キーワードのトークン数が多すぎます。
80007 | INSUFFICIENT SEARCH PARAMETERS | 検索キーワードか、URLの指定がありません。 <br>EXCLUDED_KEYWORDを指定する場合は、RELATED_TO_KEYWORDか、RELATED_TO_URLの指定を1つ以上含めてください。
120026 | REQUIRED BIDDABLE KEYWORD | 指定されたキーワードが全て対象外キーワードです。

#### コンバージョントラッカー管理に関するエラー
##### Service
[ConversionTrackerService](/docs/ja/api_reference/services/ConversionTrackerService.md)

コード                   | メッセージ  | 説明 
------------------------ | ----------- | -------------------------------------------------------
120001 | REQUIRED | 必須です。
120002 | INVALID VALUE | 値が無効です。
120010 | TOO MANY ITEM | 項目の数が多すぎます。
120012 | TOO MANY VALUE | 値の数が多すぎます。
120014 | TOO LONG VALUE | 値が長すぎます。
120016 | TOO LARGE VALUE | 値が大きすぎます。
120017 | TOO SMALL VALUE | 値が小さすぎます。
120018 | DUPLICATE VALUE | 値が重複しています。
120022 | DEACTIVATED | アクティブではありません。
120023 | OVER LIMIT | 制限を超えています。
120024 | INVALID RELATION | 関係が無効です。
210004 | INVALID SNIPPET FORMAT | スニペットの形式が無効です。

#### FeedItemに関するエラー
##### Service
[FeedItemService](/docs/ja/api_reference/services/FeedItemService.md)

コード                   | メッセージ  | 説明 
------------------------ | ----------- | -------------------------------------------------------
20103 | OVER_LIST_SIZE| 指定した要素数が上限値を超えています。
21601 | Invalid url format. | クイックリンクURL、または、キーワードのカスタムURLが不正です。
210102 | INVALID PHONE NUMBER | FeedItemServiceでCALL_PHONE_NUMBERに指定した電話番号の形式が正しくありません。<br>このエラーはCALLEXTENSIONのFeedItem情報の登録の場合に発生します。
210104 | INVALID STATUS | 審査中のため、更新できません。 
210110 | INVALID TARGET | １日のスケジュール指定が上限値（6件）を超えています。
211000 | Cannot operate AdvancedURL.	| アドバンスドURLに移行済みのため、操作できません。
210123 | CAMPAIGN TARGETING MISMATCH | targetingCampaignIdで指定したキャンペーンIDと、targetingAdGroupIdで指定した広告グループの上位キャンペーンIDが異なるため、設定できません。
210126 | Mobile app download cannot connect to. | アプリダウンロードキャンペーンは設定できません。


##### Service
[CampaignFeedService](/docs/ja/api_reference/services/CampaignFeedService.md)

コード                   | メッセージ  | 説明 
------------------------ | ----------- | -------------------------------------------------------
20103 | OVER_LIST_SIZE| 指定した要素数が上限値を超えています。
120002 | INVALID VALUE| 値が無効です。
120018 | DUPLICATE VALUE| 値が重複しています。
120022 | DEACTIVATED| 無効なIDを指定しています。
120024 | INVALID RELATION| 関係が無効です。
210103 | UNMATCH PLACEHOLDER TYPE| placeholderTypeとfeedItemIdの組み合わせが正しくありません。
210127 | Mobile app download cannot connect to Feed item.| アプリダウンロードキャンペーンにクイックリンクオプション、または電話番号オプションを紐付けしようとしています。

##### Service
[AdGroupFeedService](/docs/ja/api_reference/services/AdGroupFeedService.md)

コード                   | メッセージ  | 説明 
------------------------ | ----------- | -------------------------------------------------------
20103 | OVER_LIST_SIZE| 指定した要素数が上限値を超えています。
120002 | INVALID VALUE| 値が無効です。
120018 | DUPLICATE VALUE| 値が重複しています。
120022 | DEACTIVATED| 無効なIDを指定しています。
120024 | INVALID RELATION| 関係が無効です。
210103 | UNMATCH PLACEHOLDER TYPE| placeholderTypeとfeedItemIdの組み合わせが正しくありません。
210127 | Mobile app download cannot connect to Feed item.| アプリダウンロードキャンペーンにクイックリンクオプション、または電話番号オプションを紐付けしようとしています。

#### リターゲティングに関するエラー
##### Service
[RetargetingListService](/docs/ja/api_reference/services/RetargetingListService.md)

コード                   | メッセージ  | 説明 
------------------------ | ----------- | -------------------------------------------------------
210802 | Adult account selected.| アダルトアカウントを指定しています。
210803 | Retargeting unavailable.| 審査状態により、リターゲティングが強制停止されているアカウントです。
210804 | Registered default list.| デフォルトリストが登録済みのアカウントに対して再度デフォルトリストを登録しています。
210806 | Requires default list.| デフォルトリストが登録されていないアカウントに対して条件リストまたは組み合わせリストを登録しています。
210807 | Selecting Close default list.| 対象のデフォルトリストに「CLOSE」を指定しています。
210808 | Invalid rule operator.| 指定できないオペレーターを指定しています。
210809 | Not logical target list.| 組合せリストに組合せのターゲットリストを指定しています。
210815 | Selecting only one target list.| 組合せリストにターゲットリストをひとつだけ指定しています。
210816 | Selecting only Not condition.| 組合せリストでNOT条件のみを指定しています。

##### Service
[NegativeCampaignRetargetingListService](/docs/ja/api_reference/services/NegativeCampaignRetargetingListService.md)

コード                   | メッセージ  | 説明 
------------------------ | ----------- | -------------------------------------------------------
210810 | Status not approved.| 指定したターゲットリストの審査が承認されていません。

##### Service
[AdGroupRetargetingListService](/docs/ja/api_reference/services/AdGroupRetargetingListService.md)

コード                   | メッセージ  | 説明 
------------------------ | ----------- | -------------------------------------------------------
210810 | Status not approved.| 指定したターゲットリストの審査が承認されていません。
210811 | Target list not found.| リクエストで指定されたターゲットリストが登録されていません。
210812 | Already existing target list.| リクエストで指定されたターゲットリストが既に登録されています。
210813 | Cannot bid the negative criterion.| 除外設定にも関わらず入札が指定されています。
210814 | List already registered.| 対象広告グループIDに対して有効・除外ユーザリストの組み合わせが既に登録されています。

