## Read

Retrieve user submission data. Submission ID may be applied. In the case of no ID, all submissions made by the user get returned to them. 

#### HTTP Request

`GET https://api-icm.wax.io/api/IItemSubmission/read`

#### Authentication

API key required. Input name = `api_token`

#### Input

| Parameter | Type | Required | Description |
| - | - | :-: | - |
| submission_id| integer|  | Retrieve your submission with matching ID |

### Output

| Parameter | Type | Description |
| - | - | - |
| submissions | Array | Returns Array of [Standard Item Submission Object](/IItemSubmission.md#standard-item-submission-object) |
