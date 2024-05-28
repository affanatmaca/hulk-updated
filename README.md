
# HULK - HTTP Unbearable Load King

HULK (Http Unbearable Load King) is a powerful DoS tool designed to generate massive loads on HTTP servers, bringing them to their knees by exhausting their resource pool. This tool is intended for research and educational purposes only.

## Features

- **Unique Request Generation**: Generates unique and obfuscated HTTP requests to bypass caching engines and directly hit the server's resource pool.
- **User Agent Spoofing**: Uses a wide range of user agent strings to simulate different browsers and devices.
- **Referer Spoofing**: Generates random referer headers to obscure the source of the requests.
- **Configurable Parameters**: Customize the load with different settings for concurrency, request rate, and more.

## Usage

### Prerequisites

- Python 3.x

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/affanatmaca/hulk.git
   cd hulk
   ```

2. Install required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Running HULK

To start a DoS attack, use the following command:
```bash
python3 hulk.py <url> [safe]
```

- `<url>`: The target URL to attack.
- `[safe]` (optional): If specified, HULK will automatically stop after sending requests.

#### Example
```bash
python3 hulk.py https://example.com safe
```

## Code Explanation

### Functions

- `useragent_list()`: Generates a list of user agent strings.
- `referer_list()`: Generates a list of referer URLs.
- `buildblock(size)`: Builds a random ASCII string of the specified size.
- `httpcall(url)`: Makes an HTTP request with random parameters and headers.
- `inc_counter()`: Increments the global request counter.
- `set_flag(val)`: Sets the global flag variable.
- `set_safe()`: Sets the global safe variable.

### Classes

- `HTTPThread`: A thread class that continuously makes HTTP requests.
- `MonitorThread`: A thread class that monitors the number of requests sent and prints the status.

## Legal Disclaimer

**WARNING**: This tool is provided for educational purposes only. Using HULK to attack targets without prior mutual consent is illegal. The authors of this tool are not responsible for any misuse or damage caused by this tool.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
