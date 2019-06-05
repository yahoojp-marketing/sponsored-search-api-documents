# トラッキングパラメータ
スポンサードサーチAPIでは、ユーザーがどの種類の広告をクリックしてサイトを訪れたかの情報を得るために、トラッキングパラメータを利用できます。クリックされた広告の詳細を知ることで広告の効果を確認でき、よりよい広告の出力につなげることが可能です。<br>
スポンサードサーチAPIで利用できるトラッキングパラメータは、以下のとおりです。<br><br>
<b>■ご注意</b><br>
・本機能は、スポンサードサーチ APIをご利用のサードパーティ製ツール向けに提供しています。本機能のご利用は、取得データを自社ツールの効果測定機能において一次利用する場合に限り認められます。取得データの顧客への直接の提供譲渡や、転売等の二次利用は認められません。<br>
・アプリダウンロード広告のコンバージョン測定は、Androidアプリにのみ可能です。また、広告から直接「Google Playストアアプリ」を経由してダウンロードした場合のみコンバージョン測定が可能で、ブラウザー版「Google Playストア」からのダウンロードは測定対象外です。<br>
<br>

| パラメータ | 概要 | URLフォーマット例 |
| ----------- | ----------------- | ---------------- |
| creative | 広告トラッキングID <br>各広告に付与されるトラッキング用のIDです。広告IDとは異なります。| 最終リンク先URL <br> http://www.example.com/?creative={creative}  <br> トラッキングURL <br> http://www.example.com/?lp={lpurl}&creative={creative} |
| keyword | 入札キーワード | 最終リンク先URL <br> http://www.example.com/?keyword={keyword} <br> トラッキングURL <br> http://www.example.com/?lp={lpurl}&keyword={keyword} |
| matchtype | キーワードのマッチタイプ <br> e：完全一致 <br> p：フレーズ一致 <br> b：部分一致 | 最終リンク先URL <br> http://www.example.com/?matchtype={matchtype} <br> トラッキングURL <br> http://www.example.com/?lp={lpurl}&matchtype={matchtype} |
| device | デバイスの種類 <br> m：スマートフォンとモバイル <br> t：タブレット <br> c：PC | 最終リンク先URL <br> http://www.example.com/?device={device} <br> トラッキングURL <br> http://www.example.com/?lp={lpurl}&device={device} |
| targetid | ターゲット設定トラッキングID <br> 広告配信時のキーワードID（kwd）、およびサイトリターゲティング のターゲットリストID（aud）を表示します。 <br> 例：広告配信時にターゲットリストIDが456、キーワードIDが123の場合、{targetid}には「aud-456:kwd-123」と表示されます。 | 最終リンク先URL <br> http://www.example.com/?targetid={targetid} <br> トラッキングURL <br> http://www.example.com/?lp={lpurl}&targetid={targetid} |
| campaignid | キャンペーントラッキングID <br> 各キャンペーンに付与されるトラッキング用のIDです。キャンペーンIDとは異なります。 | 最終リンク先URL <br> http://www.example.com/?campaignid={campaignid} <br> トラッキングURL <br> http://www.example.com/?lp={lpurl}&campaignid={campaignid} |
| adgroupid | 広告グループトラッキングID <br> 各広告グループに付与されるトラッキング用のIDです。広告グループIDとは異なります。 | 最終リンク先URL <br> http://www.example.com/?adgroupid={adgroupid} <br> トラッキングURL <br> http://www.example.com/?lp={lpurl}&adgroupid={adgroupid} |
| feeditemid | 広告表示オプショントラッキングID <br> 各広告表示オプション（クイックリンク、テキスト補足など）の設定ごとに付与されるトラッキング用のIDです。広告表示オプションIDとは異なります。 | 最終リンク先URL <br> http://www.example.com/?feeditemid={feeditemid} <br> トラッキングURL <br> http://www.example.com/?lp={lpurl}&feeditemid={feeditemid} |
| adposition | 広告が掲載されたページ内の位置 <br> 例：「1t2」は、1 ページ目、上部、掲載順位 2 位を示します。 | 最終リンク先URL <br> http://www.example.com/?adposition={adposition} <br> トラッキングURL <br> http://www.example.com/?lp={lpurl}&adposition={adposition} |
| ifmobile | このパラメータを設定すると、スマートフォンからのアクセス時に任意の値をURLに付加できます。これにより、スマートフォン向けURLへの変換やパラメータの追加などが可能です。<br>※最終リンク先URL、トラッキングURL、カスタムパラメータに設定できます。 | http://www.example.com/?ifmobile={ifmobile:[value]} |
| ifnotmobile | このパラメータを設定すると、PC・タブレットからのアクセス時に任意の値をURLに付加できます。これにより、PC・タブレット向けURLへの変換やパラメータの追加などが可能です。<br>※最終リンク先URL、トラッキングURL、カスタムパラメータに設定できます。 | http://www.example.com/?ifnotmobile={ifnotmobile:[value]} |
| lpurl | 設定した箇所に最終リンク先URLを挿入します。トラッキングURLに設定できます。 | 最終リンク先URLが <br> http://www.example.com /?param=1　の場合 <br> ・トラッキングURL： <br> http://www.example.com /?lp={lpurl} <br> ・広告クリック後のURL： <br> http://www.example.com /?lp=http://www.example.com /%3Fparam%3D1 |
| lpurl+2 | lpurl（最終リンク先URL）を含むトラッキングURLで、「?」「=」「“」「#」「\t」「‘」とスペースのエンコードが2回必要な場合に利用できます。 | 最終リンク先URLが <br> http://www.example.com/?param=1　の場合 <br> ・トラッキングURL： <br> http://www.example.com/?lp={lpurl+2} <br> ・広告クリック後のURL： <br> http://www.example.com/?lp=http://www.example.com/%253Fparam%253D1 |
| lpurl+3 | lpurl（最終リンク先URL）を含むトラッキングURLで、「?」「=」「“」「#」「\t」「‘」とスペースのエンコードが3回必要な場合に利用できます。 | 最終リンク先URLが <br> http://www.example.com /?param=1　の場合 <br> ・トラッキングURL： <br> http://www.example.com/?lp={lpurl+3} <br> ・広告クリック後のURL： <br> http://www.example.com/?lp=http://www.example.com/%25253Fparam%25253D1 |
| unescapedlpurl | lpurl（最終リンク先URL）を含むトラッキングURLで、lpurlをエンコードしない場合に利用できます。 <br> URLの先頭でのみ設定可能です。| 最終リンク先URLが <br> http://www.example.com/?param=1　の場合 <br> ・トラッキングURL： <br> {unescapedlpurl}&param2=2 <br> ・広告クリック後のURL： <br> http://www.example.com/?param=1&param2=2 |
| escapedlpurl | lpurl（最終リンク先URL）を含むトラッキングURLで、lpurlの「:」「/」「?」「=」「%」をエンコードする場合に利用できます。 | 最終リンク先URLが <br> http://www.example.com/?param=1　の場合 <br> ・トラッキングURL： <br> http://www.example.com/?lp={escapedlpurl} <br> 広告クリック後のURL <br> http://www.example.com/?lp=http:%3A%2F%2Fwww.example.com%2F%3Fparam%3D |
| escapedlpurl+2 | lpurl（最終リンク先URL）を含むトラッキングURLで、lpurlの「:」「/」「?」「=」「%」を2回エンコードする場合に利用できます。 | 最終リンク先URLが <br> http://www.example.com/?param=1　の場合 <br> ・トラッキングURL： <br> http://www.example.com/?lp={escapedlpurl+2} <br> ・広告クリック後のURL： <br> http://www.example.com/?lp=http:%253A%252F%252Fwww.example.com%252F%253Fparam%253D1 |
| escapedlpurl+3 | lpurl（最終リンク先URL）を含むトラッキングURLで、lpurlの「:」「/」「?」「=」「%」を3回エンコードする場合に利用できます。 | 最終リンク先URLが <br> http://www.example.com/?param=1　の場合 <br> ・トラッキングURL： <br> http://www.example.com/?lp={escapedlpurl+3} <br> ・広告クリック後のURL： <br> http://www.example.com/?lp=http:%25253A%25252F%25252Fwww.example.com%25252F%25253Fparam%25253D1 |
