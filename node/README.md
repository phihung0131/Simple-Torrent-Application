# P2P File Sharing Application

An application that allows users to share and download files through a peer-to-peer (P2P) network with a graphical interface.

## Features

- File sharing over a P2P network
- Download files from multiple sources simultaneously
- Intuitive graphical interface
- Displays file download/share progress
- Automatic connection to the tracker
- Manages peer-to-peer connections

## System Requirements

- Python 3.7 or higher
- Python libraries:
  - requests
  - bencode.py
  - tkinter (usually included with Python)

## Installation

1. Clone the repository:

2. Install the required libraries:

   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. Start the application:

   ```bash
   python gui.py
   ```

2. Share a file:

   - Click on "Share File"
   - Select the file you want to share
   - Wait for the processing to complete
   - Copy the generated magnet link

3. Download a file:
   - Click on "Download File"
   - Paste the magnet link
   - Wait for the file to download

## Project Structure

- `gui.py`: User interface
- `node.py`: Core P2P node logic
- `peer_connection.py`: Manages connections between peers
- `download_manager.py`: Handles file download processes
- `peer_selector.py`: Selects optimal peers for downloading
- `config.py`: System configuration

## Notes

- The application uses port 52229 for P2P connections
- Ensure this port is not blocked by a firewall
- Downloaded files are saved in the `node_data/downloads` folder
- Torrent information is stored in `node_data/torrents`
