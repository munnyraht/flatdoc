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
## get_event_by_email (Retreive event)

> Endpoint: get_events_by_email

> Payload

```json
{
    "email": "email",
}
```

> Result

```json

[ 
  { 
    "event_id": 1, 
    "event_name": "event_name", 
    "event_tag": "event_tag",
    "start_date": "2019-12-02T12:30:30.001Z", 
    "end_date": "2019-05-04T12:30:30.001Z", 
    "username": "username", 
    "no_tickets_sold": 12,
    "revenue": 36000, 
    "status": "status"
  },
  {
    "event_id": 2, 
    "event_name": "Slay Festival", 
    "event_tag": "Slay", 
    "start_date": "2019-01-24T12:30:30.001Z",
    "end_date": "2019-05-04T12:30:30.001Z", 
    "username": "username", 
    "no_tickets_sold": 62,
    "revenue": 186000, 
    "status": "status"
  }

]
```

## get_event_by_username (Retreive event)

> Endpoint: get_events_by_username

> Payload

```json
{
    "username": "username"
}
```

> Result

```json

[ 
  { 
    "event_id": 1, 
    "event_name": "event_name", 
    "event_tag": "event_tag",
    "start_date": "2019-12-02T12:30:30.001Z", 
    "end_date": "2019-05-04T12:30:30.001Z", 
    "username": "username", 
    "no_tickets_sold": 12,
    "revenue": 36000, 
    "status": "status"
  },
  {
    "event_id": 2, 
    "event_name": "Slay Festival", 
    "event_tag": "Slay", 
    "start_date": "2019-01-24T12:30:30.001Z",
    "end_date": "2019-05-04T12:30:30.001Z", 
    "username": "username", 
    "no_tickets_sold": 62,
    "revenue": 186000, 
    "status": "status"
  }

]
```

## get_events_by_status (Retreive event)

> Endpoint: get_events_by_status

> Payload

```json
{
    "username": "username", "status":"status"
}
```

> Result

```json

[
   {"event_id": 1, 
    "event_name": "event_name", 
    "event_tag": "event_tag",
    "start_date": "2019-12-02T12:30:30.001Z", 
    "end_date": "2019-05-04T12:30:30.001Z", 
    "username": "username", 
    "no_tickets_sold": 12,
    "revenue": 36000, 
    "status": "status"},
    
   {"event_id": 2, 
    "event_name": "Slay Festival", 
    "event_tag": "Slay", 
    "start_date": "2019-01-24T12:30:30.001Z",
    "end_date": "2019-05-04T12:30:30.001Z", 
    "username": "username", 
    "no_tickets_sold": 62,
    "revenue": 186000, 
    "status": "status"}

]
```

## get_events_by_tag (Retreive event)

> Endpoint: get_events_by_tag

> Payload

```json
{
    "username": "username", "tag":"tag"
}
```

> Result

```json

[  {"event_id": 1, 
    "event_name": "event_name", 
    "event_tag": "event_tag",
    "start_date": "2019-12-02T12:30:30.001Z", 
    "end_date": "2019-05-04T12:30:30.001Z", 
    "username": "username", 
    "no_tickets_sold": 12,
    "revenue": 36000, 
    "status": "status"},

   {"event_id": 2, 
    "event_name": "Slay Festival", 
    "event_tag": "Slay", 
    "start_date": "2019-01-24T12:30:30.001Z",
    "end_date": "2019-05-04T12:30:30.001Z", 
    "username": "username", 
    "no_tickets_sold": 62,
    "revenue": 186000, 
    "status": "status"}

]
```

## get_no_of_sold_tickets (Retreive the number of ticket sold over a specified period of time)

> Endpoint: get_no_of_sold_tickets

> Payload

```json
{
    "username": "username", "period":"period"
}
```

> Result

```json

{"number_of_tickets_sold": "number_of_tickets_sold"}
```

## get_total_revenue (Retreive the amount of revenue made over a specified period of time)

> Endpoint: get_no_of_sold_tickets

> Payload

```json
{
    "username": "username", "period":"period"
}
```

> Result

```json

{"total_revenue":"total_revenue"}
```

## get_recent_purchases_by_email (Retreive top 10 tickets purchase records)

> Endpoint: get_recent_purchases_by_email

> Payload

```json
{
    "email": "email"
}
```

> Result

```json


[
    {"ticket_buyer_name": "ticket_buyer_name", 
    "amount":"amount", 
    "event_name": "event_name", 
    "purchase_date": "2019-05-04T12:30:30.001Z"}, 

    {"ticket_buyer_name": "ticket_buyer_name",
     "amount": "amount",
     "event_name": "event_name", 
     "purchase_date": "2019-05-04T12:30:30.001Z"} 
]

```



## get_ticket_purchase_details

> Endpoint: get_ticket_purchase_details

> Payload

```json
{
    "ticket_id": "ticket_id",
}
```

> Result

```json

[ 
  { 
    "name": "name",
    "email": "email", 
    "event_tag": "event_tag",
    "purchase_date": "2019-12-02T12:30:30.001Z",
    "ticket_id": "ticket_id",
    "ticket_type": "ticket_type"

  },
  { 
    "name": "name",
    "email": "email", 
    "event_tag": "event_tag",
    "purchase_date": "2019-12-02T12:30:30.001Z",
    "ticket_id": "ticket_id",
    "ticket_type": "ticket_type"

  }

]
```

## create_event (create a new event)

> Endpoint: create_event

> Payload

```json
{
    "username":"username",
    "event_name":"event_name",
    "event_tag":"event_tag",
    "description":"description",
    "start_date":"start_date",
    "end_date":"end_date"
}
```

> Result

```json
{   "event_ref":"event_ref",
    "username":"username",
   "event_name":"event_name",
   "event_tag":"event_tag",
   "description":"description",
   "start_date":"start_date",
   "end_date":"end_date"    

   } 

```

## edit_user_info 

> Endpoint: edit_user_info 

> Payload

```json
{
    "event_name":"event_name",
    "event_tag":"event_tag",
    "description":"description",
    "start_date":"start_date",
    "email":"email",
    "end_date":"end_date",
    "twitter_link":"twitter_link",
    "facebook_link":"facebook_link"
}
```

> Result

```json
{   

   "event_name":"event_name",
   "event_tag":"event_tag",
   "description":"description",
   "email":"email",
   "description":"description",
   "start_date":"start_date",
   "end_date":"end_date",
   "twitter_link":"twitter_link",
    "facebook_link":"facebook_link"   

   } 

```


## get_event_summary

> Endpoint: get_event_summary

> Payload

```json
{ 

  "username": "username",
  "event_name": "event_name",
   "period": "2019-09-12T12:30:30.001Z"

}
```

> Result

```json
{ 

"Total_orders": 0, 
"Total_ticket_sold": 0,
"Total_revenue": 0,
"revenue_ticketsold_details": [{"date": "date", "amount": 0,"no_of_tickets": 0},
                               {"date": "date", "amount": 0, "no_of_tickets": 0},
                               {"date": "date", "amount": 0, "no_of_tickets": 0},
                               {"date": "date", "amount": 0, "no_of_tickets": 0}, 
                               {"date": "date", "amount": 0, "no_of_tickets": 0}
                              ], 
"registration_details": [{"Male": 0, "Female": 0, "Other": 0},
                         {"under_20": 0, "21-30": 0, "31+": 0},
                         {"Testing": 0, "VIP": 0, "Table": 0, "Cabana": 0}
                        ]

   } 

```

## get_event_ticket_details

> Endpoint: get_event_ticket_details

> Payload

```json
{ 

  "username": "username",
  "event_name": "event_name"

}
```

> Result

```json

[
   {
    "ticket_name": "Regular", 
    "amount": 2000, 
    "sales_start_date": "2019-09-02T12:30:30.001Z", 
    "sales_end_date": "2019-11-02T12:30:30.001Z", 
    "no_of_ticket_sold": 2,
    "Quantity_available": 98
    }, 

    {
      "ticket_name": "VIP",
      "amount": 10000, 
      "sales_start_date": "2019-09-02T12:30:30.001Z", 
      "sales_end_date": "2019-11-02T12:30:30.001Z", 
      "no_of_ticket_sold": 3,
      "Quantity_available": 97
    },

    {
      "ticket_name": "Table",
      "amount": 85000,
      "sales_start_date": "2019-09-02T12:30:30.001Z", 
      "sales_end_date": "2019-12-02T12:30:30.001Z",
      "no_of_ticket_sold": 2,
      "Quantity_available": 98
    }
```

## create_ticket 

> Endpoint: create_ticket

> Payload

```json
{
    "username": "username",
     "event_name": "event_name", 
     "ticket_name": "ticket_name", 
     "price": 700000,
      "description": "description", 
      "Quantity Available": "Quantity Available"

}
```

> Result

```json
  {
    "username": "Acme", 
    "event_name": "Tekker Expo", 
    "ticket_name": "Table", 
    "price": 700000, 
    "description": "sit next to vip on in the front row", 
    "Quantity Available": 1000

  }

```

## get_ticket_purchase_details

> Endpoint: get_ticket_purchase_details

> Payload

```json
{
    "username": "username",
    "event_name": "event_name"

}
```

> Result

```json
  [
    { 
      "ticket_buyer_name": "ticket_buyer_name",
      "amount":"amount",
      "no_of_ticket_purchased":"no_of_ticket_purchased",
      "purchase_date":"purchase_date",
      "ticket_id":"ticket_id",
      "email":"email"
    },
    { 
      "ticket_buyer_name": "ticket_buyer_name",
      "amount":"amount",
      "no_of_ticket_purchased":"no_of_ticket_purchased",
      "purchase_date":"purchase_date",
      "ticket_id":"ticket_id",
      "email":"email"
    }
  ]
```
## edit_ticket

> Endpoint: edit_ticket

> Payload

```json
{
    "username": "username",
    "event_name":"event_name",
    "ticket_name": "ticket_name",
    "Quantity_available":"Quantity_available",
    "description":"description",
    "sales_start_date":"sales_start_date",
    "sales_end_date" : "sales_end_date",
    "minimum_tickets_per_order":"minimum_tickets_per_order",
    "max_tickets_per_order": "max_tickets_per_order"

}
```

> Result

```json
 
  'Tickets Updates Successfully'

```