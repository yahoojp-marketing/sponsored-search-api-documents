# Value Constraints
The following table contains parameter values and constraints.  
### Entity Limits 
Entity                           | Constraints                         
---------------------------- | --------------------------- | -----
Account                        | Campaign per account 100  <br> Keywords per account 50,000                     
Campaign                       | Ad Groups per campaign 2,000
Ad Group                       | Keywords per ad group 2,000 <br>Ads per Ad Group 50                         
Negative Keyword                     | Negative keywords can be set  <br>5,000 at Campaign level<br>2,000 at Ad Group level  
Day of week/Hour targeting                 | Number of HourlyTargetings that can be Set per Day <br>6 (in intervals of 15 minutes)   
Report                         | Combinations of Filter Criteria 5 <br>Number of Filters Saved (not including filters that had been saved) 10<br>Templates List can be saved 30                         

### Charcter Lengh
*Regardless of whether one-byte or two-byte

Parameters                                   | Constraints
-------------------------------------------- | -------------------------------------------------------------
Account Name Length                          | 100 characters*                                              
Campaign Name Length                         | 50 characters*                                               
Ad Group Name                                | 50 characters*                                               
Ad Name                                      | 50 characters*                                               
Auto Bidding Name                            | 50 characters        
Headline                                     | 15 characters                                                
Description                                  | 19 characters - 19 characters                                
Display URL                                  | 29 characters                                                
Destination URL                              | 1024 characters                                              
Destination URL at keyword level(Custom URL) | 1024 characters                                              
Keyword                                      | 80 characters*                                               
Negative Keyword                             | 80 characters*                                               
Campaign Budget                              | 100 to 12,500,000 JPY (in 100 JPY increments)                
Bid limit for automatic bidding              | 1 to 9,999 JPY (in 1 JPY increments)                         
Ad Group bid                                 | 1 to 50,000 JPY (in 1 JPY increments)                        
Keyword bid                                  | 1 to 50,000 JPY (in 1 JPY increments)                        
Account Budget                               | Minimum 3,000 (in 1,000 JPY increments)                      
Ad Schedule                                  | Can be specified in the range from today to December 31, 2037
Target CPA of Auto Bidding                   | 0 to 99,999,999 JPY                      
Bid Adjustment                               | 0.10 to 10.00 (-90% to +900%)                      
Target ROAS                                  | 0.01 to 1,000.00 (1% to 100,000%)                      

*Specific symbols in CampaignName/AdGroupName/AdName are converted automatically as following.

Symbol  | Convert           | Example 
------- | ----------------- | ------------------
Double-byte space | Single-byte space | 「　」→「 」
Single-byte Japanese character | Double-byte Japanese character | ｱｲｳｴｵ → アイウエオ
Double-byte number | Single-byte number | １２３５ →　1235
Double-byte alpha character | Single-byte alpha character | ＡＢＣＤ → ABCD
Multi space | 1 single-byte space | 「あい　　うえお」→「あい うえお」
Leading and trailing space | Removed | 「　あいうえお　」→「あいうえお」

### Maximum amount per request to be retrieved per service  
Web Service                  | Operation             | No. of Usable Elements | Max. Responses | Paging
---------------------------- | --------------------- | ---------------------- | -------------- | ------
LocationServices             | get                   | -                      | 1              | -     
DictionaryServices           | getDisapprovalReason  | -                      | ALL            | -     
DictionaryServices           | getGeographicLocation | -                      | ALL            | -     
AccountServices              | get                   | -                      | 200            | ○     
AccountServices              | mutate(set)           | 200                    | -              | -     
BalanceServices              | get                   | -                      | 100            | ○     
ConversionTrackerServices    | get                   | -                      | 500            | ○     
ConversionTrackerServices    | mutate(ADD)           | 100                    | -              | -     
ConversionTrackerServices    | mutate(SET)           | 100                    | -              | -     
CampaignServices             | get                   | -                      | 500            | ○     
CampaignServices             | mutate(ADD)           | 200                    | -              | -     
CampaignServices             | mutate(SET)           | 200                    | -              | -     
CampaignServices             | mutate(REMOVE)        | 200                    | -              | -     
CampaignTargetService        | get                   | -                      | 500            | ○     
CampaignTargetService        | mutate(ADD)           | 200                    | -              | -     
CampaignTargetService        | mutate(SET)           | 200                    | -              | -     
CampaignTargetService        | mutate(REMOVE)        | 200                    | -              | -     
CampaignCriterionServices    | get                   | -                      | 500            | ○     
CampaignCriterionServices    | mutate(ADD)           | 200                    | -              | -     
CampaignCriterionServices    | mutate(REMOVE)        | 200                    | -              | -     
AdGroupServices              | get                   | -                      | 500            | ○     
AdGroupServices              | mutate(ADD)           | 200                    | -              | -     
AdGroupServices              | mutate(SET)           | 200                    | -              | -     
AdGroupServices              | mutate(REMOVE)        | 200                    | -              | -     
AdGroupCriterionServices     | get                   | -                      | 500            | ○     
AdGroupCriterionServices     | mutate(ADD)           | 200                    | -              | -     
AdGroupCriterionServices     | mutate(SET)           | 200                    | -              | -     
AdGroupCriterionServices     | mutate(REMOVE)        | 200                    | -              | -     
AdGroupAdServices            | get                   | -                      | 500            | ○     
AdGroupAdServices            | mutate(ADD)           | 200                    | -              | -     
AdGroupAdServices            | mutate(SET)           | 200                    | -              | -     
AdGroupAdServices            | mutate(REMOVE)        | 200                    | -              | -     
FeedItemServices             | get                   | -                      | 500            | ○     
FeedItemServices             | mutate(ADD)           | 200                    | -              | -     
FeedItemServices             | mutate(SET)           | 200                    | -              | -     
FeedItemServices             | mutate(REMOVE)        | 200                    | -              | -     
CampaignFeedServices         | get                   | -                      | 500            | ○     
CampaignFeedServices         | mutate(SET)           | 200                    | -              | -     
AdGroupFeedServices          | get                   | -                      | 500            | ○     
AdGroupFeedServices          | mutate(SET)           | 200                    | -              | -     
AdGroupBidMultiplierServices | get                   | -                      | 500            | ○     
AdGroupBidMultiplierServices | mutate(SET)           | 200                    | -              | -     
BulkServices(download)       | getBulkDownload       | -                      | 1              | -     
BulkServices(download)       | getBulkDownloadStatus | -                      | 500            | ○     
BulkServices(upload)         | getUploadUrl          | -                      | 1              | -     
BulkServices(upload)         | getBulkUploadStatus   | -                      | 500            | ○     
ReportDefinitionServices     | get                   | -                      | 500            | ○     
ReportDefinitionServices     | getReportFields       | -                      | 1              | -     
ReportDefinitionServices     | mutate(ADD)           | 1                      | -              | -     
ReportDefinitionServices     | mutate(SET)           | 1                      | -              | -     
ReportDefinitionServices     | mutate(REMOVE)        | 1                      | -              | -     
ReportServices               | get                   | -                      | 500            | ○     
ReportServices               | mutate(ADD)           | 20 per account         | -              | -     
ReportServices               | mutate(REMOVE)        | 20 per account         | -              | -     
ReportServices               | getDownloadUrl        | 20 per account         | -              | -     
TrafficEstimatorServices     | get                   | -                      | 100            | -     
KeywordEstimatorServices     | get                   | -                      | 100            | -     
TargetingIdeaServices        | get                   | -                      | 500            | ○     
BidLandscapeServices         | get                   | -                      | 100            | -     
BiddingStrategyService       | get                   | -                      | 500            | ○     
BiddingStrategyService       | mutate(ADD)           | 200                    | -              | -     
BiddingStrategyService       | mutate(SET)           | 200                    | -              | -     
BiddingStrategyService       | mutate(REMOVE)        | 200                    | -              | -     
