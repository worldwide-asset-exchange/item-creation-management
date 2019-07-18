## Read

Retrieve user submission data. Submission ID may be applied. If no ID is provided, will return all submissions made by the user.

#### HTTP Request

`GET https://api-icm.wax.io/api/IItemSubmission/read`

#### Authentication

API key required. Input name is `api_token`.

#### Input

| Parameter | Type | Required | Description |
| - | - | :-: | - |
| submission_id| integer|  | Retrieve your submission with matching ID |

### Output

| Parameter | Type | Description |
| - | - | - |
| submissions | Array | Returns Array of [Standard Item Submission Object](/IItemSubmission.md#standard-item-submission-object) |
