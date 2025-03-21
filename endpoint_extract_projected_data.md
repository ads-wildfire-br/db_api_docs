# `/extract_projected_data` (POST)

This endpoint retrieves a GeoTIFF file from the system based on the provided `id`. The GeoTIFF file is then sent as an attachment in the response.

Request Parameters:

- `id` (integer, required): The unique identifier of the projected data entry.

Example usage with cURL:

```bash
curl -X POST http://localhost:5000/extract_projected_data?id=123
```

Response:

- The GeoTIFF file as an attachment.

Example Response:

The response will contain the GeoTIFF file as an attachment, which can be downloaded by the client.

Note: Ensure that the `id` provided corresponds to an existing entry in the database.

Example in python [here](/tutorials/test_extract_projected_data.py).