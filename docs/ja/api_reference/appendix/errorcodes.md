# SOAPエラーコード
SOAPレスポンス時のエラーコードとメッセージの詳細リストです。

### エラー処理概要
SOAPリクエストが成功した場合、スポンサードサーチ APIは HTTP 200 OKというレスポンスコードとSOAPのレスポンスを返します。<br> SOAPリクエストの処理中にエラーが発生した場合、スポンサードサーチAPIはエラーコードが含まれるメッセージを返します。<br>詳しくは[Error](/docs/ja/api_reference/data/Common/Error.md), [ErrorDetail](/docs/ja/api_reference/data/Common/ErrorDetail.md)を確認してください。
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

#### 共通エラー

##### Service
全サービス共通

コード                   | メッセージ  | 説明
------------------------ | ----------- | -------------------------------------------------------
0001 | Invalid Request.  | さまざまな要因が考えられます。<br>主な要因は、パラメータの値が不正か、誤りがあるためにオペレーションが完了できません。
0002 | An internal error has occurred.  |内部エラーが発生しました。再度操作を実行してください。 <br>もし、問題が解決しない場合は、お問い合わせページをご利用ください。<br>※お問合せの際は、必ずXML形式のSOAPリクエスト/レスポンスを含めて連絡ください。
0003 | Frequency limit exceeded. Please try your request again later | アクセス頻度が上限値に達しました。時間をおいて再度実行してください。
0004 | Invalid location.  | このlocationでは、アカウントにアクセスできません。<br>LocationServiceでアカウントに設定されているコロケーションのURL　prefixを取得してください。
0011 | Can not login. | ログインできませんでした。 <br>ライセンスキー、APIアカウント、APIアカウントパスワードに誤りがないか確認してください。<br> OnBehalfアカウントの場合は、OnBehalfOfPasswordに誤りがあるか、要求されたアカウントIDに紐づけられていない可能性があります。
0013 | method is invalid. | 要求された操作は使用できないか、存在しない操作が要求されました。
0014 | selector is invalid.  | セレクターが無効です。セレクターが複数指定されている可能性があります。<br>リクエストのセレクターを確認してください。
0015 | operations is invalid.  | オペレーションが無効です。オペレーションが複数指定されている可能性があります。<br>リクエストのオペレーションを確認してください。
0016 | operator is invalid | 要求されたサービスでは、指定のMUTATE操作はサポートされていません。
0099 | Out of service.  | APIがメンテナンス中、またはご利用できません。
F0001  | Invalid format.   | 値の形式が不正です。
F0002  |	Invalid file format. | アップロードファイルの形式が不正です。
R0001 | Require. | 必須です。
V0001 | Invalid value. | 値が無効です。
V0002 | Empty file. | アップロードファイルが0byteです。
V0003 | Over limit of the file. | アップロードファイルサイズが上限を超過しています。
L0001 | Lower list size. | 配列の要素数が下限値を下回っています。
L0002 | Over list size. | 配列の要素数が上限値を超過しています。
U0001 | Url has expired. | アップロードURLまたはダウンロードURLの有効期限が切れています。
U0002 | Invalid url. | アップロードURLまたはダウンロードURLが不正です。
S0001 | Invalid Status. | ステータスが無効です。
I0001 | Deactivated Id. | IDが無効です。
D0001 | Duplicate. | 一意な値が重複しています。
RL001 | Invalid relation. | リクエストの関連性が矛盾しています。<br> たとえば、開始＞終了の日付指定を行なっているなど
LT001 | Over limit. | 登録できる上限値を超過しています。


#### アカウント、コンバージョントラッカー、リターゲティング管理に関連するエラー
##### Service
[AccountService](/docs/ja/api_reference/services/AccountService.md),<br>
[AccountTrackingUrlService](/docs/ja/api_reference/services/AccountTrackingUrlService.md),<br>
[ConversionTrackerService](/docs/ja/api_reference/services/ConversionTrackerService.md),<br>
[RetargetingListService](/docs/ja/api_reference/services/RetargetingListService.md)

コード                     | メッセージ              | 説明
-------------------------- | ----------------------- | -----------------------------------------------------------
210802| Adult account selected.| アダルトアカウントを指定しています。
210803| Retargeting unavailable.| 審査状態により、リターゲティングが強制停止されているアカウントです。
210804| Registered default list.| デフォルトリストが登録済みのアカウントに対して再度デフォルトリストを登録しています。
210806| Requires default list.| デフォルトリストが登録されていないアカウントに対して条件リストまたは組み合わせリストを登録しています。
210807| Selecting Close default list.| 対象のデフォルトリストに「CLOSED」を指定しています。
210809| Not logical target list.| 組み合わせリストに組合せのターゲットリストを指定しています。
210815| Selecting only one target list.| 組み合わせリストにターゲットリストをひとつだけ指定しています。
210816| Selecting only Not condition.| 組み合わせリストでNOT条件のみを指定しています。
210822| Cannot create a share target list. | 共有アカウントの設定がない場合は、共有のターゲットリストを追加できません。
225303| Cannot duplicate Auto Bidding, since the app conversion type 'App Download' has been already with 'Auto' bidding on the same App ID. | 同一のappIdで、アプリコンバージョン種別に「ダウンロード」が設定されている場合、自動入札を重複して設定できません。
225304| Invalid combination of Auto Bidding and the app conversion type 'App Download' on the same App ID. | 同一のappIdで、アプリコンバージョン種別「ダウンロード」と、自動入札設定の組み合わせが正しくありません。

#### キャンペーン管理に関連するエラー
##### Service
[AccountSharedService](/docs/ja/api_reference/services/AccountSharedService.md),<br>
[AdGroupService](/docs/ja/api_reference/services/AdGroupService.md),<br>
[AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md),<br>
[AdGroupBidMultiplierService](/docs/ja/api_reference/services/AdGroupBidMultiplierService.md),<br>
[AdGroupCriterionService](/docs/ja/api_reference/services/AdGroupCriterionService.md),<br>
[AdGroupFeedService](/docs/ja/api_reference/services/AdGroupFeedService.md),<br>
[AdGroupRetargetingListService](/docs/ja/api_reference/services/AdGroupRetargetingListService.md),<br>
[BiddingStrategyService](/docs/ja/api_reference/services/BiddingStrategyService.md),<br>
[CampaignService](/docs/ja/api_reference/services/CampaignService.md),<br>
[CampaignExportService](/docs/ja/api_reference/services/CampaignExportService.md),<br> [CampaignCriterionService](/docs/ja/api_reference/services/CampaignCriterionService.md),<br>
[CampaignFeedService](/docs/ja/api_reference/services/CampaignFeedService.md),<br>
[CampaignRetargetingListService](/docs/ja/api_reference/services/CampaignRetargetingListService.md),<br>
[CampaignSharedSetService](/docs/ja/api_reference/services/CampaignSharedSetService.md),<br>
[CampaignTargetService](/docs/ja/api_reference/services/CampaignTargetService.md),<br>
[FeedItemService](/docs/ja/api_reference/services/FeedItemService.md),<br>
[SharedCriterionService](/docs/ja/api_reference/services/SharedCriterionService.md)


コード                   | メッセージ  | 説明
------------------------ | ----------- | -------------------------------------------------------
210110| INVALID TARGET | １日のスケジュール指定が上限値（6件）を超えています。
210112| can not delete a PlatformTarget | プラットフォームターゲットを削除することができません。
210113| can not modify a bidMultiplier | Bid調整率を設定することができません。
210123| CAMPAIGN TARGETING MISMATCH | targetingCampaignIdで指定したキャンペーンIDと、targetingAdGroupIdで指定した広告グループの上位キャンペーンIDが異なるため、設定できません。
210126| Mobile app download cannot connect to. | アプリダウンロードキャンペーンは設定できません。
210127| Mobile app download cannot connect to Feed item.| アプリダウンロードキャンペーンにクイックリンクオプション、または電話番号オプションを紐付けしようとしています。
210200| Auto bidding has been used.  | 自動入札がキャンペーン、広告グループ、キーワードのいずれかに設定されているため、削除できません。
210202| Auto bidding type does not match.  | 登録されている自動入札タイプとリクエストされた自動入札タイプが一致しません。
210300| Double or no settings in Auto bidding.  | 入札タイプ、もしくは自動入札IDの指定がありません。 <br>または、入札タイプと自動入札IDの両方を指定しています。
210301| Setting the disabled Auto bidding.  | 編集中（削除含む）の自動入札を指定しています。
210302| Conversion related settings in Auto bidding.  | コンバージョン関連の自動入札を指定しています。
210303| Invalid conversion tracking.  | コンバージョントラッキングが無効です。
210304| Not enough conversions.  | コンバージョン数が不十分です。
210305| Auto bidding is already set.  | キーワードに個別の入札価格や入札設定が指定されている状態で、キャンペーンに「コンバージョン数の最大化」、または「コンバージョン単価の目標値」の自動入札を設定しております。
210306| Cannot use conversion optimizer.| コンバージョンオプティマイザーが利用できません。
210307| Budget is lower than ad group/keywords.| 予算額は、キャンペーン内の広告グループ・キーワードに設定されている予算よりも高く設定してください。
210308| Set campaign active.| キャンペーンがACTIVEでないため、入札設定が利用できません。
210309| Set campaign to Manual CPC.  | キャンペーンが「MANUAL_CPC」でないため、入札設定が利用できません。
210310| Select the correct bid type.  | 入札最適化タイプと一致しません。
210311| Campaign has been started.  | すでに開始しているキャンペーンの開始日は変更できません。
210400| Double setting in Auto bidding.| 入札タイプと自動入札IDの両方を指定しています。
210405| Budget has exceeded.  | 予算額を超過しています。
210409| Bid setting limit has exceed.  | キャンペーン配下の広告広告グループに設定した入札金額または自動入札設定数が上限を超えています。<br>※1キャンペーンに設定できる入札金額および自動入札設定は、配下の広告グループ合計で1000件までです。
210504| Invalid settings in Auto bidding of campaign.  | キャンペーンの入札設定に「コンバージョン数の最大化」、または「コンバージョン単価の目標値」が設定されています。
210505| Invalid settings in Auto bidding of ad group.  | 広告グループの入札設定に「コンバージョン数の最大化」、または「コンバージョン単価の目標値」が設定されています。
210509| Cannot set bidding keyword to negative keywords, or vice versa.  | 対象外キーワードに登録されているキーワードを入札キーワードとしては登録できません。その逆も同様です。
210510| Exists same text with match type.  | 指定されたキーワード、マッチタイプはすでにキャンペーン/広告グループ内に存在します。
210517| Exceeds maximum word limit. | キーワードは最大10個までしか指定できません。
210601| Multiple feeds are set in one ad. | 一つの広告に複数のフィードが含まれています。
210605| App ad does not support Data Auto Insertion. | アプリ広告はデータ自動挿入をサポートしていません。
210606| Cannot create double text ad. | 拡張テキスト広告が設定できるアカウントではありません。
211000| Cannot operate AdvancedURL.| アドバンスドURLに移行済みのため、操作できません。
211001| Cannot set AdvancedMobileURL. | アプリダウンロードキャンペーンでは、advancedMobileUrlの設定はできません。
211003| Domain does not match with DisplayURL.  |表示URLと最終リンク先URLのドメインが一致していません。
211004| Cannot set under AndroidCampaign.  |Androidのアプリキャンペーンでは、以下の設定ができません：<br>・キャンペーン、広告グループ、広告、キーワードにTrackingUrlや CustomParameterを設定<br>・キーワードに最終リンク先URLやスマートフォン向けURLを設定
211005| SharedList is used. | 削除しようとしている対象外キーワードリストは、キャンペーンに設定済みです。<br>（キャンペーンに設定されている対象外キーワードリストは削除できません）
211006| Cannot bid modify criterion campaign opted out. |  キャンペーンでデバイス別入札価格調整率を0（そのデバイスには配信しない）で設定済みのため、広告グループで同デバイスの入札価格調整率は変更できません。
211007| Representative URL Does Not Match. | FeedFolderで設定されているドメインと異なります。
211008| Cannot change Dynamic Ads for Search Campaign. | Dynamic Ads for Searchのキャンペーンに変更はできません。
211009| Cannot Update. | Dynamic Ads for SearchのFeedFolderは更新（mutate[set]）はできません。
211010| Cannot set excluded. | AdGroupWebpageServiceの場合、WebpageConditionType：ALL_PAGESの時にExcludedType：EXCLUDEDは設定できません。又、CampaignWebpageServiceの場合、WebpageConditionType：ALL_PAGESは設定できません。
211011| Cannot set DisplayURL and AdvancedURL,AdvancedMobileURL. | Dynamic Ads for SearchにはAdvancedUrl,AdvancedMobileUrl,displayUrlは設定できません。
211012| Cannot update excluded type target. | 除外タイプのターゲットは変更できません。
211014| Cannot remove FeedFolder related with campaign. | DASキャンペーンに設定されているFeedFolderは削除できません。
211015| Same feedFolderId UploadJob is in progress. | 同じfeedFolderIdのアップロードジョブが実行中のため、アップロードできません。
211017| Cannot add Dynamic Search Ads Feed by Adult Account. | アダルトアカウントの場合、Dynamic Ads for Searchのフィード登録はできません。
225301| Cannot attach criteria at campaign and adgroup. | 広告グループとキャンペーンの両方にターゲットリストの関連付けはできません。
225302| Cannot add closed target list. | 停止中のターゲットリストは関連付けできません。
225305| invalid structured snippet header. | カテゴリ補足オプション（ヘッダ）が不正です。
225306| duplicate structured snippet values. | カテゴリ補足オプション（ヘッダ）が重複しています。

#### レポート処理に関連するエラー
##### Service
[ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md),<br>
[ReportService](/docs/ja/api_reference/services/ReportService.md)

コード                   | メッセージ  | 説明
------------------------ | ----------- | -------------------------------------------------------
240002 | Invalid sortFields Item. | sortFieldsに指定できない組み合わせ項目が含まれています。
240003 | Invalid Filters Item. | Filtersに指定できない項目が含まれています。
240004 | Can not Specify Date Range.| 期間指定の種類がCUSTOM_DATE以外に期間の指定はできません。
240007 | Is Not Template.	| レポートのテンプレート指定がFALSEの時にレポート作成のタイミング時期をONETIME以外の指定はできません。
240008 | Interval Type Is Not SPECIFY_DAY. | レポート作成のタイミング時期をSPECIFYDAY以外に定期レポート作成日の設定はできません。
