# Timezone API Documentation

This API provides timezone, offset, and region information for North American area codes.

## Base URL

```
https://timezone-api-sypv.onrender.com/
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

## Notes

- All area codes must be provided as 3-digit strings (e.g., `"201"`).
- The API supports only North American area codes as defined in the source code.
