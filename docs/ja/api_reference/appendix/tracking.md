# トラッキングパラメータ
スポンサードサーチAPIでは、ユーザーがどの種類の広告をクリックしてサイトを訪れたかの情報をトラッキングパラメータで確認できます。<br>
クリックされた広告タイプを知ることで広告の効果を確認でき、よりよい広告の出力につなげることが可能です。<br>
<br>
本トラッキング機能は、スポンサードサーチ APIをご利用のサードパーティ製ツール向けに提供される機能です。<br>
本機能のご利用は、取得データを自社ツールの効果測定機能において一次利用する場合に限り認められます。<br>
取得データの貴社顧客への直接の提供譲渡および転売等、二次利用は認められません。<br>
<br>
アプリ広告のリンク先URLにトラッキングパラメータを設定した場合、コンバージョンは正しく計測できません。<br>
Android 向けアプリケーションのダウンロードは、広告が Google Play Store に直接リンクしている場合のみトラッキングできます。<br>
<br>

パラメータ | 概要 | URLフォーマット例
----------- | ----------------- | ---------------- 
creative | 広告トラッキングID（adTrackId）です。<br>※各広告にユニークに付与されるIDです。広告ID（adId）とは異なります。| http://www.example.com/?creative={creative} 
keyword | 入札キーワードです。| http://www.example.com/?keyword={keyword} 
matchtype | マッチタイプです。表示内容は以下の通りです。<br>・e：完全一致<br>・p：フレーズ一致<br>・b：部分一致<br>|http://www.example.com/?matchtype={matchtype} 
device | クリックされたデバイスの種類です。表示内容は以下の通りです。<br>・m：スマートフォンとモバイル<br>・t：タブレット<br>・c：PC | http://www.example.com/?device={device}
ifmobile | このパラメータを設定すると、スマートフォンからのアクセス時に任意の値をURLに付加できます。これにより、スマートフォン向けURLへの変換やパラメータの追加などが可能です。<br>※キーワード、広告、クイックリンクオプションの最終リンク先URLに設定できます。| http://www.example.com/?ifmobile={ifmobile:[value]}
ifnotmobile | このパラメータを設定すると、PC・タブレットからのアクセス時に任意の値をURLに付加できます。これにより、PC・タブレット向けURLへの変換やパラメータの追加などが可能です。<br>※キーワード、広告、クイックリンクオプションの最終リンク先URLに設定できます。 | http://www.example.com/?ifnotmobile={ifnotmobile:[value]}
lpurl|最終リンク先URLです。トラッキングURLへの設定の際に利用できます。<br>アドバンスドURL対応済みのエンティティのみ利用可能です。|・最終リンク先URL：<br>http://www.yahoo.co.jp/?param=1<br>・トラッキングURL：<br>http://www.yahoo.co.jp/?lp={lpurl}<br>・広告クリック後のURL：<br>http://www.yahoo.co.jp/?lp=http://www.yahoo.co.jp/%3Fparam%3D1
lpurl+2|lpurl（最終リンク先URL）を含むトラッキングURLで、「?」「=」「“」「#」「\t」「‘」とスペースのエンコードが2回必要な場合に利用できます。<br>アドバンスドURL対応済みのエンティティのみ利用可能です。|最終リンク先URL：<br>http://www.yahoo.co.jp/?param=1<br>・トラッキングURL：<br>http://www.yahoo.co.jp/?lp={lpurl+2}<br>・広告クリック後のURL：<br>http://www.yahoo.co.jp/?lp=http://www.yahoo.co.jp/%253Fparam%253D1
lpurl+3|lpurl（最終リンク先URL）を含むトラッキングURLで、「?」「=」「“」「#」「\t」「‘」とスペースのエンコードが3回必要な場合に利用できます。<br>アドバンスドURL対応済みのエンティティのみ利用可能です。|・最終リンク先URL：<br>http://www.yahoo.co.jp/?param=1<br>・トラッキングURL：<br>http://www.yahoo.co.jp/?lp={lpurl+3}<br>・広告クリック後のURL：<br>http://www.yahoo.co.jp/?lp=http://www.yahoo.co.jp/%25253Fparam%25253D1
unescapedlpurl|lpurl（最終リンク先URL）を含むトラッキングURLで、lpurlをエンコードしない場合に利用できます。URLの先頭でのみ設定可能です。<br>アドバンスドURL対応済みのエンティティのみ利用可能です。|・最終リンク先URL：<br>http://www.yahoo.co.jp/?param=1<br>・トラッキングURL：<br>{unescapedlpurl}&param2=2<br>・広告クリック後のURL：<br>http://www.yahoo.co.jp/?param=1&param2=2
escapedlpurl|lpurl（最終リンク先URL）を含むトラッキングURLで、lpurlの「:」「/」「?」「=」「%」をエンコードする場合に利用できます。<br>アドバンスドURL対応済みのエンティティのみ利用可能です。|・最終リンク先URL：<br>http://www.yahoo.co.jp/?param=1<br>・トラッキングURL：<br>http://www.yahoo.co.jp/?lp={escapedlpurl}<br>広告クリック後のURL <br>http://www.yahoo.co.jp/?lp=http:%3A%2F%2Fwww.yahoo.co.jp%2F%3Fparam%3D1
escapedlpurl+2|lpurl（最終リンク先URL）を含むトラッキングURLで、lpurlの「:」「/」「?」「=」「%」を2回エンコードする場合に利用できます。<br>アドバンスドURL対応済みのエンティティのみ利用可能です。|・最終リンク先URL：<br>http://www.yahoo.co.jp/?param=1<br>・トラッキングURL：<br>http://www.yahoo.co.jp/?lp={escapedlpurl+2}<br>・広告クリック後のURL：<br>http://www.yahoo.co.jp/?lp=http:%253A%252F%252Fwww.yahoo.co.jp%252F%253Fparam%253D1
escapedlpurl+3|lpurl（最終リンク先URL）を含むトラッキングURLで、lpurlの「:」「/」「?」「=」「%」を3回エンコードする場合に利用できます。<br>アドバンスドURL対応済みのエンティティのみ利用可能です。|・最終リンク先URL：<br>http://www.yahoo.co.jp/?param=1<br>・トラッキングURL：<br>http://www.yahoo.co.jp/?lp={escapedlpurl+3}<br>・広告クリック後のURL：<br>http://www.yahoo.co.jp/?lp=http:%25253A%25252F%25252Fwww.yahoo.co.jp%25252F%25253Fparam%25253D1

