# Python HTTP Proxy Server

This project implements a simple HTTP proxy server in Python. The server can handle HTTP requests and proxy them between clients and destination servers. 

## Features

- Handles HTTP and HTTPS (CONNECT) requests
- Provides a customizable logging system
- Can be configured with different hostnames and ports

## Requirements

- Python 2.7 or Python 3.x
- Socket programming knowledge is helpful but not required

## Usage

To run the proxy server, follow these steps:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-repo/proxy.py
   cd proxy.py
   ```

2. **Run the proxy server:**
   ```bash
   python proxy.py --hostname <hostname> --port <port> --log-level <log-level>
   ```

   - `--hostname`: The hostname or IP address where the proxy server will run. Default is `127.0.0.1`.
   - `--port`: The port number where the proxy server will listen for connections. Default is `8899`.
   - `--log-level`: The logging level. Choose from `DEBUG`, `INFO`, `WARNING`, `ERROR`, or `CRITICAL`. Default is `INFO`.

   Example:
   ```bash
   python proxy.py --hostname 127.0.0.1 --port 8899 --log-level INFO
   ```

3. **Connect to the proxy server:**
   Configure your HTTP client (e.g., browser, curl) to use the proxy server by specifying the hostname and port.

4. **Stop the server:**
   You can stop the server by pressing `Ctrl + C` in the terminal where it's running.

## How It Works

The proxy server acts as an intermediary between a client and a destination server. It listens for incoming client connections, parses HTTP requests, and forwards them to the destination server. Once the server responds, the proxy server forwards the response back to the client.

### Key Classes

- `HttpParser`: Parses incoming HTTP requests and responses.
- `ChunkParser`: Handles chunked transfer encoding in HTTP responses.
- `Connection`: Abstract class representing a TCP connection.
- `Server`: Represents a connection to a destination server.
- `Client`: Represents an accepted client connection.
- `Proxy`: Implements the proxy logic, handling the connection between a client and a server.
- `TCP`: Base class for the TCP server.
- `HTTP`: HTTP proxy server implementation that extends `TCP`.

## Logging

The server uses Python's `logging` module for logging. You can control the verbosity of the logs using the `--log-level` argument.

- `DEBUG`: Detailed information, typically of interest only when diagnosing problems.
- `INFO`: Confirmation that things are working as expected.
- `WARNING`: An indication that something unexpected happened, but the proxy is still working.
- `ERROR`: A more serious problem, the proxy may still be working, but some functionality is broken.
- `CRITICAL`: A very serious error, indicating that the proxy may be unable to continue running.

## License

This project is licensed under the BSD License. See the LICENSE file for details.
