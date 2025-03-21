# `/extract_data` (POST, GET)

This endpoint extracts geolocation data based on specified filters. The parameters are optional, allowing for flexible queries.

Request Payload Format:

- `time_begin` (string, optional): Start date and time in the ISO 8601 format.
- `time_end` (string, optional): End date and time in the ISO 8601 format.
- `lat_begin` (float, optional): Minimum latitude in degrees (>= -90.0)
- `lat_end` (float, optional): Maximum latitude in degrees (<= 90.0>)
- `long_begin` (float, optional): Minimum longitude in degrees (>= -180.0)
- `long_end` (float, optional): Maximum longitude in degrees (<= 180.0)
- `tag` (string, optional): Tag to filter the data.

Example usage with cURL:

```bash
curl -X POST -H "Content-Type: application/json" -d '{"lat_begin": -30.0, "lat_end": -20.0, "long_begin": -50.0, "long_end": -40.0, "tag": "humidity"}' http://localhost:5000/extract_data
```

Response:

- `status` (string): Indicates the status of the request ("success" or "error").
- `message` (string): Provides additional information about the request result.

Example Response:

```json
{
  "status": "success",
  "message": "Data extraction successful",
  "data": [
    {
      "timestamp": "2022-02-15T10:30:00Z",
      "latitude": -25.0,
      "longitude": -45.0,
      "altitude": 100.0,
      "value": 25.5,
      "tag": "humidity"
    },
    {
      "timestamp": "2022-02-16T12:45:00Z",
      "latitude": -23.5,
      "longitude": -44.5,
      "altitude": 150.0,
      "value": 28.2,
      "tag": "humidity"
    },
    {
      "timestamp": "2022-02-17T15:15:00Z",
      "latitude": -22.0,
      "longitude": -45.5,
      "altitude": 200.0,
      "value": 22.0,
      "tag": "humidity"
    }
    // ... additional data entries
  ]
}
```

Note: The response includes a list of extracted data entries.

Example in Python [here](/tutorials/test_extract_data.py).