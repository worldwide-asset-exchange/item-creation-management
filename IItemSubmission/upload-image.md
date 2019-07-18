## Upload Image

Upload image provided by the user and return the image url from static.wax.io.

#### HTTP Request

`POST https://api-icm.wax.io/api/IItemSubmission/upload-image`

#### Authentication

API key required. Input name is `api_token`.

#### Input

| Parameter | Type | Required | Description |
| - | - | :-: | - |
| image_file_to_upload | file | + | Image file to upload |
| image_name | string |   | Image name (will show up slugfied as part of the url) |

#### Output

Parameter | Type    | Description
--------- | -----   | --------
image_url | string  | Full static.wax.io image url with support to dynamic resolution. |
