# API Documentation for WAX ICM (Item Creation Management) Documentation

## API Interfaces
* [IItemSubmission](IItemSubmission.md)

## API Response
A typical response may look like this:
```json
{
  "success":true,
  "message":"Your request was received."
}
```

A typical error response may look like this:
```json
{
  "success":false,
  "error":"The amount must be an integer."
}
```