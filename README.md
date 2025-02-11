# Moly Server

A local HTTP server that powers the Moly app by providing capabilities for searching, downloading, and running local Large Language Models (LLMs). This server integrates with WasmEdge for model execution and provides an OpenAI-compatible API interface.

## Features

- Search and discover LLM models
- Download and manage model files
- Automatic mirror selection based on region
- Run local LLMs using WasmEdge runtime
- OpenAI-compatible API interface

## Building and Running

> ⚠️ **Note**: TODO

## Development

To run the server locally:

```bash
cargo run -p moly-server
```

The server will start on the configured port (default: 8765) and log its address.

## Configuration

The server can be configured using the following environment variables:

- `MOLY_SERVER_PORT`: Port number for the HTTP server (default: 8765)
- `MODEL_CARDS_REPO`: Custom repository URL for model cards
- `MOLY_API_SERVER_ADDR`: Custom address for the API server (default: localhost:0)

## API Endpoints

### File Management

- `GET /files` - List all downloaded files
- `DELETE /files/{id}` - Delete a specific file

### Download Management

- `GET /downloads` - List all current downloads
- `POST /downloads` - Start a new download
- `GET /downloads/{id}/progress` - Get download progress
- `POST /downloads/{id}` - Pause a download
- `DELETE /downloads/{id}` - Cancel a download

### Model Management

- `POST /models/load` - Load a model
- `POST /models/eject` - Eject the currently loaded model
- `GET /models/featured` - Get featured models
- `GET /models/search` - Search for models
- `POST /models/v1/chat/completions` - Chat completions endpoint (OpenAI-compatible)
