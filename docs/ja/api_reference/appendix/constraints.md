# 値の制限
各種数値の制限値は下記のとおりです。

### 各エンティティの登録可能数
説明                         | 制限                         
---------------------------- | ---------------------------
アカウント                   | キャンペーン数：100<br /> キーワード数：50,000 <br />※デフォルトの上限値です。  
キャンペーン                 | 広告グループ数：2,000
広告グループ                 | キーワード数：2,000<br/>※対象外キーワード数との合計です。<br /> 広告数：50 
対象外キーワード             | キャンペーンレベル：5,000<br />広告グループレベル：2,000<br />※入札キーワード数との合計です。 
曜日・時間帯ターティング     | 1日6個まで<br />※15分単位で作成できます。   
レポート                     | フィルタ条件：5    
フィルタ数                   | 保存可能な数：10                         
テンプレート数               | 保存可能な数：30                                    

### 文字数・入力値の範囲
※特に記載がなければ、文字のbyteサイズに関係なく、文字数による上限になります。

対象          | 制限                              
----------- | --------------------------------
アカウント名      | 100文字                           
キャンペーン名     | 50文字 ※1                         
広告グループ名     | 50文字 ※1                         
広告名         | 50文字 ※1                         
自動入札名       | 50文字                            
タイトル        | 15文字                            
説明文         | 19文字-19文字                       
表示URL       | 29文字                            
リンク先URL     | 1024文字                          
カスタムURL     | 1024文字                          
キーワード       | 80文字 10トークン                     
対象外キーワード    | 80文字 10トークン                     
キャンペーン予算    | 100円～12,500,000円（100円単にで設定可能です。）
キャンペーン      | 1円～9,999円（1円単位で設定可能です。）         
広告グループ入札価格  | 1円～50,000円（1円単位で設定可能です。）        
キーワード入札価格   | 1円～50,000円（1円単位で設定可能です。）        
入金額         | 最小3,000円 （1,000円単位で設定可能です。)     
掲載スケジュール    | 本日から2037年12月31日までの間で指定可能        
自動入札のクリック単価 | 0円～50,000円                      
自動入札の目標CPA  | 0円～99,999,999円                  
入札価格調整率     | 0.10 ～10.00（-90%～+900%）         
広告費用対効果の目標値 | 0.01 ～1000.00（1%～100,000%）      

※1 キャンペーン名／広告グループ名／広告名は、入稿時に特定の記号において下記の変換を行います。

記号      | 変換                | 変換例               
------- | ----------------- | ------------------
全角スペース  | 半角スペース            | 「　」→「 」           
半角カナ    | 全角カナ              | ｱｲｳｴｵ → アイウエオ     
全角数字    | 半角数字              | １２３５ →　1235       
全角英字    | 半角英字              | ＡＢＣＤ → ABCD       
複数スペース  | 一つの半角スペースに結合されます。 | 「あい　　うえお」→「あい うえお」
前後のスペース | 除去されます。           | 「　あいうえお　」→「あいうえお」 

### 各IDの登録可能数

ID | 定期レポート（Add Template指定：YES）| ONETIMEレポート（Add Template指定：NO）                
----------- | ----------- |----------- 
レポートID  　　　　| 30            　　　　| 上限無し        
レポートジョブID    | 上限無し              | 50

※各IDの登録数が上限値に達した場合、新規にIDを作成する事が出来なくなります。<br>
　必要に応じて、mutate Removeをご利用頂きIDの削除をお願いします。<br>
※定期レポートのレポートID（AddTemplate指定、YES）のレポート定義は保存され使いまわしが可能です。<br>
　その他、ONETIMEレポートのレポートID、レポートジョブIDは、作成後1週間程度で自動削除されます。<br>
※APIで登録された各IDの登録可能数は、代行アクセスで作成したID数と通常アクセスで作成したID数の合計値となります。<br>

### 1リクエストあたりの最大指定/取得数
<table>
 <tr>
  <th>Web Service</th>
  <th>Operation</th>
  <th>Max. Elements</th>
  <th>Max. Responses</th>
  <th>Paging</th>
 </tr>
 <tr>
  <td rowspan="2">AccountService</td>
  <td>get</td>
  <td>-</td>
  <td>200</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(SET)</td>
  <td>200</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="2">AccountTrackingUrlService</td>
  <td>get</td>
  <td>-</td>
  <td>1000</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(SET)</td>
  <td>200</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="4">AdGroupAdService</td>
  <td>get</td>
  <td>-</td>
  <td>2000</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(ADD)</td>
  <td>2000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(SET)</td>
  <td>2000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(REMOVE)</td>
  <td>2000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="2">AdGroupBidMultiplierService</td>
  <td>get</td>
  <td>-</td>
  <td>500</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(SET)</td>
  <td>200</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td rowspan="4">AdGroupCriterionService</td>
  <td>get</td>
  <td>-</td>
  <td>2000</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(ADD)</td>
  <td>2000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(SET)</td>
  <td>2000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(REMOVE)</td>
  <td>2000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="2">AdGroupFeedService</td>
  <td>get</td>
  <td>-</td>
  <td>500</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(SET)</td>
  <td>200</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="4">AdGroupRetargetingListService</td>
  <td>get</td>
  <td>-</td>
  <td>1000</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(ADD)</td>
  <td>1000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(SET)</td>
  <td>1000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(REMOVE)</td>
  <td>1000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="4">AdGroupService</td>
  <td>get</td>
  <td>-</td>
  <td>2000</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(ADD)</td>
  <td>2000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(SET)</td>
  <td>2000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(REMOVE)</td>
  <td>2000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="2">AuditLogService</td>
  <td>get</td>
  <td>-</td>
  <td>1000</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>addJob</td>
  <td>1</td>
  <td>-</td>
  <td>-</td>
 </tr>
<tr>
  <td>BalanceService</td>
  <td>get</td>
  <td>-</td>
  <td>100</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>BidLandscapeService</td>
  <td>get</td>
  <td>-</td>
  <td>100</td>
  <td>◯</td>
 </tr>
 <tr>
  <td rowspan="4">BiddingStrategyService</td>
  <td>get</td>
  <td>-</td>
  <td>500</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(ADD)</td>
  <td>200</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(SET)</td>
  <td>200</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(REMOVE)</td>
  <td>200</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="3">CampaignCriterionService</td>
  <td>get</td>
  <td>-</td>
  <td>500</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(ADD)</td>
  <td>200</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(REMOVE)</td>
  <td>200</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="2">CampaignExportService</td>
  <td>get</td>
  <td>-</td>
  <td>500</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>addJob</td>
  <td>500</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="2">CampaignFeedService</td>
  <td>get</td>
  <td>-</td>
  <td>500</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(SET)</td>
  <td>200</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="4">CampaignService</td>
  <td>get</td>
  <td>-</td>
  <td>2000</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(ADD)</td>
  <td>2000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(SET)</td>
  <td>2000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(REMOVE)</td>
  <td>2000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="4">CampaignTargetService</td>
  <td>get</td>
  <td>-</td>
  <td>500</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(ADD)</td>
  <td>200</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(SET)</td>
  <td>200</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(REMOVE)</td>
  <td>200</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="3">ConversionTrackerService</td>
  <td>get</td>
  <td>-</td>
  <td>500</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(ADD)</td>
  <td>100</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(SET)</td>
  <td>100</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="2">DictionaryService</td>
  <td>getDisapprovalReason</td>
  <td>-</td>
  <td>全件</td>
  <td>-</td>
 </tr>
 <tr>
  <td>getGeographicLocation</td>
  <td>-</td>
  <td>全件</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="4">FeedFolderService</td>
  <td>get</td>
  <td>-</td>
  <td>50</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(ADD)</td>
  <td>50</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(SET)</td>
  <td>50</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(REMOVE)</td>
  <td>50</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="4">FeedItemService</td>
  <td>get</td>
  <td>-</td>
  <td>2000</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(ADD)</td>
  <td>2000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(SET)</td>
  <td>2000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(REMOVE)</td>
  <td>2000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>KeywordEstimatorService</td>
  <td>get</td>
  <td>-</td>
  <td>100</td>
  <td>-</td>
 </tr>
 <tr>
  <td>LocationService</td>
  <td>get</td>
  <td>-</td>
  <td>1</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="3">NegativeCampaignRetargetingListService</td>
  <td>get</td>
  <td>-</td>
  <td>1000</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(ADD)</td>
  <td>1000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(REMOVE)</td>
  <td>1000</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="4">ReportDefinitionService</td>
  <td>get</td>
  <td>-</td>
  <td>500</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>getReportFields</td>
  <td>-</td>
  <td>1</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(ADD)</td>
  <td>30</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(REMOVE)</td>
  <td>30</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="3">ReportService</td>
  <td>get</td>
  <td>-</td>
  <td>500</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(ADD)</td>
  <td>20</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(REMOVE)</td>
  <td>20</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="3">RetargetingListService</td>
  <td>get</td>
  <td>-</td>
  <td>1000</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>mutate(ADD)</td>
  <td>200</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mutate(SET)</td>
  <td>200</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>TargetingIdeaService</td>
  <td>get</td>
  <td>-</td>
  <td>500</td>
  <td>◯</td>
 </tr>
 <tr>
  <td>TrafficEstimatorService</td>
  <td>get</td>
  <td>-</td>
  <td>100</td>
  <td>-</td>
 </tr>
</table>
