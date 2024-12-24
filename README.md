# Website Status Checker

This Python program reads a list of website URLs from a CSV file and checks their HTTP status codes. It uses random user agents to simulate requests, helping bypass bot detection mechanisms.

## Features
- Reads website URLs from a CSV file.
- Ensures URLs use the correct HTTP/HTTPS scheme.
- Generates random Firefox user agents for requests.
- Fetches and displays HTTP status codes along with descriptions.
- Handles errors gracefully for inaccessible websites.

## Requirements
- Python 3.x
- Required libraries:
  - `requests`: For making HTTP requests.
  - `fake-useragent`: For generating random user agents.

### Install Dependencies
```bash
pip install requests fake-useragent
```

## Usage
1. Prepare a CSV file named `websites.csv` with URLs in the second column.
2. Run the script using the following command:
```bash
python website_checker.py
```
3. The program will output the status codes of each website along with a description.

### Example CSV File (`websites.csv`)
```csv
Name,URL
Google,www.google.com
GitHub,https://github.com
Example,http://example.com
```

### Sample Output
```
https://www.google.com (200 OK Request fulfilled, document follows)
https://github.com (200 OK Request fulfilled, document follows)
https://example.com (200 OK Request fulfilled, document follows)
```

## Configuration
- CSV File Path: Update the file path in the `get_websites` function if the CSV file is located elsewhere.
- User-Agent: The script generates a random Firefox user-agent string using `fake-useragent`. You can modify the `get_user_agent` function to use other browsers or fixed strings.

## Error Handling
- Handles invalid or missing URLs by prepending `https://` if necessary.
- Logs errors for websites that cannot be reached.
