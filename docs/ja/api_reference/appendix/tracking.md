# トラッキングパラメータ
スポンサードサーチAPIでは、ユーザーがどの種類の広告をクリックしてサイトを訪れたかの情報をトラッキングパラメータで知ることができます。<br>
クリックされた広告タイプを知ることで広告の効果を確認でき、よりよい広告の出力につなげることが可能になります。<br>
<br>
本トラッキング機能は、スポンサードサーチ APIをご利用のサードパーティ製ツール向けに提供される機能です。<br>
本機能のご利用は、取得データを自社ツールの効果測定機能において一次利用する場合に限り認められます。<br>
取得データの貴社顧客への直接の提供譲渡および転売等、二次利用は認められません。<br>
<br>
アプリ広告のリンク先URLにトラッキング用パラメーターを設定した場合、コンバージョンは正しく計測できません。<br>
Android 向けアプリケーションのダウンロードは、広告が Google Play Store に直接リンクしている場合のみトラッキングできます。<br>
<br>

パラメータ | 概要 | URLフォーマット例
----------- | ----------------- | ---------------- 
creative | 広告ID（adTrackID）です。<br>※adTrackIDとは各広告にユニークに付与されるIDです。広告IDとは異なります。 | http://www.example.com/?creative={creative} 
keyword | 入札キーワードです。| http://www.example.com/?keyword={keyword} 
matchtype | マッチタイプです。表示内容は以下の通りです。<br>・e：完全一致<br>・p：フレーズ一致<br>・b：部分一致<br>|http://www.example.com/?matchtype={matchtype} 
device | クリックされたデバイスの種類です。表示内容は以下の通りです。<br>・m：スマートフォンとモバイル<br>・t：タブレット<br>・c：PC | http://www.example.com/?device={device}
ifmobile | スマートフォンやモバイルからクリックされた場合、事前に設定した値が返されます。<br>※カスタムURLにのみ設定頂けます。<br>※広告表示オプションのQuickLinkでも利用可能です。 | http://www.example.com/?ifmobile={ifmobile:[value]}
ifnotmobile|タブレットやPCからクリックされた場合、事前に設定した値が返されます。<br>※カスタムURLにのみ設定頂けます。<br>※広告表示オプションのQuickLinkでも利用可能です。|http://www.example.com/?ifnotmobile={ifnotmobile:[value]}
lpurl | 最終リンク先URLです。トラッキングURLへの設定の際にご利用いただけます。<br>※アドバンスドURL対応されたエンティティのみご利用 可能です。|・最終リンク先URL：http://example.com<br>・トラッキングURL設定：{lpurl}?creative=XXXXXXXX<br>・配信時URL：<br>http://www.example.com/?creative=XXXXXXXX

