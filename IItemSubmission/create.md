## Create

Create a new item using the API. New items get either approved or denied by support.

#### HTTP Request

`POST https://api-icm.wax.io/api/IItemSubmission/create`

#### Authentication

API key required. Input name is `api_token`.

#### Input

| Parameter | Type | Required | Description |
| - | - | :-: | - |
| internal_app_id | int | + | WAX App ID for `12 - WAX Stickers`, `14 - WAX Digital Art` and `32 - WAX Collectible Cards` |
| name | string | + | Item name (simpler/shorter version of `makert_name`) <br> Example: "WAX Dog" |
| market_name | string | + | Full market name (must be unique per `internal_app_id`) <br> Example: "Sticker &#124; WAX Dog [Special Edition]" <br> Example with collection: "Sticker &#124; {Collection Name} &#124; WAX Dog" |
| image_generic | string | + | Item image that must be a static.wax.io URL <br><br>**Tip.** You can use our [Upload Image](/IItemSubmission/upload-image.md) endpoint to upload your image and get a valid static.wax.io image URL. |
| amount | int | + | Number of items to be generated (copies) <br><br>**Important.** If you add Unique Attribute rules in the `json_attributes` input, those copies won't be identical. To learn more about the Unique Attributes, see the [Dynamic Item Attributes](/IItemSubmission.md#dynamic-attributes) section. |
| color | string | + | Color hex (#aa0000), related with Rarity |
| rarity_name | string |   | Rarity name (Legendary, Rare, etc.) |
| collection_name | string |   | Collection name where the item belongs <br>**Tip.** Use to group your items together. You can also add the `collection_name` to your `market_name` input in order to make it unique. |
| external_id | string |   | ID linking this item to your records <br>Example: You can use this optional identification field to store information about your item in a external location.<br><br>**Note.** It's not guaranteed to be a unique ID on our side. |
| instant_sell_enabled | bool |   | Enable instant sell for items with the `Verified_Authentic` `json_attribute` set to `"Yes"` <br><br>Default value is set to false/no. |
| instant_sell_value | int |   | Instant sell value for each item in USD cents<br><br>**Tip.** Upon submission, you get charged `instant_sell_value`\*`amount` from your WAX Points balance. Denied submissions get funds returned to corresponding account. |
| json_attributes | json |   | [Dynamic Item Attributes](/IItemSubmission.md#dynamic-attributes) in json format |

### Output

| Parameter | Type | Description |
| - | - | - |
| submission_id | int | Newly created submission's ID |
