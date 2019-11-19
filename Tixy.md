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
    "event_id": "event_id", 
    "event_name": "event_name", 
    "event_tag": "event_tag",
    "start_date": "start_date", 
    "end_date": "end_date", 
    "username": "username", 
    "no_tickets_sold": "no_tickets_sold",
    "revenue": "revenue", 
    "status": "status"
  },
  {
  "event_id": "event_id", 
    "event_name": "event_name", 
    "event_tag": "event_tag",
    "start_date": "start_date", 
    "end_date": "end_date", 
    "username": "username", 
    "no_tickets_sold": "no_tickets_sold",
    "revenue": "revenue", 
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
    "event_id": "event_id", 
    "event_name": "event_name", 
    "event_tag": "event_tag",
    "start_date": "2019-12-02T12:30:30.001Z", 
    "end_date": "2019-05-04T12:30:30.001Z", 
    "username": "username", 
    "no_tickets_sold": "no_tickets_sold",
    "revenue": "revenue", 
    "status": "status"
  },
  { 
    "event_id": "event_id", 
    "event_name": "event_name", 
    "event_tag": "event_tag",
    "start_date": "2019-12-02T12:30:30.001Z", 
    "end_date": "2019-05-04T12:30:30.001Z", 
    "username": "username", 
    "no_tickets_sold": "no_tickets_sold",
    "revenue": "revenue", 
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
  {
    "event_id": "event_id",
    "event_name": "event_name",
    "event_tag": "event_tag",
    "start_date": "start_date",
    "end_date": "end_date",
    "username": "username",
    "no_tickets_sold": "no_tickets_sold",
    "revenue": "revenue",
    "status": "status"
  },
  {
    "event_id": "event_id",
    "event_name": "event_name",
    "event_tag": "event_tag",
    "start_date": "start_date",
    "end_date": "end_date",
    "username": "username",
    "no_tickets_sold": "no_tickets_sold",
    "revenue": "revenue",
    "status": "status"
  }
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

[
   {
    "event_id": "event_id", 
    "event_name": "event_name", 
    "event_tag": "event_tag",
    "start_date": "start_date", 
    "end_date": "end_date", 
    "username": "username", 
    "no_tickets_sold": "no_tickets_sold",
    "revenue": "revenue", 
    "status": "status"
  },
    
    {
    "event_id": "event_id", 
    "event_name": "event_name", 
    "event_tag": "event_tag",
    "start_date": "start_date", 
    "end_date": "end_date", 
    "username": "username", 
    "no_tickets_sold": "no_tickets_sold",
    "revenue": "revenue", 
    "status": "status"
  }

]
```

## get_no_of_sold_tickets 

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

## get_total_revenue 

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
  {
    "ticket_buyer_name": "ticket_buyer_name",
    "amount": "amount",
    "event_name": "event_name",
    "purchase_date": "purchase_date"
  },
  {
    "ticket_buyer_name": "ticket_buyer_name",
    "amount": "amount",
    "event_name": "event_name",
    "purchase_date": "purchase_date"
  }
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

"User info updated Successfully"

```


## get_event_summary

> Endpoint: get_event_summary

> Payload

```json
{ 

  "username": "username",
  "event_name": "event_name",
  "period":"period"

}
```

> Result

```json
{
  "orders": "total_number_of_orders",
  "ticket_sold": "total_ticket_sold",
  "total_event_page_view": "total_event_page_view",
  "revenue_ticketsold_details": [
    {
      "date": "date",
      "amount": "amount",
      "no_of_tickets": "no_of_tickets"
    },
    {
      "date": "date",
      "amount": "amount",
      "no_of_tickets": "no_of_tickets"
    },
    {
      "date": "date",
      "amount": "amount",
      "no_of_tickets": "no_of_tickets"
    }
  ],
  "registration_details": [
    {
      "Male": "no_of_male",
      "Female": "no_of_female",
      "Other": "no_of_other"
    },
    {
      "under_20": "number_of_under_20",
      "21-30": "number_of_21-30",
      "31+": "number_of_31"
    },
    {
      "Ticket1": "number_of_ticket1",
      "Ticket2": "number_of_ticket2",
      "Ticket3": "number_of_ticket3"
    }
  ],
  "event_view_details": [
    {
      "date": "date",
      "views": "number_of_views"
    },
    {
      "date": "date",
      "views": "number_of_views"
    },
    {
      "date": "date",
      "views": "number_of_views"
    }
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
    "ticket_name": "Ticket1",
    "amount": "amount",
    "sales_start_date": "sales_start_date",
    "sales_end_date": "sales_end_date",
    "no_of_ticket_sold": "no_of_ticket_sold",
    "Quantity_available": "Quantity_available",
    "Revenue": "Revenue"
  },
  {
    "ticket_name": "Ticket2",
    "amount": "amount",
    "sales_start_date": "sales_start_date",
    "sales_end_date": "sales_end_date",
    "no_of_ticket_sold": "no_of_ticket_sold",
    "Quantity_available": "Quantity_available",
    "Revenue": "Revenue"
  }
]
```

## create_ticket 

> Endpoint: create_ticket

> Payload

```json
{
  "username": "username",
  "event_name": "event_name",
  "ticket_name": "ticket_name",
  "price": "price",
  "description": "description",
  "Quantity Available": "Quantity Available"
}
```

> Result

```json
  
  "Ticket Created Successfully"

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
  "event_name": "event_name",
  "ticket_name": "ticket_name",
  "Quantity_available": "Quantity_available",
  "description": "description",
  "sales_start_date": "sales_start_date",
  "sales_end_date": "sales_end_date",
  "minimum_tickets_per_order": "minimum_tickets_per_order",
  "max_tickets_per_order": "max_tickets_per_order"
}
```

> Result

```json
 
  "Tickets Updates Successfully"

```

## get_attendees

> Endpoint: get_attendees

> Payload

```json
{
  "username": "username",
  "event_name": "event_name",
  "status": "status",
  "payment": "payment"
}
```

> Result

```json
  [
  {
    "name": "name",
    "email": "email",
    "ticket_type": "ticket_type",
    "check_in status": false
  },
  {
    "name": "name",
    "email": "email",
    "ticket_type": "ticket_type",
    "check_in status": false
  },
  {
    "name": "name",
    "email": "email",
    "ticket_type": "ticket_type",
    "check_in status": false
  }
]
```

## get_event_details

> Endpoint: get_event_details

> Payload

```json
{
  "username": "username",
  "event_name": "event_name"
}
```

> Result

```json
 {
  "event_name": "Valentine Fest",
  "description": "description",
  "start_date": "start_date",
  "end_date": "end_date",
  "venue_name": "venue_name",
  "city": "city",
  "address": "address"
}
```

## get_orders_by_event_name

> Endpoint: get_attendees

> Payload

```json
{
  "username": "username",
  "event_name":"event_name",
  "status":"status",
  "payment":"payment"

}
```

> Result

```json
  [
  {
    "name": "name",
    "email": "email",
    "order_date": "date",
    "amount": "amount",
    "payment_status": "payment_status"
  },
  {
    "name": "name",
    "email": "email",
    "order_date": "date",
    "amount": "amount",
    "payment_status": "payment_status"
  },
  {
    "name": "name",
    "email": "email",
    "order_date": "date",
    "amount": "amount",
    "payment_status": "payment_status"
  }
]
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
```

## get_surveys

> Endpoint: get_surveys

> Payload

```json
{
  "username": "username",
  "event_name":"event_name"
}
```

> Result

```json
[
  {
    "survey_id": "survey_id",
    "question": "What does Fox say",
    "ticket": [
      "ticket1", "ticket2"
    ],
    "channel": "channel",
    "answers": "number_of_answers"
  },
  {
    "survey_id": "survey_id",
    "question": "What does Fox say",
    "ticket": [
      "ticket1", "ticket2"
    ],
    "channel": "channel",
    "answers": "number_of_answers"
  }
]
  
```

## get_survey_answers

> Endpoint: get_survey_answers

> Payload

```json
{
  "username": "username",
  "event_name":"event_name",
  "survey_id":"survey_id"
}
```

> Result

```json
[
  {
    "respondent": "respondent",
    "answer": "answer"
  },
  {
    "respondent": "respondent",
    "answer": "answer"
  },
  {
    "respondent": "respondent",
    "answer": "answer"
  }
]
  
```

## create_survey

> Endpoint: create_survey

> Payload

```json
{
  "username": "username",
  "event_name":"event_name",
  "survey_id":"survey_id"
}
```

> Result

```json
[
  {
    "respondent": "respondent",
    "answer": "answer"
  },
  {
    "respondent": "respondent",
    "answer": "answer"
  },
  {
    "respondent": "respondent",
    "answer": "answer"
  }
]
  
```

##create_event_messages

> Endpoint: create_event_messages

> Payload

```json
{
  "username": "username",
  "event_name":"event_name",
  "message_body":"message_body",
  "message_subject":"message_subject",
  "group":"group",
  "ticket":"ticket"

}
```

> Result

```json
"Message Composed Succesfully"
  
```

##get_payment_messages

> Endpoint: get_payment_messages

> Payload

```json
{
  "username": "username",
  "event_name":"event_name"

}
```

> Result

```json
{
  "message_before_payment": "message_before_payment",
  "message_after_payment": "message_after_payment",
  "offline_payment_message": "offline_payment_message"
}
  
```

##save_payment_messages

> Endpoint: save_payment_messages

> Payload

```json
{
  "username": "username",
  "event_name":"event_name",
  "message_before_payment": "message_before_payment",
  "message_after_payment": "message_after_payment",
  "offline_payment_message": "offline_payment_message"

}
```

> Result

```json
"Message Created Succesfully"
  
```

##get_ticket_design

> Endpoint: get_ticket_design

> Payload

```json
{
  "username": "username",
  "event_name":"event_name",
  "ticket_name": "ticket_name"

}
```

> Result

```json
{
  "background_color":"background_color",
  "accent_color":"accent_color",
  "logo":"logo"
}
  
```

##save_ticket_design

> Endpoint: save_ticket_design

> Payload

```json
{
  "username": "username",
  "event_name":"event_name",
  "ticket_name": "ticket_name",
  "background_color":"background_color",
  "accent_color":"accent_color",
  "logo":"logo"

}
```

> Result

```json
"Design Saved Succesfully"
  
```

##get_orders_by_event_name

> Endpoint: get_orders_by_event_name

> Payload

```json
{
  "username": "username",
  "event_name":"event_name",
  "status":"status",
  "payment":"payment"
}
```

> Result

```json
[
  {
    "ticket_buyer_name": "ticket_buyer_name",
    "email": "email",
    "ticketid": "ticketid",
    "purchase_date": "ticketid",
    "amount": "amount",
    "no_of_ticket_purchased": "no_of_ticket_purchased",
    "status": "status",
    "payment": "payment"
  },
  {
    "ticket_buyer_name": "ticket_buyer_name",
    "email": "email",
    "ticketid": "ticketid",
    "purchase_date": "ticketid",
    "amount": "amount",
    "no_of_ticket_purchased": "no_of_ticket_purchased",
    "status": "status",
    "payment": "payment"
  }
]
  
```

##get_message_details

> Endpoint: get_message_details

> Payload

```json
{
  "username": "username",
  "event_name":"event_name",
  "group": "group",
  "ticket":"ticket"

}
```

> Result

```json
[
  {
  "message_id": "message_id",
  "message": "message",
  "respondent": "respondent",
  "mail_opened": "mail_opened",
  "group": "group",
  "ticket":[ "tickets"]
  },
  {
  "message_id": "message_id",
  "message": "message",
  "respondent": "respondent",
  "mail_opened": "mail_opened",
  "group": "group",
  "ticket":[ "tickets"]
  }
]

```