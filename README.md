# shopper

![](xmind.png)
<br><br>
API documentation
<br><br>

### Notes:

```
all requests required token in the header, There is two types of tokens for requests, Signed user token and
guest token that able the user to view all products and to products to the cart and checkout the products you need to sign in or sign up.
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
"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVjODE1NmY4NjA3M2U3NTU1MDhlZDNjMiIsImlhdCI6MTU1MjY1NTIwMSwiZXhwIjoxNTU1MDc0NDAxfQ.gTX4y6LrEWHOSFWk60lHzrdTeV3K10iXpTLbAN2nNCc"
}
```

### Guest Login

Link:[/api/v1/auth/guest_login/]()
<br><br>
Method: **POST**
<br><br>
**BODY**
<br><br>
random_id: Required
<br><br>
Response :

```
{
"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVjODE1NmY4NjA3M2U3NTU1MDhlZDNjMiIsImlhdCI6MTU1MjY1NTIwMSwiZXhwIjoxNTU1MDc0NDAxfQ.gTX4y6LrEWHOSFWk60lHzrdTeV3K10iXpTLbAN2nNCc"
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
"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVjODE1NmY4NjA3M2U3NTU1MDhlZDNjMiIsImlhdCI6MTU1MjY1NTIwMSwiZXhwIjoxNTU1MDc0NDAxfQ.gTX4y6LrEWHOSFWk60lHzrdTeV3K10iXpTLbAN2nNCc"
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

### Get categories (section_id)

Link:[api/v1/categories/:id]()
<br><br>
Method: **GET**
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

### get products (category_id)

Link:[api/v1/products/:id]()
<br><br>
Method: **GET**
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
      "arrival_time":234
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

### Get cities (province_id)

Link:[api/v1/provinces/:id]()
<br><br>
Method: **GET**
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
priceID: Required
<br><br>
quantity: Required
<br><br>
Response :

```
{
    "cart_id": "xxxxxxxxx",
}
```

<br><br>

### Get Cart products

Link:[api/v1/cart/]()
<br><br>
Method: **GET**
<br><br>
Response :

```
{
  "products" :[
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
productID: Required
<br><br>
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

Link:[api/v1/Odrers/]()
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

### Get my Orders products (order_id)

Link:[api/v1/Odrers/:id]()
<br><br>
Method: **GET**
<br><br>
Response :

```
{
  "order_products":[
    {
      "id": 1,
      "product_quantity" : 10,
      "status" : "",
    }
    ]
}
```

<br><br>

### Get my Order product details (product_id)

Link:[api/v1/Odrers/product_details/:id]()
<br><br>
Method: **GET**
<br><br>
Response :

```
{
  "product":
       {
      "id": 1,
      "title":"",
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
    }

}
```

<br><br>

### checkout

Link:[/api/v1/cart/checkout/]()
<br><br>
Method: **POST**
<br><br>
**BODY**
<br><br>
productIDs: Required
<br><br>
quantities: Required
<br><br>
Response :

```
{
    "msg": "Done",
}
```

<br><br>

### Search for product

Link:[api/v1/Search]()
<br><br>
Method: **POST**
<br><br>
**BODY**
<br><br>
name: Required
<br><br>
Response :

```
{
  "products":[
    {
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
    }
    ]
}
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
