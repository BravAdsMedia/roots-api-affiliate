### Usage

Poll this endpoint to obtain the available offers you can use to request a new campaign.

### URI / Method

* Endpoint: `https://roots.bravads.com/api/campaignrequests/available_offers` (Method: `GET`)

### Response fields

Field           | Data Type | Nullable | Notes
--------------- | --------- | -------- | --------------------------------------------------------------
id              | integer   | No       | The offer ID.
name            | string    | No       | The offer name.
traffic_rating  | string    | Yes      | Traffic rating. Check the Related Entities section for a list of possible values.
incent          | boolean   | Yes      | If the campaign allows incent traffic.
preview         | string    | Yes      | The fullsize preview image URL. Hotlinking not allowed.
preview_thumb   | string    | Yes      | The thumbnail preview image URL. Hotlinking not allowed.
payout_type     | string    | No       | The payout type. Check the Related Entities section for a list of possible values.
payout_value    | float     | No       | The payout value.
status          | string    | No       | The offer status. Posible values: Available, Pending, Denied. Pending indicates you have already requested a campaign and the request is being evaluated. Denied means you have already requested a campaign and the request was not approved. 

### Sample Response

```
{
    "data": [
        {
            "id": 22,
            "name": "Sample Offer 1",
            "traffic_rating": "Mainstream",
            "incent": true,
            "preview": "https://roots.bravads.com/x/previews/22.jpg",
            "preview_thumb": "https://roots.bravads.com/x/previews/22_t.jpg",
            "payout_type": "CPC",
            "payout_value": 0.001,
            "status": "Available"
        },
        {
            "id": 25,
            "name": "Sample Offer 2",
            "traffic_rating": "Adult",
            "incent": false,
            "preview": null,
            "preview_thumb": null,
            "payout_type": "CPA",
            "payout_value": 1.25,
            "status": "Pending"
        }
    ]
}
```
