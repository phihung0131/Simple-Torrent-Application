# BitTorrent-like File Sharing System

A distributed file sharing system built with a tracker server and peer nodes, enabling efficient file sharing and downloading among users.

## Preview

<video width="640" height="360" controls>
  <source src="preview/pre.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

## 📁 Project Structure

The project consists of two main components:

1. **Tracker**: A central server that manages file sharing metadata and coordinates peer connections.
2. **Node**: Peer nodes that share, download, and manage files, each with a GUI for easy interaction.

### Tracker Component

Located in the `/tracker` directory:

- **Backend**: An Express.js server using MongoDB for data storage.
- **Functionality**: Manages peer connections, tracks file availability, and stores metadata.
- **API**: Provides RESTful API endpoints to facilitate communication with peer nodes.

### Node Component

Located in the `/node` directory:

- **Peer Implementation**: Written in Python to handle file sharing and downloading.
- **GUI**: Provides a user-friendly interface for interaction.
- **Functionality**: Manages piece-based file transfer and allows users to share files with other peers.

## 🚀 Setup & Installation

### 1. Tracker Setup

1. **Navigate to the tracker directory**:

   ```sh
   cd tracker
   ```

2. **Install dependencies**:

   ```sh
   npm install
   ```

3. **Environment Configuration**:

   - Create a `.env` file with your MongoDB connection string:
     ```env
     MONGO_URI=your_mongodb_connection_string
     ```

4. **Start the tracker server**:
   ```sh
   npm run dev
   ```

### 2. Node Setup

1. **Navigate to the node directory**:

   ```sh
   cd node
   ```

2. **Install dependencies**:

   ```sh
   pip install -r requirements.txt
   ```

3. **Start the node application**:
   ```sh
   python gui.py
   ```

## ✨ Features

- **File Sharing**: Allows multiple peers to share files seamlessly.
- **Piece-Based File Transfer**: Downloads are divided into pieces, allowing faster and more resilient transfers.
- **Tracker Coordination**: The tracker coordinates file availability and peer connections.
- **User-Friendly GUI**: Provides an intuitive interface for sharing and downloading files.
- **Download Management**: Monitors and manages ongoing transfers.

## 📦 Dependencies

### Tracker Dependencies

- **Express.js**: Web server framework.
- **MongoDB & Mongoose**: Database and ORM for storing file and peer data.
- **Multer**: For handling file uploads.
- **CORS**: Enables cross-origin requests.
- **Bencode**: For parsing torrent-like file metadata.

### Node Dependencies

Listed in `requirements.txt`, including:

- **Python GUI libraries**: For creating the graphical user interface.
- **Network communication libraries**: To enable peer-to-peer communication.

## 📂 Project Structure

```plaintext
├── node/               # Peer node implementation
│   ├── node_data/      # Storage for downloaded files and file pieces
│   ├── gui.py          # User interface for file sharing and downloading
│   └── node.py         # Core node functionality
└── tracker/            # Central tracker server
    ├── src/            # Source code
    │   ├── config/     # Configuration files
    │   ├── controller/ # Handles requests and responses
    │   ├── model/      # Database models
    │   └── route/      # API route definitions
    └── app.js          # Server entry point
```

## 📝 Usage

1. **Start the Tracker Server**:

   - Run the tracker server to manage peer connections and file metadata.

2. **Launch the Node Application**:
   - Open the node GUI to share or download files.
3. **Use the GUI to**:
   - **Share Files**: Select files to make available to other peers.
   - **Download Files**: Choose files to download from other peers.
   - **Monitor Transfers**: Track progress and manage ongoing downloads.
