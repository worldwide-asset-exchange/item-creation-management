## Create

Create a new item using the API. Then once created item, will either be approved or denied by support.

#### HTTP Request

`POST https://api-icm.wax.io/api/IItemSubmission/create`

#### Authentication

API key required. Input name is `api_token`.

#### Input

| Parameter | Type | Required | Description |
| - | - | :-: | - |
| internal_app_id | int | + | WAX App ID. Enabled apps are `12 - WAX Stickers`, `14 - WAX Digital Art` or `32 - WAX Collectible Cards`. |
| name | string | + | Item name (simpler/shorter version of `makert_name`). <br> Example: "WAX Dog". |
| market_name | string | + | Full market name (must be unique per `internal_app_id`). <br> Example: "Sticker &#124; WAX Dog [Special Edition]". |
| image_generic | string | + | Item image url. Must be a static.wax.io URL. You can use our [Upload Image](/upload-image.md) endpoint to upload your image and get a valid static.wax.io image url. |
| amount | int | + | Number of items to be generated (copies). If you add Unique Attribute rules in the `json_attributes` input, those copies won't be identical. See the [Dynamic Item Attributes](/IItemSubmission.md#dynamic-attributes) section to learn more about the Unique Attributes. |
| color | string | + | Color hex (#aa0000), related with rarity. |
| rarity_name | string |   | Rarity name (Legendary, Rare, etc). |
| collection_name | string |   | Name of the collection this item belongs to. This can be used to group your items together. You can also add the `collection_name` to your `market_name` input in order to make it unique. <br>Sticker example: "Sticker &#124; {Collection Name} &#124; WAX Dog" |
| external_id | string |   | Id that links this item with your records (not guaranteed to be unique in our side). This optional identification field can be used if you want to store information about your item in a external location. |
| instant_sell_enabled | bool |   | Enable instant sell for this item. Only available for items with de Verified_Authentic json_attribute set to "Yes". Default is false. |
| instant_sell_value | int |   | Instant sell value for each item in USD cents. Upon submission, you will be charged `instant_sell_value`*`amount` from your WAX Points balance. If the submission is denied, funds will return to your account. |
| json_attributes | json |   | [Dynamic Item Attributes](/IItemSubmission.md#dynamic-attributes) in json format. |

### Output

| Parameter | Type | Description |
| - | - | - |
| submission_id | int | Newly created submission's ID |
