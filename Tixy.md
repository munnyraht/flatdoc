# Tixy

Endpoint for Tixy

## Create an account (Sign up)

> Endpoint: tixy_register

> Payload

```json
{
    "email": "email",
    "industry": "industry",
    "password": "password",
    "organizer": "organizer",
    "website": "website"
}
```

> Result

```json
{
    "accountRef": "ea7ca901-9217-4a04-9af4-3c6c21ccc3a2"
}
```

## Sign-in to an account

> Endpoint: tixy_sign_in

> Payload

```json
{
    "email": "email",
    "password": "password"
}
```
> Result

```json
{
    "account": {
        "accountRef": "ea7ca901-9217-4a04-9af4-3c6c21ccc3a2",
        "email": "email",

        "industry": "industry",
        "organizer": "organizer",
        "website": "website",
        "plan": ""
    }
}

```
## get_accountid

> Endpoint: get_accountid

> Payload

```json
{ 
    "idToken": "idToken",
     "uid":"uid"
}
```

> Result

```json

{
  "account_id": "account_id"
}

```
## get_events

> Endpoint: get_events

> Payload(filter is not required)

```json
{ 
    "idToken": "idToken",
     "uid":"uid",
     "accountid": "accountid",
     "filter":{
      "status": true,
      "event_tag": "payment_method"
     }

}
```

> Result

```json

[ 
  { 
    "event_id": "event_id", 
    "event_name": "event_name", 
    "event_tag": "event_tag",
    "start_date": "start_date", 
    "end_date": "end_date", 
    "status":"status",
    "username": "username", 
    "tickets": "tickets",
    "revenue": "revenue"
  }
]
```

## get_revenue_and_ticketsold

> Endpoint: get_revenue_and_ticketsold

> Payload

```json
{
    "idToken" : "idToken",
     "uid": "uid",
     "accountid": "accountid",
     "period": "period",
      // period format must be -%Y-%m-%dT%H:%M:%S.%fZ
}
```

> Result

```json

{
  "ticket_sold": "ticket_sold",
  "revenue": "revenue"
}
```

## get_recent_orders

> Endpoint: get_recent_orders

> Payload

```json
{
    "idToken" : "idToken",
    "uid" : "uid",
    "accountid" :"accountid",
    "number_of_orders": "number_of_orders"
}
```

> Result

```json

[
  {
    "event_id": "event_id",
    "event_tag": "event_tag",
    "order_id": "order_id",
    "buyer_name": "buyer_name",
    "amount": "amount",
    "purchase_date": "purchase_date",
    " number_of_ticket": "number_of_ticket",
    "tickets": [
      {
        "ticket_name": "ticket_name",
        "attendees_email": "attendees_email",
        "ticket_id": "ticket_id",
        "attendees_name": "attendees_name",
        "price": "price"
      }
    ]
  }
]

```

## get_tickets_by_event_id

> Endpoint: get_tickets_by_event_id

> Payload

```json
{
    "idToken" : "idToken",
    "uid" : "uid",
    "event_id" :"event_id",
    "filter":{
      "check_in_status": true,
      "ticket_name": "ticket_name"
     }
}
```

> Result

```json

[ 
  {
    "ticket_id": "ticket_id",
    "attendees_name": "attendees_name",
    "attendee_email": "attendee_email",
    "ticket_name": "ticket_name",
    "attendee_ticket_id": "attendee_ticket_id",
    "check_in_status": "check_in_status",
    "payment_method": "payment_method"
  }

]
```

## create_event

> Endpoint: create_event

> Payload

```json
{
    "idToken": "idToken", 
    "uid" : "idToken",
    "event_name" : "event_name",
    "event_tag": "event_tag",
    "description": " description",
    "address":"address",
    "banner":"banner",
    "city":"city",
    "image":"image",
    "logo":"logo",
    "venue":"venue",
    "end_date": "end_date",
    "start_date": "start_date"
}
```

> Result

```json
{ 
  "status": 200,
  "text": "event created Succesfully"
}

```

## update_account 

> Endpoint: update_account

> Payload

```json
{
    "idToken": "idToken",
    "uid" : "uid",
    "accountid": "accountid",
    "email": "email",
    "organizer": "organizer",
    "website": "website",
    "facebook_link": "facebook_link",
    "google_analytic_code": "google_analytic_code",
    "twitter_link": "twitter_link",
    "logo": "logo",
    "image": "image"
  }
```

> Result

```json

{
  "status": 200,
  "text": "Account updated successful"
}

```


## get_event_summary

> Endpoint: get_event_summary

> Payload

```json
{ 

  "idToken": "idToken",
  "uid": "uid",
  "event_id": "event_id",
  "period": "period",
   // period format must be -%Y-%m-%dT%H:%M:%S.%fZ
}
```

> Result

```json
{
  "orders": "total_orders",
  "ticket_sold": "ticket_sold",
  "total_revenue": "total_revenue",
  "total_event_page_view": "total_event_page_view",
  "ticket_details": "tickets_details",
  "registration_details": "registration_details",
  "event_view_details": "event_views"
}
```

## get_ticket_categories

> Endpoint: get_ticket_category

> Payload

```json
{ 
  "idToken": "idToken",
  "uid": "uid",
  "event_id": "event_id"
}
```

> Result

```json

[
  {
    "ticket_category_id":"ticket_category_id",
    "category_name": "category_name",
    "price":"price",
    "description":"description",
    "sales_start_date": "sales_start_date",
    "sales_end_date": "sales_end_date",
    "Quantity_available": "Quantity_available",
    "minimum_tickets_per_order": "minimum_tickets_per_order",
    "maximum_tickets_per_order": "maximum_tickets_per_order"
  }
]
```

## create_ticket_category 

> Endpoint: create_ticket_category

> Payload

```json
{
  "idToken": "idToken",
  "uid": "uid",
  "accountid": "accountid",
  "event_id": "event_id",
  "ticket_category_name": "ticket_category_name",
  "price": "price",
  "description": "description",
  "sales_start_date": "sales_start_date",
  "sales_end_date": "sales_end_date",
  "Quantity_available": "Quantity_available",
  "minimum_tickets_per_order": "minimum_tickets_per_order",
  "maximum_tickets_per_order": "maximum_tickets_per_order"
}
```

> Result

```json
  
  "Ticket Category Created Successfully"

```

## get_event_orders

> Endpoint: get_event_orders

> Payload

```json
{
    "idToken": "idToken",
    "uid": "uid",
    "accountid": "accountid",
    "event_id": "event_id",
    "filter":{ "payment_status": "payment_status",
                "payment_method": "payment_method"

    }
}
```

> Result

```json
  [
  {
    "order_id": "order_id",
    "buyer_name": "buyer_name",
    "email": "email",
    "amount": "amount",
    "payment_status": "payment_status",
    "order_date": "order_date",
    "payment_method": "payment_method",
    "tickets": [
      {
        "ticket_name": "ticket_name",
        "ticket_id": "ticket_id",
        "attendee_email": "attendee_email"
      }
    ],
    "ticket_details": [
      {
        "ticket_name": "ticket_name",
        "quantity": 2,
        "amount": "50000"
      }
    ]
  }
]
```
## edit_ticket_categories

> Endpoint: edit_ticket_categories

> Payload

```json
{
  "idToken": "idToken",
  "uid": "uid",
  "accountid": "accountid",
  "event_id": "event_id",
  "ticket_category_id":"ticket_category_id",
  "category_name":"category_name",
  "price":"price",
  "Quantity_available": "Quantity_available",
  "description": "description",
  "sales_start_date": "sales_start_date",
  "sales_end_date": "sales_end_date",
  "minimum_tickets_per_order": "minimum_tickets_per_order",
  "maximum_tickets_per_order": "maximum_tickets_per_order"
}
```

> Result

```json
 
  {
    "status": 200,
    "text": "Ticket category edited successful"
  }

```

## check_in_status

> Endpoint: check_in_status

> Payload

```json
{
  "idToken": "idToken",
  "uid": "uid",
  "ticket_id": "ticket_id",
  "status":"status"
}
```

> Result

```json
 
  {
    "status": 200,
    "text": "check in status updated successful"
  }

```


## send_mail

> Endpoint: send_mail

> Payload

```json
{
  "idToken": "idToken",
  "uid": "uid",
  "event_id": "event_id",
  "message_subject" : "message_subject",
  "message_body" : "message_body",
  "recipient_group": ["recipient_group"],
  "ticket_categories": ["ticket_category1", "ticket_category1" ]

}
```

> Result

```json
  "Mail Sent Successfully"

```

## update_event

> Endpoint: update_event

> Payload

```json
{
  "idToken": "idToken",
  "uid": "uid",
  "event_id": "event_id",
  "event_name":"event_name",
  "start_date":"start_date",
  "end_date":"end_date",
  "venue ":"venue",
  "city":"city",
  "address": "address",
  "logo" : "logo",
  "image" : "image"

}
```

> Result

```json
  
  "Event Updated Successfully"

```

## get_account_details

> Endpoint: get_account_details

> Payload

```json
{
  "idToken": "idToken",
  "uid": "uid",
  "accountid": "accountid"
}
```

> Result

```json
  
  {
    "created_at": "created_at",
    "industry": "industry",
    "website": "website",
    "twitter_link": "twitter_link",
    "plan": "plan",
    "updated_at": "updated_at",
    "organizer": "organizer"
}

```

## buy_tickets

> Endpoint: get_account_details

> Payload

```json
{
  "buyer":{
    "fname ":"fname",
    "lname":"lname",
    "email":"email",
    "amount":"amount",
    "number_of_tickets":"number_of_tickets",
    "fees":"fees"
  },
  "attendees":[
                {
                  "fname":"fname",
                  "lname":"lname",
                  "email":"email"
                },
                {
                  "fname":"fname",
                  "lname":"lname",
                  "email":"email"
                }
              ]
}
```

> Result

```json
  
  {
    "":""
  }

```


## event_page_views

> Endpoint: event_page_views

> Payload

```json
{
  "event_id":"event_id"
}
```

> Result

```json
  
  "OK"

```

## get_event_page_details

> Endpoint: get_event_page_details

> Payload

```json
{
  "idToken":  "idToken",
  "uid" : "uid",
  "event_id":"event_id",
  "period": "period"
}
```

> Result

```json
  
 {
  "date":"views",
  "dtae":"views"
 }

```

## get_event_details

> Endpoint: get_event_details

> Payload

```json
{
  "idToken": "idToken",
  "uid": "uid",
  "event_id": "event_id"
}
```

> Result

```json
  
  {
    "event_name": "event_name",
    "event_tag": "event_tag",
    "start_date": "start_date",
    "twitter_link": "twitter_link",
    "image_link": "",
    "venue": "",
    "city": "",
    "created_at": "created_at",
    "end_date": "end_date",
    "address": "address",
    "updated_at": "updated_at",
    "description": " description",
    "logo_link": ""
}

```
## plan_subscription_callback

> Endpoint: plan_subscription_callback

> Payload

```json
{
  "accountRef" : "accountRef",
  "reference" : "reference",
  "plan": "plan"
}
```

> Result

```json
  
  {
    "status": 200,
    "text": "Account Subscription updated successful"
}

```

## delete_ticket_category

> Endpoint: delete_ticket_category

> Payload

```json
{
  "idToken": "idToken",
  "uid" : "uid",
  "accountid"  : "accountid",
  "event_id": "event_id",
  "ticket_category_id": "ticket_category_id"
}
```

> Result

```json
  
  {
    "status": 200,
    "text": "ticket category deleted successfully'"
}

```
## open_event_details

> Endpoint: open_event_details

> Payload

```json
{
  "event_id": "event_id"

}
```

> Result

```json
  
  {
    "description": "description",
    "logo": "logo",
    "start_date": "start_date",
    "logo_link": "logo_link",
    "twitter_link": "twitter_link",
    "event_tag": "event_tag",
    "venue": "venue",
    "city": "city",
    "event_name": "event_name",
    "end_date": "end_date",
    "banner": "banner",
    "address": "address"
}

```


## get_ticket_categories

> Endpoint: open_ticket_categories

> Payload

```json
{ 

  "event_id": "event_id"
}
```

> Result

```json

[
  {
    "ticket_category_id":"ticket_category_id",
    "category_name": "category_name",
    "price":"price",
    "description":"description",
    "sales_start_date": "sales_start_date",
    "sales_end_date": "sales_end_date",
    "Quantity_available": "Quantity_available",
    "minimum_tickets_per_order": "minimum_tickets_per_order",
    "maximum_tickets_per_order": "maximum_tickets_per_order"
  }
]
```
