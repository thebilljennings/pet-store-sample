# Place an order for a Pet

## 1. Get a Store's Inventory
A store's `inventory` object returns inventory status codes and quantities.
> **GET /store/inventory**
* **Summary:** Returns pet inventories by status
* **Description:** Returns a map of status codes quantities 
 
### Parameters
None

### Curl
  ```
  curl -X 'GET' \
    'https://petstore3.swagger.io/api/v3/store/inventory' \
    -H 'accept: application/json' 
  ```  
  
### Responses
| **Code** | **Description** |
| ------------- |:-------------:|
| 200 | successful operation |

### Example
```
{
  "additionalProp1": 0,
  "additionalProp2": 0,
  "additionalProp3": 0
}
```

## 2. Place an order for a Pet
A store's `order` object returns values based off the request body.
> **POST /store/order**
* **Summary:** Place an order for a pet
* **Description:** Place a new order in the store

### Parameters
None

### Request Body
* **id:** integer($int64)
* **petId:** integer($int64)
* **quantity:** integer($int32)
* **shipDate:** string($date-time)
* **status:** (string [placed, approved, delivered])
* **complete:** (boolean)

### Curl
  ```
  curl -X 'POST' \
  'https://petstore3.swagger.io/api/v3/store/order' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "id": 10,
  "petId": 198772,
  "quantity": 7,
  "shipDate": "2021-09-27T04:52:25.129Z",
  "status": "approved",
  "complete": true
  }' 
  ```  

### Responses
| **Code** | **Description** |
| ------------- |:-------------:|
| 200 | successful operation |
| 405 | Invalid input |

### Example
```
{
  "id": 10,
  "petId": 198772,
  "quantity": 7,
  "shipDate": "2021-09-27T05:05:33.402Z",
  "status": "approved",
  "complete": true
}
```

## 3. Confirm the order status with the store
