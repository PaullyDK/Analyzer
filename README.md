⸻

Log Analysis & Metrics Tool

A lightweight Python CLI tool that parses structured server log files and outputs aggregated metrics in JSON format.

Overview

This script analyzes log files containing HTTP request data and computes:
	•	Total number of requests
	•	Request count per endpoint
	•	Success rate (2xx status codes)
	•	Average response time (ms)

It is designed to demonstrate:
	•	File parsing
	•	Basic analytics
	•	Dictionary-based aggregation
	•	Error handling
	•	JSON serialization

⸻

Expected Log Format

Each line in the log file should follow this format:

METHOD ENDPOINT STATUS RESPONSE_TIME

Example:

GET /api/users 200 120ms
POST /api/login 401 45ms
GET /api/users 200 98ms

Fields:
	•	METHOD → HTTP method (GET, POST, etc.)
	•	ENDPOINT → API route
	•	STATUS → HTTP status code
	•	RESPONSE_TIME → Response time in milliseconds (must include ms)

Invalid or malformed lines are skipped automatically.

⸻

How It Works

The script:
	1.	Reads each line of the log file
	2.	Splits the values into components
	3.	Tracks:
	•	Total requests
	•	Per-endpoint counts
	•	Successful responses (2xx)
	•	Total response time
	4.	Calculates:
	•	Success rate (%)
	•	Average response time (ms)
	5.	Outputs a formatted JSON summary

⸻

Example Output

{
  "totalRequests": 3,
  "requestsPerEndpoint": {
    "/api/users": 2,
    "/api/login": 1
  },
  "successRate": 66.66666666666666,
  "averageResponseTime": 87
}


⸻

How to Run

Make sure you have Python 3 installed.

From the project directory:

python3 your_script_name.py

The script currently analyzes:

log.txt
log1.txt
log2.txt

You can modify the file names at the bottom of the script as needed.

⸻

Strengths Demonstrated
	•	Dictionary-based counting pattern
	•	Defensive parsing with try/except
	•	Clean metric aggregation
	•	JSON formatting for structured output
	•	Simple, readable CLI execution

⸻

Potential Improvements (Next Iteration Ideas)
	•	Accept filename as a command-line argument
	•	Add error handling for empty files
	•	Handle division-by-zero if no valid requests
	•	Export results to a JSON file
	•	Add response time percentiles (p95, p99)
	•	Convert into a Flask API or Dockerized microservice

⸻

Why This Project Matters

This tool demonstrates foundational backend engineering skills:
	•	Log parsing
	•	Metric aggregation
	•	API monitoring concepts
	•	Data transformation
	•	Clean output formatting

It reflects real-world observability and analytics workflows in a simplified form.

⸻
