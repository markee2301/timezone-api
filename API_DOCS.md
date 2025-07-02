# Timezone API Documentation

This API provides timezone, offset, and region information for North American area codes.

## Base URL

```
https://<your-render-url>
```

## Endpoints

### GET `/timezone`

Retrieve timezone information for a given 3-digit area code.

#### Query Parameters

- `areaCode` (string, required): The 3-digit area code to look up.

#### Example Request

```
GET /timezone?areaCode=201
```

#### Example Response

```
{
  "areaCode": "201",
  "timezone": "America/New_York",
  "offset": "EST",
  "region": "New Jersey"
}
```

#### Error Response

If the area code is missing or invalid:

```
{
  "error": "Please provide a valid 3-digit areaCode as a query parameter."
}
```

If the area code is not found:

```
{
  "areaCode": "999",
  "timezone": "Unknown",
  "offset": "Unknown",
  "region": "Unknown"
}
```

---

### GET `/`

Returns a simple status message.

#### Example Request

```
GET /
```

#### Example Response

```
Timezone API is running. Use /timezone?areaCode=XXX
```

---

## Deployment

- Deploy this API to [Render](https://render.com/) or any Node.js hosting platform.
- The server listens on the port defined by the `PORT` environment variable or defaults to `3000`.

## Notes

- All area codes must be provided as 3-digit strings (e.g., `"201"`).
- The API supports only North American area codes as defined in the source code.
