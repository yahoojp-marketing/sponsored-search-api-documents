

# RetargetingListService

RetargetingListService is to get, add, or update information of target list.

#### WSDL

| environment |                                      url                                      |
| ----------- | ----------------------------------------------------------------------------- |
| production  | https://ss.yahooapis.jp/services/V201909/RetargetingListService?wsdl |
| sandbox     | https://sandbox.ss.yahooapis.jp/services/V201909/RetargetingListService?wsdl  |

#### Namespace

http://ss.yahooapis.jp/V201909/RetargetingList

#### Service Overview

RetargetingListService provides operation of target list.

#### Operation

Explains operations provided by RetargetingListService.

+ [get](#get)
+ [getCustomKey](#getcustomkey)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)


## get

### Request

Retrieves the target list information.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| selector | Yes | [RetargetingListSelector](../data/RetargetingList/RetargetingListSelector.md) |

### Response

Retrieves the target list information.

| Parameter | Data Type |
| -------- | ------- |
| rval | [RetargetingListPage](../data/RetargetingList/RetargetingListPage.md) |

## getCustomKey

### Request

Get custom key information.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| selector | Yes | [GetCustomKeySelector](../data/RetargetingList/GetCustomKeySelector.md) |

### Response

Get custom key information.

| Parameter | Data Type |
| -------- | ------- |
| rval | [RetargetingListCustomKeyPage](../data/RetargetingList/RetargetingListCustomKeyPage.md) |

## mutate(ADD)

### Request

Adds target list.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| operations | Yes | [RetargetingListOperation](../data/RetargetingList/RetargetingListOperation.md) |

### Response

Adds target list.

| Parameter | Data Type |
| -------- | ------- |
| rval | [RetargetingListReturnValue](../data/RetargetingList/RetargetingListReturnValue.md) |

## mutate(SET)

### Request

Updates the target list.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| operations | Yes | [RetargetingListOperation](../data/RetargetingList/RetargetingListOperation.md) |

### Response

Updates the target list.

| Parameter | Data Type |
| -------- | ------- |
| rval | [RetargetingListReturnValue](../data/RetargetingList/RetargetingListReturnValue.md) |

