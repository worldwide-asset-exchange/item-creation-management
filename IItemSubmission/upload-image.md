## Upload Image

Upload image provided by the user and return the static.wax.io image URL.

#### HTTP Request

`POST https://api-icm.wax.io/api/IItemSubmission/upload-image`

#### Authentication

API key required. Input name = `api_token`

#### Input

| Parameter | Type | Required | Description |
| - | - | :-: | - |
| image_file_to_upload | file | + | Image file to upload |
| image_name | string |   | Image name (shows up slugfied as part of the URL) |

#### Output

Parameter | Type    | Description
--------- | -----   | --------
image_url | string  | Full static.wax.io image URL with support to dynamic resolution |
