# Tracker Server

A lightweight tracker server, built with Node.js and MongoDB, designed to coordinate peer-to-peer (P2P) file sharing similar to BitTorrent.

## Features

- Manages torrent metadata and file information
- Tracks active peers and file pieces
- RESTful API for node interactions
- Real-time peer management and piece tracking
- Background processing of file pieces
- CORS support for cross-domain requests

## Prerequisites

- Node.js >= 16.20.1
- MongoDB >= 4.0
- npm or yarn for package management

## Installation & Setup

1. **Install dependencies**:

   ```bash
   npm install
   ```

2. **Configure environment**: Create a `.env` file with the following variables:

   ```env
   HOST=localhost
   PORT=8081
   ```

3. **Start server**:

   ```bash
   npm run dev
   ```

## API Documentation

### Node Management

- **Register/Update Node**

  - **POST** `/api/nodes`
  - **Body**:
    ```json
    {
      "ip": "string",
      "port": "number"
    }
    ```

- **Set Node Offline**
  - **PUT** `/api/nodes`
  - **Body**: Same as register/update

### File Operations

- **Share New File**

  - **POST** `/api/files`
  - **Body** (`multipart/form-data`):
    - `name`: File name
    - `magnet_text`: Magnet link
    - `torrent_file`: .torrent file
    - `ip`: Peer IP address
    - `port`: Peer port

- **Get Peers for File**

  - **POST** `/api/files/peers`
  - **Body**:
    ```json
    {
      "magnet_text": "string"
    }
    ```

- **Update Piece Information**

  - **PUT** `/api/pieces`
  - **Body**:
    ```json
    {
      "magnet_text": "string",
      "piece_index": "number",
      "ip": "string",
      "port": "number"
    }
    ```

- **Download Torrent File**
  - **GET** `/api/files/:id/download`
  - **URL Params**:
    - `id`: File ID

## Project Structure

```
tracker/
├── src/
│   ├── config/       # Configuration files
│   ├── controller/   # Request handlers
│   ├── model/        # Database models
│   ├── route/        # API routes
│   └── utils/        # Helper utilities
├── app.js            # Server entry point
└── package.json      # Project metadata
```

## Models

### Node

- **IP address**
- **Port number**
- **Online status**
- **Last ping time**

### File

- **Name**
- **Magnet link**
- **Torrent file data**
- **Processing status**

### Piece

- **File reference**
- **Piece index**
- **List of nodes containing piece**

## Dependencies

- **express**: Web server framework
- **mongoose**: MongoDB object modeling
- **multer**: File upload management
- **bencode**: BitTorrent encoding/decoding
- **cors**: Cross-Origin Resource Sharing support
- **dotenv**: Environment configuration
