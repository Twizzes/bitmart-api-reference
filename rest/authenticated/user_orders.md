# List Orders

Get a list of user orders.

### Sample Request \(Python\)

```py
import requests

url = "https://api.bitmart.com/v2/orders?symbol=BMX_ETH&status=0&offset=0&limit=100"

// timestamp is in milliseconds and the authorization header is "Bearer " + token
headers = {"X-BM-TIMESTAMP": xxx, "X-BM-AUTHORIZATION": "xxx"}

response = requests.get(url, headers=headers)

print(response.text)
```

### Sample Response

```js
{
   "orders":[
      {
         "entrust_id":1223181,
         "symbol":"BMX_ETH",
         "timestamp":1528060666000,
         "side":"buy",
         "price":"1.000000",
         "fees":"0.1",
         "original_amount":"1",
         "executed_amount":"1",
         "remaining_amount":"0",
         "status":3
      }
   ],
   "total_pages":1,
   "total_orders":1,
   "current_page":0,
}
```

#### Request Parameter

| Parameter | Type | Description |
| :--- | :--- | :--- |
| symbol | query | Trading pair symbol (optional, if null, return orders of all symbols) |
| status | query | Integer enum, please check the table below |
| offset | query | Current page, which starts from 0 |
| limit | query | Maximum size of the results in one page, less than 100 |


#### Status Type
| Status | Description |
| :--- | :--- |
| 0 | All orders |
| 1 | Pending orders |
| 2 | Partially successful orders |
| 3 | Success orders |
| 4 | Canceled orders |
| 5 | Pending and partially successful orders |
| 6 | Success and canceled orders |



#### Response Details

| Key | Type | Description |
| :--- | :--- | :--- |
| orders | array | List of orders |
| entrust_id | string | Order id |
| symbol | string | Trading pair symbol |
| timestamp | string | Order create time (in milliseconds) |
| side | string | 'buy' or 'sell' |
| price | string | Price of the order |
| fees | string | Fees of the order |
| original_amount | string | Order amount |
| executed_amount | string | Successful amount |
| remaining_amount | string | Remaining amount |
| total_pages | string | Total number of pages in that status |
| total_orders | string | Total number of orders in that status |
| current_page | string | Current page number |
| status | string | Integer enum, please check the table above |




