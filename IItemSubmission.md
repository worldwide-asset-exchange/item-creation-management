## IItemSubmission

- [IItemSubmission/create](IItemSubmission/create.md)
- [IItemSubmission/read](IItemSubmission/read.md)
- [IItemSubmission/search](IItemSubmission/search.md)
- [IItemSubmission/upload-image](IItemSubmission/upload-image.md)
- [IItemSubmission/refill](IItemSubmission/refill.md)

## Item Submission Statuses
Status | Desciption
------ | ----------
1 | New Request
2 | Awaiting Approval - (Support Team will Approve/Deny Item)
3 | Denied
4 | Approved - (Item has been approved and is awaiting to be generated on WAX)
5 | Created

## Standard Item Submission Object
Parameter | Type | Description
--------- | -----| -------- 
id | int | Submission ID
submission_user_id    | int | UserID of user that submitted the item
internal_app_id| int | Internal App ID
name | string | Simpler name for an item (compared to full market_name) -> "WAX Dog".
market_name | string | Full market name -> "Sticker &#124; WAX Dog [Special Edition]".
image_generic | string | Item Image
amount | int | Amount requested
color | string | Hexadecimal color for rarity color.
rarity_name | string | Name of the Rarity
collection_name | string | Collection Name item belongs to.
destination_user_id | int | UserID to send the item to. (This is default to the user that submits the item right now)
status | int | [Item Submission Statuses](/IItemSubmission.md#item-submission-statuses)
wax_item_definition | int/null | Once item is created, this will be its item_definition
json_attributes | json | This holds item [Dynamic Attributes](/IItemSubmission.md#dynamic-attributes).
created_at | timestamp | Created timestamp
updated_at | timestamp | Updated timestamp

## Minified Item Submission Object
Parameter | Type | Description
--------- | -----| -------- 
id | int | Submission ID
market_name | string | Full market name e.g. Sticker | WAX DOG.
image_generic | string | Item Image
color | string | Hexadecimal color for rarity color.
status | int | [Item Submission Statuses](/IItemSubmission.md#item-submission-statuses)

## Dynamic Attributes
The `json_attributes` field allows you to add `key:value` pairs that represent attributes of your item. Those will be public available via WAX API's.

Below is a list of some useful/important pre-defined attributes that you may want to add:

Attribute name | Description
--------- | -------- 
Verified_Authentic | Value may be Yes or No. If not provided, defaults to No. Verified Collectible means that you own the image on this submission and can provide proof of ownership. These submissions take longer to approve and will show as Verified Authentic in WAX Trade and OPSkins. <br>Example: `{"Verified_Authentic": "Yes"}`.
product_box_display | Comma-separated names of the attributes you want to be visible in OPSkins and WAX Trade product boxes. Limited to 5 custom attributes. All the other attributes are still available via API to be used on dApps/websites. <br>Example: `{"class":"Fighter", "mana": 150, "hp": 90, "product_box_display": "class, hp"}`. <br>In the example above, attributes `class` and `hp` will be visible in the product box, while attribute `mana` will be available via API only.
markdown_description | Use this attribute to provide a description for your item. It supports basic html and markdown tags. The description will be available via API and will show up for your item in WAX Trade, WAX Explorer and OPSkins. You don't need to add this attribute to the product_box_display. <br>Example: `{"markdown_description": "This is a <strong>cool</strong> description field!"}`.

You can also make use of our Unique Attribute rules to make each item one-of-a-kind. This can be done by adding attributes with the prefix `unique_rule_` into the `json_attributes` field with the following structure for the attribute value: `unique_{type}_{min}_{max}` (for now, type is either `integer` of `float`). Examples:
 - "unique_rule_bite_chance": "unique_float_0_1" - Each item copy generated from this submission will have a `unique_bite_chance` attribute with a float value between 0 and 1.
 - "unique_rule_happiness_level": "unique_integer_0_100" - Each item copy generated from this submission will have a `unique_happiness_level` attribute with a integer value between 0 and 100.
The resultant unique attributes can be added to the `product_box_display`. 
Example: `{"unique_rule_bite_chance": "unique_float_0_1", "unique_rule_happiness_level": "unique_integer_0_100", "product_box_display": "unique_happiness_level"}`.
In the example above, the `unique_bite_chance` attribute will be available via API only, while the `unique_happiness_level` attribute will be visible in the Product Box for WAX Trade and OPSkins.
