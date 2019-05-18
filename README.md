# shopper

![](xmind.png)
<br><br>
API documentation
<br><br>

### Notes:

```
user able to view all products but add to products to the cart and checkout the products you need to sign in or sign up.

request status code:
- 200 OK
- 400 bad request // param issue
- 401 unauthed // header: token issue
- 404 not found // url issue
```

### Login

Link:[/api/v1/auth/login/]()
<br><br>
Method: **POST**
<br><br>
**BODY**
<br><br>
email: Required
<br><br>
password: Required
<br><br>
Response :

```
{
"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVjODE1NmY4NjA3M2U3NTU1MDhlZDNjMiIsImlhdCI6MTU1MjY1NTIwMSwiZXhwIjoxNTU1MDc0NDAxfQ.gTX4y6LrEWHOSFWk60lHzrdTeV3K10iXpTLbAN2nNCc" // cache it
}
```


### Registration

Link:[/api/v1/auth/registration/]()
<br><br>
Method: **POST**
<br><br>
**BODY**
<br><br>
name: Required
<br><br>
email: Required
<br><br>
password: Required
<br><br>
phone_number: Required
<br><br>
province_id: Required
<br><br>
city_id: Required
<br><br>
Response :

```
{
"msg": "Check Your Email.."
}
```

### Active Email

Link:[/api/v1/auth/active_email/]()
<br><br>
Method: **POST**
<br><br>
**BODY**
<br><br>
activition_code: Required
<br><br>
Response :

```
{
"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVjODE1NmY4NjA3M2U3NTU1MDhlZDNjMiIsImlhdCI6MTU1MjY1NTIwMSwiZXhwIjoxNTU1MDc0NDAxfQ.gTX4y6LrEWHOSFWk60lHzrdTeV3K10iXpTLbAN2nNCc" // cache it
}
```

### forget password

Link:[/api/v1/auth/forget_password/]()
<br><br>
Method: **POST**
<br><br>
**BODY**
<br><br>
email: Required
<br><br>
Response :

```
{
    "msg": "Check Your Email.."
}
```

### set new password

Link:[/api/v1/auth/set_new_password/]()
<br><br>
Method: **POST**
<br><br>
**BODY**
<br><br>
activition_code: Required
<br><br>
new_password: Required
<br><br>
Response :

```
{
"msg": "sign in again.."
}
```

### Get profile

Link:[api/v1/profile/]()
<br><br>
Method: **GET**
<br><br>
Response :

```
{
  "profile":
    {
      "id": 1,
      "name":"",
      "email":"",
      "province":"",
      "city":"",
      "phone_number":""
    }
}
```

<br><br>

### Edit User Info

Link:[/api/v1/edit_user_info/]()
<br><br>
Method: **POST**
<br><br>
**BODY**
<br><br>
name: Required
<br><br>
phone_number: Required
<br><br>
province_id: Required
<br><br>
city_id: Required
<br><br>
Response :

```
{
"msg": "done"
}
```

### Get sections

Link:[api/v1/sections/]()
<br><br>
Method: **GET**
<br><br>
Response :

```
{
  "sections":[{
      "id": 1,
      "name":"",
      "icon":"url"
    }]
}
```

<br><br>

### Get categories

Link:[api/v1/categories]()
<br><br>
Method: **GET**
<br><br>
**Param**
<br><br>
section_id: Required
<br><br>
Response :

```
{
  "categories":[{
      "id": 1,
      "name":"",
      "image":"url"
    }]
}
```

<br><br>

### get products

Link:[api/v1/products]()
<br><br>
Method: **GET**
<br><br>
**Param**
<br><br>
category_id: Required
<br><br>
Response :

```
{
  "products":[{
      "id": 1,
      "title":"",
      "image":"url",
      "price":10000,
      "discount":50,
      "des":"",
      "is_summer":true,
      "is_active":true,
      "search_count":123,
      "view_count":234,
      "is_coming_soon":true,
      "stock":123,
      "arrival_time":234,
       "prices":[{
            "price_id":"xxxxxxx"
            "image": "slug",
            "price": 30000,
            "description": "New XL"
      }]
    }]
}
```

<br><br>

### banners

Link:[api/v1/home/banners/]()
<br><br>
Method: **GET**
<br><br>
Response :

```
{
    "banners": [
     {
       "id": 1,
       "image": "https//:imagelink.com",
       "title": "",
       "description": "",
       "parentId": 1,
       "parentType": 1,
     }
  ]
}
```

<br><br>

### discount_items

Link:[api/v1/home/discount_items/]()
<br><br>
Method: **GET**
<br><br>
Response :

```
{
   "discount_items":{
    "label" : "Discount Items",
    "data" : [
     {
       "id": 1,
       "image": "",
       "title": "",
       "description": "",
       "price": 212,
       "categoryId": 1,
     }
  ]}
}
```

<br><br>

### coming_soon

Link:[api/v1/home/coming_soon/]()
<br><br>
Method: **GET**
<br><br>
Response :

```
{
    "coming_soon":{
    "label" : "Coming Soon",
    "data" : [
     {
       "id": 1,
       "image": "",
       "title": "",
       "description": "",
       "price": 212,
       "categoryId": 1,
     }
  ]}
}
```

<br><br>

### most_viewed

Link:[api/v1/home/most_viewed/]()
<br><br>
Method: **GET**
<br><br>
Response :

```
{
    "most_viewed":{
    "label" : "Most View",
    "data" :  [
       {
       "id": 1,
       "image": "",
       "title": "",
       "description": "",
       "price": 212,
       "categoryId": 1,
     }
  ]}
}
```

<br><br>

### most_searched

Link:[api/v1/home/most_searched/]()
<br><br>
Method: **GET**
<br><br>
Response :

```
{
    "most_searched":{
    "label" : "Most View",
    "data" :  [
       {
       "id": 1,
       "image": "",
       "title": "",
       "description": "",
       "price": 212,
       "categoryId": 1,
     }
  ]}
}
```

<br><br>

### new_items

Link:[api/v1/home/new_items/]()
<br><br>
Method: **GET**
<br><br>
Response :

```
{
    "new_items":{
    "label" : "New Items",
    "data" :  [
     {
       "id": 1,
       "image": "",
       "title": "",
       "description": "",
       "price": 212,
       "categoryId": 1,
     }
  ]}
}
```

<br><br>

### Get provinces

Link:[api/v1/provinces/]()
<br><br>
Method: **GET**
<br><br>
Response :

```
{
"provinces":
 [{
  "province_name":"",
  "province_id": 12
  }]
}
```

<br><br>

### Get cities

Link:[api/v1/provinces]()
<br><br>
Method: **GET**
<br><br>
**Param**
<br><br>
province_id: Required
<br><br>
Response :

```
{
  "cities":
  [{
  "city_name":"" ,
  "city_id":13
}]
}
```

<br><br>

### Add Product To the cart

Link:[/api/v1/cart/add/]()
<br><br>
Method: **POST**
<br><br>
**BODY**
<br><br>
price_id: Required
<br><br>
quantity: Required
<br><br>
Response :

```
{
    "cart_id": "xxxxxxxxx" // cache it 
}
```

<br><br>

### Get Cart

Link:[api/v1/cart/]()
<br><br>
Method: **GET**
<br><br>
**Param**
<br><br>
cart_id: Required
<br><br>
Response :

```
{
  "cart" :[
      {
        "prodcut_id": 1,
        "product_quantity" : 4,
        "price": 1500
      }
      ]

}

```

<br><br>

### Delete Products Form cart

Link:[/api/v1/cart/delete/]()
<br><br>
Method: **POST**
<br><br>
**BODY**
<br><br>
cart_id: Required
<br><br>
productID: Required
<br><br>
quantity: Required // quantity: 0
<br><br>
Response :

```
{
    "msg": "Done",
}
```

<br><br>

### Get my Orders

Link:[api/v1/orders/]()
<br><br>
Method: **GET**
<br><br>
Response :

```
{
  "orders": [
    {
      "id" : 1,
      "status" : "",
      "products_count" : 10,
      "products_amount_sum" : 10000,
      "create_at":""

    }
}

```

<br><br>

### Get my Orders products

Link:[api/v1/orders/products]()
<br><br>
Method: **GET**
<br><br>
**Param**
<br><br>
order_id: Required
<br><br>
Response :

```
{
  "order_products":[
    {
      "product_id": 1,
      "product_quantity" : 10
    }
    ]
}
```

<br><br>


### checkout product

Link:[/api/v1/checkout/product/]()
<br><br>
Method: **POST**
<br><br>
**BODY**
<br><br>
product_id: Required
<br><br>
quantity: Required
<br><br>
same_user_info: Required // bool
<br><br>
place: optional
<br><br>
phone: optional
<br><br>
Response :

```
{
    "msg": "Done",
}
```

### checkout cart

Link:[/api/v1/checkout/cart/]()
<br><br>
Method: **POST**
<br><br>
**BODY**
<br><br>
cart_id: Required
<br><br>
same_user_info: Required // bool
<br><br>
place: optional
<br><br>
phone: optional
<br><br>
Response :

```
{
    "msg": "Done",
}
```

<br><br>

### Search for product

Link:[api/v1/search]()
<br><br>
Method: **POST**
<br><br>
**BODY**
<br><br>
name: Required
<br><br>
Response :

```
// get product response
```

<br><br>

### rate for product

Link:[api/v1/rate]()
<br><br>
Method: **POST**
<br><br>
**BODY**
<br><br>
product_id: Required
<br><br>
product_rate: Required
<br><br>
Response :

```
{
"msg":"done"
}
```

<br><br>

### Get notifications

Link:[api/v1/notifications/]()
<br><br>
Method: **GET**
<br><br>
Response :

```
{
"notifications":
 [{
  "title":"",
  "message":"",
  "id":15,
  "type": 12
  }]
}
```
