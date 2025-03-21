# `/load_projected_data` (POST)

This endpoint loads geolocation projected data, GeoTIFF files, into the system. Each entry represents a single GeoTIFF file along with its associated metadata.
The required metadata are:

- `CAPTURE_TIMESTAMP`: ISO 8601 formatted datetime string (timestamp) of the time the image was captured.
- #TODO

Request Payload Format:

- `file` (multipart/form-data, required): A GeoTIFF file to be uploaded.

Example usage with cURL:

```bash
curl -X POST -F "file=@/path/to/your/geotiff/file.tif" http://localhost:5000/load_projected_data
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

Note: Ensure that the GeoTIFF file being uploaded is in the correct format and adheres to the allowed file extensions.

Example in Python [here](/tutorials/test_load_projected_data.py).