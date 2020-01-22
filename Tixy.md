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
     "period": "period"
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
    "buyer_name":"buyer_name",
    "amount": "amount",
    "purchase_date": "purchase_date"
  }
]

```

## get_tickets_by_order_id

> Endpoint: get_tickets_by_order_id

> Payload

```json
{
    "idToken" : "idToken",
    "uid" : "uid",
    "order_id" :"order_id"
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
    "attendee_ticket_id": "attendee_ticket_id"
  }

]
```

## get_tickets_by_event_id

> Endpoint: get_tickets_by_order_id

> Payload

```json
{
    "idToken" : "idToken",
    "uid" : "uid",
    "event_id" :"event_id",
    "filter":{
      "check_in_status": true,
      "payment_method": "payment_method"
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
    "check_in_status": true,
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
    "description": " description"
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
    "industry": "industry",
    "password": "password",
    "website": "website",
    "plan": "plan",
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
  "period": "period"
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
      "payment_method":"payment_method"
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

## edit_event

> Endpoint: edit_event

> Payload

```json
{
  "username": "username",
  "event_name":"event_name",
  "new_event_name":"new_event_name",
  "description":"description",
  "start_date":"start_date",
  "end_date":"end_date",
  "venue_name":"venue_name",
  "city":"city",
  "address":"address",
  "image_link":"image_link",
  "logo_link":"logo_link"

}
```

> Result

```json
  "Event  Updated Successfully"


