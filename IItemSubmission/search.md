## Search

Retrieve submission data, that matches or is like `market_name`.

#### HTTP Request

`GET https://api-icm.wax.io/api/IItemSubmission/search`

#### Authentication

API key required.

#### Input

| Parameter | Type | Required | Description |
| - | - | :-: | - |
| q | string |  | Searches submissions using market_name |

### Output

| Parameter | Type | Description |
| - | - | - |
| submissions | Array | Returns Array of [Standard Item Submission Object](/IItemSubmission.md#minified-item-submission-object) |
