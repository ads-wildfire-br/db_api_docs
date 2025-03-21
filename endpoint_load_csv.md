# `/load_csv` (POST)

This endpoint enables the upload of geolocation data from a CSV file, following the [demo in tutorial](/tutorials/linear_periodic_drone_training.csv).
The CSV file should contain columns: `timestamp`, `dlat` (latitude), `dlong` (longitude), and `value`.
The data will be stored in the database.

Request Payload Format:

- `file` (file, required): The CSV file to be uploaded.

Example usage with cURL:

```bash
curl -X POST -H "Content-Type: multipart/form-data" -F "file=@data.csv" http://localhost:5000/load_csv
```

Response:

- `status` (string): Indicates the status of the request ("success" or "error").
- `message` (string): Provides additional information about the request result.

Example Response:

```json
{
  "status": "success",
  "message": "Data uploaded successfully"
}
```

Note: Ensure that the CSV file adheres to the specified column names and format. The actual format for the column values needs to be determined. They are from the simulator project. TODO.

Example in Python [here](/tutorials/test_load_csv.py).