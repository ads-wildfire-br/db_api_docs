# `/load_vector_data` (POST)

This endpoint loads geolocation vector data into the system based on a list of specified entries. The data is provided in a structured format, allowing for batch insertion.

Request Payload Format:

- `data_list` (list of lists, required): Each entry in the list should contain the following elements:
    1. ISO 8601 formatted datetime string (timestamp).
    2. Latitude (float, degrees).
    3. Longitude (float, degrees).
    4. Altitude (float, meters).
    5. Value (float).
    6. Tag (string representing the metric type).

Example usage with cURL:

```bash
curl -X POST -H "Content-Type: application/json" -d '{"data_list": [{"timestamp": "2022-02-15T10:30:00Z", "latitude": -23.210, "longitude": -45.896, "altitude": 100.0, "value": 25.5, "tag": "temperature"}, {"timestamp": "2022-02-16T12:45:00Z", "latitude": -23.215, "longitude": -45.900, "altitude": 150.0, "value": 28.2, "tag": "humidity"}, {"timestamp": "2022-02-17T15:15:00Z", "latitude": -23.200, "longitude": -45.910, "altitude": 200.0, "value": 22.0, "tag": "pressure"}, {"timestamp": "2022-02-18T17:30:00Z", "latitude": -23.195, "longitude": -45.890, "altitude": 120.0, "value": 30.8, "tag": "temperature"}, {"timestamp": "2022-02-19T20:00:00Z", "latitude": -23.225, "longitude": -45.905, "altitude": 180.0, "value": 26.5, "tag": "humidity"}]}' http://localhost:5000/load_data
```

Response:

- `status` (string): Indicates the status of the request ("success" or "error").
- `message` (string): Provides additional information about the request result.

Example Response:

```json
{
  "status": "success",
  "message": "Data loaded successfully"
}
```

Note: Ensure that the order of elements in each entry of the `data_list` matches the order specified in the response format.

Example in python [here](/tutorials/test_load_vector_data.py).
