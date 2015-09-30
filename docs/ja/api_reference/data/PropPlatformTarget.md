# PropPlatformTarget
PropPlatformTargetオブジェクトは、トラフィック見積もり時の条件としてBid調整率を格納するコンテナです。
### Service
+ [TrafficEstimatorService](../services/TrafficEstimatorService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| platformName| <a href="../data/PlatformType.md">PlatformType</a>| プラットフォーム名です。 |
| bidMultiplier| xsd:double| Bid調整ができます。数値は0か0.10-4.00<br>・0: -100%（スマートフォン配信なし）<br>・0.10-4.00: -90%-+300%（スマートフォン調整あり）<br>※小数点2ケタまで入力してください<br>※上記の境界値を外れるか、小数点3ケタ以上を指定するとエラーになります。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
