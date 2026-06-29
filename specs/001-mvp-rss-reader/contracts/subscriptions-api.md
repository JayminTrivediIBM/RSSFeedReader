# Subscriptions API Contract

## POST /api/subscriptions

Creates a new subscription for the current session.

### Request

- **Body**: JSON object with a single field, `url`
- **Example**:
  ```json
  {
    "url": "https://example.com/feed.xml"
  }
  ```

### Response

- **201 Created** on success
- **400 Bad Request** when the URL is empty or whitespace-only
- **409 Conflict** when the same URL is already present in the current session

## GET /api/subscriptions

Returns the current list of subscriptions for the session.

### Response

- **200 OK** with a JSON array of subscription objects
- **Example**:
  ```json
  [
    {
      "id": 1,
      "url": "https://example.com/feed.xml"
    }
  ]
  ```
