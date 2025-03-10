# Solana-MCP-Trading-Server
An innovative MCP server that shows trending tokens and integrates Grok, xAI image understanding and vision (interpreted as a vision-capable AI), and Claude's computer use capabilities.

# Solana Trading MCP Server

A comprehensive server for launching Solana tokens with AI-powered features, including token concept generation, image creation, and DNA sequence generation.

## Features

- **AI-Powered Token Generation**: Uses xAI/Grok to generate innovative token concepts, names, and descriptions
- **Image Generation**: Utilizes FAL.ai's fast-lightning-sdxl model for high-quality token artwork
- **DNA Sequence Generation**: Integrates NVIDIA's DNA Generator API for unique token identifiers
- **Solana Token Launcher**: Creates and deploys tokens on the Solana blockchain
- **Real-time WebSocket Support**: Provides immediate feedback during image generation
- **Multiple Testing Options**: Supports testing on devnet and real token launches on mainnet

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/Solana-Trading-MCP-Server.git
cd Solana-Trading-MCP-Server

# Install dependencies
npm install

# Build the project
npm run build
```

## Environment Setup

Create a `.env` file in the root directory with the following variables:

```
FAL_KEY=your_fal_ai_key
FAL_SECRET=your_fal_ai_secret
XAI_API_KEY=your_xai_api_key
HELIUS_RPC_URL=your_helius_rpc_url
OPENAI_API_KEY=your_openai_api_key
NVIDIA_API_KEY=your_nvidia_api_key
PRIVATE_KEY=your_solana_private_key
```

## Usage

### Running the Server

```bash
npm run start
```

### Running the Client

```bash
npm run client
```

### AI-Powered Token Creation

The AI token creator combines xAI/Grok, FAL.ai, and Solana to create tokens with AI-generated concepts:

```bash
# Run with a specific theme
node dist/test-ai-token.js "space exploration"

# Run in test mode on devnet
TEST_MODE=true NETWORK=devnet node dist/test-ai-token.js

# Run for real token launch on mainnet
TEST_MODE=false NETWORK=mainnet-beta node dist/test-ai-token.js
```

### Real-time Image Generation Example

Experience real-time updates during image generation with WebSockets:

```bash
node dist/realtime-image-example.js
```

## API Methods

The server supports the following JSON-RPC methods:

### Launch Token

```json
{
  "jsonrpc": "2.0",
  "id": 1,
  "method": "callTool",
  "params": {
    "name": "launch_token",
    "arguments": {
      "deployer_private_key": "your_private_key",
      "name": "MyToken",
      "symbol": "MTK",
      "prompt": "A futuristic token logo with blue and purple gradients"
    }
  }
}
```

### Generate Image

```json
{
  "jsonrpc": "2.0",
  "id": 2,
  "method": "callTool",
  "params": {
    "name": "generate_image",
    "arguments": {
      "prompt": "A serene beach at sunset with lightning in the background"
    }
  }
}
```

### Chat with Grok

```json
{
  "jsonrpc": "2.0",
  "id": 3,
  "method": "callTool",
  "params": {
    "name": "chat_with_grok",
    "arguments": {
      "messages": [
        { "role": "user", "content": "What is the meaning of life?" }
      ]
    }
  }
}
```

### Generate DNA Sequence

```json
{
  "jsonrpc": "2.0",
  "id": 4,
  "method": "callTool",
  "params": {
    "name": "generate_dna",
    "arguments": {
      "sequence": "ATGCATGCATGC",
      "temperature": 0.7,
      "top_k": 30,
      "max_length": 50
    }
  }
}
```

### Generate Token Details

```json
{
  "jsonrpc": "2.0",
  "id": 5,
  "method": "callTool",
  "params": {
    "name": "generate_token_details",
    "arguments": {
      "theme": "space exploration"
    }
  }
}
```

## Testing

The project supports multiple testing options:

1. **Simple Mock Test**: Simulates the token launch process without connecting to the Solana blockchain
2. **Test Mode on Devnet**: Uses a randomly generated keypair to test on Solana devnet
3. **Real Token Launch**: For launching actual tokens on devnet or mainnet

See `TESTING.md` for more details on testing options.

## DNA Visualization

The DNA Generator visualizes sequences with colored nucleotides:
- A = Green
- T = Blue
- G = Yellow
- C = Red

It also provides probability distributions for each generated nucleotide.

## License
