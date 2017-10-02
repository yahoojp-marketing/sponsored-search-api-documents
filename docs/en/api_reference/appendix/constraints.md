# Value Constraints
The following table contains parameter values and constraints.  

### Entity Limits 
Entity                           | Constraints                         
---------------------------- | --------------------------- 
Account                        | Campaign per account 100  <br> Keywords per account 50,000                     
Campaign                       | Ad Groups per campaign 2,000
Ad Group                       | Keywords per ad group 2,000 <br>Ads per Ad Group 50                         
Negative Keyword                     | Negative keywords can be set  <br>5,000 at Campaign level<br>2,000 at Ad Group level  
Day of week/Hour targeting                 | Number of HourlyTargetings that can be Set per Day <br>6 (in intervals of 15 minutes)   
Report                         | Combinations of Filter Criteria 5 <br>Number of Filters Saved (not including filters that had been saved) 10<br>Templates List can be saved 30                         
Filter                   | can be save up to 10                         
Template               | can be saved up to 30      

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
Keyword                                      | 80 characters* 10 words                                         
Negative Keyword                             | 80 characters* 10 words                                                  
Campaign Budget                              | 100 to 12,500,000 JPY (in 100 JPY increments)                
Campaign                                     | 1 to 9,999 JPY (in 1 JPY increments)                            
Ad Group bid                                 | 1 to 50,000 JPY (in 1 JPY increments)                        
Keyword bid                                  | 1 to 50,000 JPY (in 1 JPY increments)                        
Account Budget                               | Minimum 3,000 (in 1,000 JPY increments)                      
Ad Schedule                                  | Can be specified in the range from today to December 31, 2037
Auto Bidding CPC                             | 0 to 50,000 JPY    
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

### Limitation of number of ID

ID | Scheduled report (Add Template: YES)| ONETIME report (Add Template: NO)           
----------- | ----------- |----------- 
Report ID　　　　| 30            　　　　| No limits.       
Report Job ID   | No limits.             | 50

*Once you hit the upper limit, you are no longer able to create a new ID.<br>
&nbsp;Please delete IDs by mutate Remove, if necessary.<br>
*Scheduled report IDs (AddTemplate YES) can be repeatedly used. <br>
&nbsp;ONETIME report IDs and Report Job IDs are deleted automatically in a week.<br>
*Maximum number of IDs set via API is a total number created by "on-behalf of" and "standard" authentication access.

### Maximum amount per request to be retrieved per service  
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
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>Yes</td>
 </tr>
 <tr>
  <td>BidLandscapeService</td>
  <td>get</td>
  <td>-</td>
  <td>100</td>
  <td>Yes</td>
 </tr>
 <tr>
  <td rowspan="4">BiddingStrategyService</td>
  <td>get</td>
  <td>-</td>
  <td>500</td>
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>all</td>
  <td>-</td>
 </tr>
 <tr>
  <td>getGeographicLocation</td>
  <td>-</td>
  <td>all</td>
  <td>-</td>
 </tr>
 <tr>
  <td rowspan="4">FeedFolderService</td>
  <td>get</td>
  <td>-</td>
  <td>50</td>
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>Yes</td>
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
  <td>Yes</td>
 </tr>
 <tr>
  <td>TrafficEstimatorService</td>
  <td>get</td>
  <td>-</td>
  <td>100</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
