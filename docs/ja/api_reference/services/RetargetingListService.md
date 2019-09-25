

# RetargetingListService

RetargetingListServiceでは、ターゲットリストに関する情報の取得および追加・更新を行います。

#### WSDL

| environment |                                      url                                      |
| ----------- | ----------------------------------------------------------------------------- |
| production  | https://ss.yahooapis.jp/services/V201909/RetargetingListService?wsdl |
| sandbox     | https://sandbox.ss.yahooapis.jp/services/V201909/RetargetingListService?wsdl  |

#### Namespace

http://ss.yahooapis.jp/V201909/RetargetingList

#### Service Overview

ターゲットリストに関する情報の取得および追加・更新を行います。

#### Operation

RetargetingListServiceで提供される操作を説明します。

+ [get](#get)
+ [getCustomKey](#getcustomkey)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)


## get

### リクエスト

ターゲットリストに関する情報を取得します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| selector | Yes | [RetargetingListSelector](../data/RetargetingList/RetargetingListSelector.md) |

### レスポンス

ターゲットリストに関する情報を取得します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [RetargetingListPage](../data/RetargetingList/RetargetingListPage.md) |

## getCustomKey

### リクエスト

カスタムキーに関する情報を取得します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| selector | Yes | [GetCustomKeySelector](../data/RetargetingList/GetCustomKeySelector.md) |

### レスポンス

カスタムキーに関する情報を取得します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [RetargetingListCustomKeyPage](../data/RetargetingList/RetargetingListCustomKeyPage.md) |

## mutate(ADD)

### リクエスト

ターゲットリストを追加します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| operations | Yes | [RetargetingListOperation](../data/RetargetingList/RetargetingListOperation.md) |

### レスポンス

ターゲットリストを追加します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [RetargetingListReturnValue](../data/RetargetingList/RetargetingListReturnValue.md) |

## mutate(SET)

### リクエスト

ターゲットリストを更新します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| operations | Yes | [RetargetingListOperation](../data/RetargetingList/RetargetingListOperation.md) |

### レスポンス

ターゲットリストを更新します。

| パラメータ | データ型 |
| -------- | ------- |
| rval | [RetargetingListReturnValue](../data/RetargetingList/RetargetingListReturnValue.md) |

