# bridge-q

Arduino uno Q Bridge, for the python that runs in the terminal.

Python client for Arduino router MessagePack-RPC over a Unix socket. This code is gathered from https://docs.arduino.cc/tutorials/uno-q/routerbridge-multilanguage/

## Install

From GitHub (latest `main`):

```bash
pip install git+https://github.com/Nikola-Academy/bridge-q.git
```

A specific branch, tag, or commit:

```bash
pip install git+https://github.com/Nikola-Academy/bridge-q.git@main
pip install git+https://github.com/Nikola-Academy/bridge-q.git@v0.1.0
```

Via SSH:

```bash
pip install git+ssh://git@github.com/Nikola-Academy/bridge-q.git
```

Editable install from a local clone:

```bash
pip install -e .
```

## Usage Example

```python
from bridge_q import ArduinoBridge

bridge = ArduinoBridge()  # default: /var/run/arduino-router.sock

if bridge.connect():
    result = bridge.call("some_method", arg1, arg2)
    bridge.notify("some_event", value)
    bridge.disconnect()
```

Custom socket path:

```python
bridge = ArduinoBridge(socket_path="/tmp/arduino-router.sock")
```

## Requirements

- Python 3.8+
- POSIX OS (Linux / macOS) — uses Unix domain sockets
- `msgpack`
