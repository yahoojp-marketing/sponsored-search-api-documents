# GeographicLocation
GeographicLocation contains geographic location information.
### Service
+ [DictionaryService](../services/DictionaryService.md)

| Field | Data Type | Description | 
|---|---|---|
| code| xsd:string| Geographic code |
| parent| xsd:string| Parent geographic code |
| name| xsd:string| Name of places (City Only) |
| fullName| xsd:string| Name of places (Prefecture and all) |
| order| xsd:string| Order of list<br><br>			Sequential number based on the order below.<br><br>			- Prefecture is in order of Hokkaido, Aomori to Okinawa. (North to South)<br><br>			- Cities under prefecture are listed in the order of the 50-character Japanese kana syllabary. |
| status| enum <a href="./GeographicLocationStatus.md">GeographicLocationStatus</a>| Status of geographic location |
| child| <a href="./GeographicLocation.md">GeographicLocation</a>| Child geographic location. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
