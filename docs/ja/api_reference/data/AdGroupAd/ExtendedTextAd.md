

# ExtendedTextAd

ExtendedTextAdオブジェクトは、拡大テキスト広告に関する情報を表します。

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

### Inheritance

+ [Ad](./Ad.md)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| headline2 | xsd:string | 2行目のタイトルです。 | yes | - | Requirement | - | - | |
| path1 | xsd:string | 自動作成される表示URLを補足するパスです。<br/>※path2を指定する場合は、path1は必須。 | yes | - | Optional<br/>※default:null | - | - | |
| path2 | xsd:string | 自動作成される表示URLを補足するパスです。<br/>※path1を指定していない場合、path2はIgnore。 | yes | - | Optional<br/>※default:null | - | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
