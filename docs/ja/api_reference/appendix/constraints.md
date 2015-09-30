# 値の制限
各種数値の制限値は下記のとおりです。
### 各エンティティの登録可能数
説明                           | 制限                         
---------------------------- | --------------------------- | -----
アカウント                        | キャンペーン数 100  <br> キーワード数  ※デフォルトの上限値です。 50,000                     
キャンペーン                       | 広告グループ数 2,000
広告グループ                       | キーワード数  ※対象外キーワード数との合計です。 2,000 <br>広告数 50                         
対象外キーワード                     | キャンペーンレベル 5,000 広告グループレベル  ※入札キーワード数との合計です。 2,000  
曜日・時間帯ターティング                 | 1日に設定できるターゲティングの数  （15分単位） 6個   
レポート                         | フィルタ条件 5    
保存可能なフィルタ数                   | 10                         
保存可能なテンプレート数                 | 30                         

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

### 各サービスの1リクエストあたりの最大指定（取得）数
Web Service                  | Operation             | 操作可能エレメント数 | レスポンス最大数                       | Paging
---------------------------- | --------------------- | ---------- | ------------------------------ | ------
LocationService              | get                   | -          | 1                              | -     
AccountService               | get                   | -          | 200                            | ○     
AccountService               | mutate(SET)           | 200        | -                              | -     
BalanceService               | get                   | -          | 100                            | ○     
CampaignService              | get                   | -          | 500                            | ○     
CampaignService              | mutate(ADD)           | 200        | -                              | -     
CampaignService              | mutate(SET)           | 200        | -                              | -     
CampaignService              | mutate(REMOVE)        | 200        | -                              | -     
CampaignTargetService        | get                   | -          | 500                            | ○     
CampaignTargetService        | mutate(ADD)           | 200        | -                              | -     
CampaignTargetService        | mutate(SET)           | 200        | -                              | -     
CampaignTargetService        | mutate(REMOVE)        | 200        | -                              | -     
CampaignCriterionService     | get                   | -          | 500                            | ○     
CampaignCriterionService     | mutate(ADD)           | 200        | -                              | -     
CampaignCriterionService     | mutate(REMOVE)        | 200        | -                              | -     
AdGroupService               | get                   | -          | 500                            | ○     
AdGroupService               | mutate(ADD)           | 200        | -                              | -     
AdGroupService               | mutate(SET)           | 200        | -                              | -     
AdGroupService               | mutate(REMOVE)        | 200        | -                              | -     
AdGroupCriterionService      | get                   | -          | 500                            | ○     
AdGroupCriterionService      | mutate(ADD)           | 200        | -                              | -     
AdGroupCriterionService      | mutate(SET)           | 200        | -                              | -     
AdGroupCriterionService      | mutate(REMOVE)        | 200        | -                              | -     
AdGroupAdService             | get                   | -          | 500                            | ○     
AdGroupAdService             | mutate(ADD)           | 200        | -                              | -     
AdGroupAdService             | mutate(SET)           | 200        | -                              | -     
AdGroupAdService             | mutate(REMOVE)        | 200        | -                              | -     
FeedItemServices             | get                   | -          | 500                            | ○     
FeedItemServices             | mutate(ADD)           | 200        | -                              | -     
FeedItemServices             | mutate(SET)           | 200        | -                              | -     
FeedItemServices             | mutate(REMOVE)        | 200        | -                              | -     
CampaignFeedServices         | get                   | -          | 500                            | ○     
CampaignFeedServices         | mutate(SET)           | 200        | -                              | -     
AdGroupFeedServices          | get                   | -          | 500                            | ○     
AdGroupFeedServices          | mutate(SET)           | 200        | -                              | -     
AdGroupBidMultiplierServices | get                   | -          | 500                            | ○     
AdGroupBidMultiplierServices | mutate(SET)           | 200        | -                              | -     
BulkServices(download)       | getBulkDownload       | -          | 1                              | -     
BulkServices(download)       | getBulkDownloadStatus | -          | 500                            | -     
BulkServices(upload)         | getUploadUrl          | -          | 1                              | -     
BulkServices(upload)         | getBulkUploadStatus   | -          | 500                            | -     
ReportDefinitionService      | get                   | -          |                         <  500 | ○     
ReportDefinitionService      | getReportFields       | 1          | 1                              | -     
ReportDefinitionService      | mutate(ADD)           | 1          | -                              | -     
ReportDefinitionService      | mutate(SET)           | 1          | -                              | -     
ReportDefinitionService      | mutate(REMOVE)        | 1          | -                              | -     
ReportService                | get                   | -          | 500                            | ○     
ReportService                | mutate(ADD)           | 20/アカウント   | -                              | -     
ReportService                | mutate(REMOVE)        | 20/アカウント   | -                              | -     
ReportService                | getDownloadUrl       |  20/アカウント   | -                              | -     
TargetingIdeaService         | get                   | -          | 500                            | ○     
TrafficEstimatorService      | get                   | -          | 100                            | -     
BidLandsacpeService          | get                   | -          | 100                            | -     
DictionaryService            | getDisapprovalReason  | -          | 全件取得可能                         | -     
DictionaryService            | getGeographicLocation | -          | 全件取得可能                         | -     
KeywordEstimatorService      | get                   | 500        | 500                            | -     
BiddingStrategyService       | get                   | -          | 500      | ○     
BiddingStrategyService       | mutate(ADD)           | 200        | -        | -     
BiddingStrategyService       | mutate(SET)           | 200        | -        | -     
BiddingStrategyService       | mutate(REMOVE)        | 200        | -        | -     
