## Create

Create a new item using the API. Then once created item, will either be approved or denied by support.

#### HTTP Request

`POST https://api-icm.wax.io/api/IItemSubmission/create`

#### Authentication

API key required.

#### Input

| Parameter | Type | Required | Description |
| - | - | :-: | - |
| internal_app_id | int | + | WAX App ID. |
| name | string | + | Item name. |
| market_name | string | + | Item market name (must be unique per app_id). |
| image_generic | string | + | Item image url. |
| amount | int | + | Amount of identical items to be generated |
| color | string | + | Color hex (fff), related with rarity. |
| rarity_name | string |   | Rarity name (Legendary, Rare, etc). |
| collection_name | string |   | Name of the collection this item belongs to. |
| external_id | string |   | Searchable id that links this item with your records (not guaranteed to be unique in our side). |
| instant_sell_enabled | bool |   | Enable instant sell for this item. Only available for items with de Verified_Authentic json_attribute set to "Yes". Default is false. |
| instant_sell_value | int |   | Instant sell value for each item in USD cents. Upon submission, you will be charged this value*amount from your OPSkins balance. If the submission is denied, funds will return to your account. |
| json_attributes | json |   | Dynamic item attributes in json format. |

### Output

| Parameter | Type | Description |
| - | - | - |
| submission_id | int | Newly created submission's ID |