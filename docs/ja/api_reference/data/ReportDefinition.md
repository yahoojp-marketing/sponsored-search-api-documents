# ReportDefinition
ReportDefinitionオブジェクトは、レポート定義を表します。
### Service
+ [ReportDefinitionService](../services/ReportDefinitionService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| reportId(notupdatable)| xsd:long| レポート定義のIDです。| ─| Req| Req |
| accountId(notupdatable)| xsd:long| アカウントIDです。| Req| Req| Req |
| campaignIds[]| xsd:long| キャンペーンIDの配列です。| Opt| ─| ─ |
| adGroupIds[]| xsd:long| 広告グループIDの配列です。| Opt| ─| ─ |
| kwIds[]| xsd:long| キーワードIDの配列です。| Opt| ─| ─ |
| adIds[]| xsd:long| 広告IDの配列です。| Opt| ─| ─ |
| feedItemIds[]| xsd:long| FeedItem情報のIDです。| Opt| ─| ─ |
| feedFolderIds[]| xsd:long| Feedフォルダ情報のIDです。| Opt| ─| ─ |
| biddingStrategyIds[]| xsd:long| 自動入札IDです。| Opt| ─| ─ |
| targetListIds[]| xsd:long| ターゲットリストIDです。| Opt| ─| ─ |
| reportName| xsd:string| ユーザーにより設定されるレポート名です。| Req| Opt| ─ |
| reportType| enum <a href="../data/ReportType.md">ReportType</a>| レポートの種類です。| Req| ─| ─ |
| dateRangeType| enum <a href="../data/ReportDateRangeType.md">ReportDateRangeType</a>| 定義されたレポートの集計対象期間です。| Req| ─| ─ |
| dateRange| <a href="../data/ReportDateRange.md">ReportDateRange</a>| ユーザーにより設定されるレポート集計の範囲期間です。dataRangeTypeがCUSTOM_DATEの場合必須項目になります。| Opt| ─| ─ |
| filters[]| <a href="../data/ReportFilter.md">ReportFilter</a>| レポートのフィルタ条件です。| Opt| ─| ─ |
| segments[]| xsd:string| グループ化するフィルタ条件です。<br>詳細は<a href="../appendix/reports.md#%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%82%BB%E3%82%B0%E3%83%A1%E3%83%B3%E3%83%88"><span>レポートセグメント</span></a>を参照してください。| Opt| ─| ─ |
| sort| xsd:string| フィールド名を指定し、昇順または降順でソートします。ソートの指定はフィールド名の頭に半角で「+」か「-」を指定します。<br>フィールド名は、<a href="../services/ReportDefinitionService.md#cNavigetReportFields"><span>getReportFields</span></a>で取得します。| Req| ─| ─ |
| fields[]| xsd:string| フィールド（レポートの項目名）です。getReportFieldsで取得した値を指定します。| Req| ─| ─ |
| format| enum <a href="../data/ReportDownloadFormat.md">ReportDownloadFormat</a>| 定義されたダウンロードレポートのファイル形式です。| Req| ─| ─ |
| encode| enum <a href="../data/ReportDownloadEncode.md">ReportDownloadEncode</a>| 定義されたダウンロードレポートの文字コードです。| Req| ─| ─ |
| zip| enum <a href="../data/ReportZip.md">ReportZip</a>| ダウンロードレポートを圧縮／非圧縮を指定します。| Req| ─| ─ |
| lang| enum <a href="../data/ReportLang.md">ReportLang</a>| 定義されたカラム名の言語です。| Opt| ─| ─ |
| frequency| enum <a href="../data/ReportFrequency.md">ReportFrequency</a>| 定期レポートの作成タイミングです。| Opt| ─| ─ |
| specifyDay| xsd:int| 特定の日付です。ReportFrequencyでSPECIFYDAYを指定した場合、必須項目です。| Opt| Opt| ─ |
| addTemplate| enum <a href="../data/ReportAddTemplate.md">ReportAddTemplate</a>| レポートのテンプレートとして追加するかを指定します。テンプレートで登録できる数は標準認証と代行認証の合計で30個までとなります。標準認証と代行認証でテンプレートを共有はすることはできません。| Req| ─| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
