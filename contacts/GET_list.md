# Contact List

    GET accounts/:account_id/contacts    
    GET services/:service_id/contacts
    GET contacts
    
Returns a list of [Contacts].  If the service is included in the URL, only contacts for the specified service or account will be searched. If no service or account is specified in the URL, all 
contacts accessible by the current developer credentials will be searched.




## Parameters
Field | Wildcards | Description
--- | --- | ---
Pagination options | N | (see [Overview - Request Modifiers][])
channel_value | Y | Filter by contact channel values
channel_type_id | N | Filter by channel type
label_id | N | Filter by Label ID
contact_group_id | N | Filter by Contact Group ID
assigned_to_user_id | N | Filter by assigned user
assigned_to_team_id | N | Filter by assigned team
is_confirmed | N | Filter by confirmed status (true = confirmed, false = not confirmed)
is_starred | N | Filter by starred status (true = starred, false = not starred)
is_closed | N | Filter by closed status (true = closed, false = not closed)
is_unassigned | N | Filter by unassigned contacts (true = unassigned, false not supported)
locked_by_source | N | Filter by lock source
optin_status | N | Filter by opt-in status
query | N | Search contacts by first name, last name, or channel value
search_message_bodies | N | When using the 'query' parameter, setting this to true will return any contacts who have sent or received a message containing the query string

### Sortable Fields
* created_at
* updated_at
* is_confirmed
* is_starred
* is_closed
* last_message_created_at
* locked_by_source
* last_name
* first_name
* optin_status

## Example
### Request

    GET https://api.zingle.me/v1/services/aff7bc93-6e28-4e70-8770-defa35cdfc1b/contacts

### Response
``` json
{
    "status": {
        "text": "OK",
        "status_code": 200,
        "description": null,
        "sort_field": "id",
        "sort_direction": "asc",
        "page": 1,
        "page_size": 10,
        "total_pages": 1,
        "total_records": 1
    },
    "result": [
    {
        "id": "89d9e8b5-b225-476c-a83e-50cdb720e3b1",
        "notes": null,
        "service_id": "aff7bc93-6e28-4e70-8770-defa35cdfc1b",
        "assigned_to_team_id": "bf5c8s4e-b4f5-4382-9f3a-9ees5eedaef1",
        "assigned_to_user_id": null,
        "is_messageable": true,
        "is_confirmed": true,
        "is_starred": false,
        "is_closed": false,
        "avatar_uri": null,
        "optin_status": null,            
        "created_at": 1442352326,
        "updated_at": 1442621196,
        "locked_by_source": null,
        "last_message": {
          "id": null,
          "body": null,
          "created_at": null
        },
        "channels": [
          {
            "id": "1bc63907-b3df-47c4-9a7c-11ad9ab35085",
            "display_name": "Woohoo!",
            "value": "+18582355555",
            "formatted_value": "(858) 235-5555",
            "country": "US",
            "is_default": false,
            "is_default_for_type": false,
            "block_inbound": false,
            "block_outbound": true,
            "channel_type": {
              "id": "0e3d71ee-9518-4b9b-b95a-dea251829887",
              "type_class": "PhoneNumber",
              "display_name": "Phone Number",
              "inbound_notification_url": null,
              "outbound_notification_url": null,
              "allow_communications": true
            }
          },
          {
            "id": "cca65a79-cf8e-44e0-8003-b422819db801",
            "display_name": "Home",
            "value": "+18585555523",
            "formatted_value": "(858) 555-5523",
            "country": "US",
            "is_default": false,
            "is_default_for_type": false,
            "block_inbound": false,
            "block_outbound": true,
            "channel_type": {
              "id": "0e3d71ee-9518-4b9b-b95a-dea251829887",
              "type_class": "PhoneNumber",
              "display_name": "Phone Number",
              "inbound_notification_url": null,
              "outbound_notification_url": null,
              "allow_communications": true
            }
          }
        ],
        "custom_field_values": [
          {
            "value": "William",
            "selected_custom_field_option_id": null,
            "custom_field": {
              "id": "56c70519-6c70-40e5-904e-7652e54a07b6",
              "display_name": "First Name",
              "code": "first_name",
              "replacement_variable": "FIRST NAME",
              "is_global": true,
              "options": []
            }
          },
          {
            "value": "Tell",
            "selected_custom_field_option_id": null,
            "custom_field": {
              "id": "29fdae7d-c5d7-4cd6-b2e4-cd52603ff577",
              "display_name": "Last Name",
              "code": "last_name",
              "replacement_variable": "LAST NAME",
              "is_global": true,
              "options": []
            }
          },
          {
            "value": "Mr.",
            "selected_custom_field_option_id": "266cbe3c-dd2f-45c2-8473-d84a8e6fada6",
            "custom_field": {
              "id": "808cd25e-ca27-4fdb-a10c-d87032108f38",
              "display_name": "Title",
              "code": "title",
              "replacement_variable": "TITLE",
              "is_global": true,
              "options": [
                {
                  "id": "6c39cca3-a27c-4a8b-9383-53262651d0af",
                  "display_name": "",
                  "value": "",
                  "sort_order": 1
                },
                {
                  "id": "266cbe3c-dd2f-45c2-8473-d84a8e6fada6",
                  "display_name": "Mr.",
                  "value": "Mr.",
                  "sort_order": 2
                },
                {
                  "id": "4f0fe1ce-dff6-47e6-8737-1212d603b430",
                  "display_name": "Mrs.",
                  "value": "Mrs.",
                  "sort_order": 3
                },
                {
                  "id": "5af67d3f-f31d-4f32-a560-c6a36e734b21",
                  "display_name": "Ms.",
                  "value": "Ms.",
                  "sort_order": 4
                },
                {
                  "id": "5782d3ca-9db8-4549-a5e5-9e0abd3b7366",
                  "display_name": "Dr",
                  "value": "Dr",
                  "sort_order": 5
                },
                {
                  "id": "f941f1ff-1c99-40b8-841b-b46bc5e1fd90",
                  "display_name": "Prof.",
                  "value": "Prof.",
                  "sort_order": 6
                },
                {
                  "id": "97b482f2-93a8-4eb9-8458-f922f2d4026a",
                  "display_name": "Dir.",
                  "value": "Dir.",
                  "sort_order": 7
                },
                {
                  "id": "cd15f583-a4de-46d8-b9af-17f674263472",
                  "display_name": "Rev.",
                  "value": "Rev.",
                  "sort_order": 8
                },
                {
                  "id": "5b298689-faae-4a40-8703-735b1057e892",
                  "display_name": "Capt.",
                  "value": "Capt.",
                  "sort_order": 9
                }
              ]
            }
          },
          {
            "value": "Yes",
            "selected_custom_field_option_id": null,
            "custom_field": {
              "id": "533a2ea5-ccae-4662-9a09-215aa0156a04",
              "display_name": "Verified",
              "code": "verified",
              "replacement_variable": "VERIFIED",
              "is_global": true,
              "options": []
            }
          }
        ],
        "labels": []
      }      
    ]
}
```

[Overview - Request Modifiers]: /README.md#request-modifiers
[Contacts]: README.md
