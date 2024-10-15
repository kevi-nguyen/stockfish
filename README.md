# Stockfish-Service

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/kevi-nguyen/stockfish-service.git
   cd stockfish-service
   ```

2. **Install Dependencies**:
   Activate your virtual environment and install the required dependencies from the `requirements.txt` file.
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Service**:
   To start the button service, use the following command:
   ```bash
   python Stockfish-API.py
   ```
   This will start the FastAPI service on `http://0.0.0.0:8081`.

**Stockfish Path Configuration**:
The project relies on Stockfish for chess move analysis, and it needs to know where the Stockfish executable is located. By default, the code will look for `stockfish` (or `stockfish.exe` on Windows). However, this assumes either:
- The executable is in the same directory as the script.
- Or it is in the system's `PATH` environment variable.
  
If Stockfish is installed in a custom directory, you can either:
1. Place `stockfish.exe` in the same folder as your script.
2. Set the correct path explicitly in the code, like so:

```python
STOCKFISH_PATH = os.getenv('STOCKFISH_PATH') or 'C:/path/to/stockfish.exe'
stockfish = Stockfish(path=STOCKFISH_PATH)
```

For Linux systems, update the path similarly with the appropriate executable path, such as:

```python
STOCKFISH_PATH = os.getenv('STOCKFISH_PATH') or '/usr/local/bin/stockfish'
```
