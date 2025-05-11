# MCP-Weather-Alert

# Overview
This service allows you to fetch active weather alerts for any US state using the NWS public API. Built with FastMCP, it provides a simple interface to query weather hazards and emergency information.

# Features
Retrieve active weather alerts by US state code
Format alert data into human-readable information
Proper error handling for API requests
Asynchronous operation for improved performance

# Requirements
Python 3.7+
FastMCP
httpx

# Installation
Install the required dependencies:
bashpip install fastmcp httpx

Include the service in your FastMCP environment.

# Get Weather Alerts
Retrieve active weather alerts for a specific US state:
pythonfrom your_mcp_client import client

# Get alerts for California
alerts = await client.tools.get_alerts(state="CA")
print(alerts)
The response includes formatted alert information:

# Event type
Affected area
Severity
Description
Safety instructions

# Echo Resource
The service also includes a simple echo resource for testing:
pythonresponse = client.resources.echo(message="Hello World")
print(response)  # Outputs: "Resource echo: Hello World"
API Reference
get_alerts(state)
Get weather alerts for a US state.
Parameters:

state (str): Two-letter US state code (e.g., CA, NY, TX)

Returns:

String containing formatted alert information or status message

echo_resource(message)
Echo a message (for testing purposes).
Parameters:

message (str): Message to echo

Returns:

String with the echoed message

Technical Details

Uses the National Weather Service API (https://api.weather.gov)
Implements proper User-Agent headers
Handles API timeouts and errors gracefully
Formats complex JSON responses into readable text
