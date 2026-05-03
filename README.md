[README.md](https://github.com/user-attachments/files/27312409/README.md)
# SimRail Timetable Exporter

Download timetable data from SimRail API and export to CSV or JSON format.

## Features

- ✅ Fetch all timetables from SimRail API
- ✅ Filter by specific train number
- ✅ Export to CSV or JSON
- ✅ Retry logic with exponential backoff
- ✅ Comprehensive error handling
- ✅ Verbose logging support

## Installation

```bash
git clone https://github.com/yourusername/simrail-timetable-exporter.git
cd simrail-timetable-exporter
pip install -r requirements.txt
```

## Usage

### Basic usage - export all timetables for a server

```bash
python main.py --server en1
```

### Export specific train

```bash
python main.py --server en1 --train 1441
```

### Export to JSON

```bash
python main.py --server de1 --format json
```

### Verbose mode

```bash
python main.py --server pl1 --verbose
```

### Custom output filename

```bash
python main.py --server en1 --output custom_name.csv
```

## API Servers

- `en1`, `en2` - English servers
- `de1`, `de2` - German servers
- `pl1`, `pl2` - Polish servers
- `cz1` - Czech server
- `it1` - Italian server

## Output Format

### CSV Output
Data is exported with the following columns:
- `train_number` - Train number
- `train_type` - Type of train
- `server_code` - Server code
- `line_id` - Line identifier
- `distance` - Total distance
- `travel_time` - Total travel time
- `departure_station` - Departure station name
- `departure_time` - Departure time (HH:MM)
- `arrival_station` - Arrival station name
- `arrival_time` - Arrival time (HH:MM)
- `platform` - Platform number
- `distance_km` - Distance in kilometers
- `available_seats` - Available seats
- `stock_car` - Type of vehicle

### JSON Output
Raw JSON response from the API with all available fields.

## Project Structure

```
simrail-timetable-exporter/
├── main.py                 # Main entry point
├── requirements.txt        # Python dependencies
├── README.md              # This file
├── .gitignore             # Git ignore rules
└── simrail/
    ├── __init__.py
    ├── api.py             # API client
    ├── exporter.py        # CSV/JSON exporter
    └── utils.py           # Utility functions
```

## Notes

- The SimRail API has rate limiting - be respectful with your requests
- Times are in 24-hour HH:MM format
- Some fields may be empty or null depending on the train and server

## License

MIT

## References

- [SimRail API Documentation](https://wiki.simrail.eu/en/API/Timetable-endpoint)
- [SimRail Official Website](https://www.simrail.eu/)
