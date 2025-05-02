# Project Setup and Running Guide

This guide provides detailed instructions to set up and run the CARLA simulator, Flask APIs, MongoDB tunneling, traffic generation, backend, frontend, and WebSocket streaming.

`SSRCP React Frontend Application: `https://github.com/pavithramg11/SSRCP

`SSRCP Node Backend Application: `https://github.com/pavithramg11/ssrcp_backend

`SSRCP Flask Backend Application: `https://github.com/pavithramg11/SSRCP_FLASK

---
## Prerequisites

1. **System Requirements**: Ensure your system meets the CARLA simulator requirements.
2. **Installed Software**:
   - Python 3.7+
   - MongoDB
   - CARLA simulator (download and set up using `CARLA_SETUP.pdf` in the project root)
   - Node.js (for frontend, if applicable)
3. **Network Configuration**: For remote servers, configure SSH tunneling for required ports.

---

## Step 1: Start the CARLA Simulator

1. Navigate to the CARLA simulator root directory.
2. Start the CARLA simulator using the `.sh` file:
   ```bash
   ./CarlaUE4.sh --no-rendering


## Step 2: Start Flask APIs

Navigate to the Flask API directory:
```bash
  cd SSRCP_FLASK
```

Set up a virtual environment (if not already done):
```bask
  python -m venv venv
  source venv/bin/activate  # Use `venv\Scripts\activate` on Windows
  pip install -r requirements.txt
```

Start the Flask APIs:
```bash
  python run.py
```

### Step 3: Set Up SSH Tunneling

If you're using a remote server for MongoDB or Flask, set up SSH tunneling for the necessary ports:

Open a terminal on your local machine.
Create an SSH tunnel:
```bash
  ssh -L 27017:<remote_host>:27017 -L 5000:<remote_host>:5000 <username>@<server_ip>
```

### Step 4: Generate Traffic Using Python Script

Navigate to the traffic generation script directory from `carla root` directory.
Run the traffic generation script:
```bash
  python3 ./PythonAPI/examples/generate_traffic.py --hero -w 200 -n 100
```


### Step 5: Start the Flask Backend 
Navigate to the `SSRCP_FLASK` directory of the project.
Start the backend service:
```bash
  source venv/bin/activate
  python run.py
```

### Step 6: Start WebSocket Streaming and NodeJs Backend

Navigate to the `ssrcp_backend` project directory.
Start the WebSocket streaming service:
```bash
  node DemoStreamLocWS.js
  yarn start
```

### Step 6: Start React Application Frontend

Navigate to the `SSRCP` project directory.
Start the WebSocket streaming service:
```bash
  yarn start
```

