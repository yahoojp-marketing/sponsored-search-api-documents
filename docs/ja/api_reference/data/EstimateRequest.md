# EstimateRequest
EstimateRequestオブジェクトは、見積もりのリクエストを格納するコンテナです。
### Service
+ [TrafficEstimatorService](../services/TrafficEstimatorService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| target| <a href="../data/EstimateTarget.md">EstimateTarget</a>| 見積もりに必要なターゲット条件を指定します。 |
| keyword| <a href="../data/EstimateKeyword.md">EstimateKeyword</a>| 見積もりに必要なキーワードに関する条件を指定します。 |
| bid| xsd:long| 見積もるときの入札単価です。 |
| platform[]| <a href="../data/PropPlatformTarget.md">PropPlatformTarget</a>| デバイスの設定ができます。<br>※ひとつしかリクエストを受け付けません。 |
| wap| enum <a href="../data/Wap.md">Wap</a>| モバイルデバイス向けの広告の設定ができます。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
