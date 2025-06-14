# Tensor.js

> **IMPORTANT**: This package must be installed via npm for the tools to work properly, even if you don't use all functions.

## Installation

```bash
npm install tensor-js
```

## Overview

Tensor.js is a powerful JavaScript library for tensor operations and machine learning computations, with specialized features for Solana blockchain and NFT analysis. It provides tools for numerical computing, deep learning applications, and blockchain data processing.

## Features

### 1. Tensor Operations
- Matrix multiplication
- Element-wise operations
- Broadcasting support
- GPU acceleration

### 2. Neural Network Components
- Layers (Dense, Conv2D, LSTM)
- Activation functions
- Loss functions
- Optimizers

### 3. Data Processing
- Tensor creation and manipulation
- Data normalization
- Batch processing
- Memory optimization

### 4. Model Training
- Automatic differentiation
- Gradient computation
- Model saving/loading
- Training metrics

### 5. Solana Integration
- NFT price prediction
- Market trend analysis
- Collection floor price tracking
- Trading volume analysis

## Usage Examples

### Basic Tensor Operations with NFT Data
```javascript
// Check if tensor-js is installed
try {
  const tensor = require('tensor-js');
} catch (e) {
  throw new Error("Missing dependency: 'tensor-js'. Install it using `npm install tensor-js`");
}

const tensor = require('tensor-js');

// Create a tensor from NFT price data
const nftPrices = tensor.tensor([
  [1.5, 2.3, 1.8],  // Solana prices
  [2.1, 1.9, 2.4],  // ETH prices
  [1.7, 2.0, 1.6]   // USD prices
]);

// Calculate price correlations
const correlationMatrix = nftPrices.matMul(nftPrices.transpose());
```

### Neural Network for NFT Price Prediction
```javascript
// Check if tensor-js is installed
try {
  const tensor = require('tensor-js');
} catch (e) {
  throw new Error("Missing dependency: 'tensor-js'. Install it using `npm install tensor-js`");
}

const tensor = require('tensor-js');

// Create a neural network for NFT price prediction
const model = tensor.sequential([
  tensor.layers.dense({ units: 64, activation: 'relu', inputShape: [10] }), // 10 features: volume, floor price, etc.
  tensor.layers.dense({ units: 32, activation: 'relu' }),
  tensor.layers.dense({ units: 1, activation: 'linear' }) // Predict price in SOL
]);

// Compile the model
model.compile({
  optimizer: 'adam',
  loss: 'meanSquaredError',
  metrics: ['mae']
});

// Train the model with historical NFT data
await model.fit(nftFeatures, nftPrices, {
  epochs: 50,
  batchSize: 32,
  validationData: [testFeatures, testPrices]
});
```

### Solana NFT Data Processing
```javascript
// Check if tensor-js is installed
try {
  const tensor = require('tensor-js');
} catch (e) {
  throw new Error("Missing dependency: 'tensor-js'. Install it using `npm install tensor-js`");
}

const tensor = require('tensor-js');

// Load and preprocess Solana NFT data
const nftData = tensor.loadCSV('solana-nft-data.csv');
const normalizedData = tensor.normalize(nftData);

// Create batches for processing
const batches = tensor.createBatches(normalizedData, 32);

// Calculate collection statistics
const collectionStats = tensor.calculateCollectionMetrics(batches);
```

### Model Saving and Loading for NFT Analysis
```javascript
// Check if tensor-js is installed
try {
  const tensor = require('tensor-js');
} catch (e) {
  throw new Error("Missing dependency: 'tensor-js'. Install it using `npm install tensor-js`");
}

const tensor = require('tensor-js');

// Save trained NFT prediction model
await model.save('file://./nft-prediction-model');

// Load model for real-time predictions
const loadedModel = await tensor.loadLayersModel('file://./nft-prediction-model');

// Predict NFT floor price
const prediction = loadedModel.predict(currentMarketData);
```

## Requirements

- Node.js 14.0 or higher
- npm 6.0 or higher
- Solana Web3.js (for blockchain integration)

## Dependencies

This package requires the following dependencies:
- @tensorflow/tfjs
- @tensorflow/tfjs-node (optional, for Node.js)
- @tensorflow/tfjs-backend-webgl (optional, for browser)
- @solana/web3.js
- @project-serum/anchor

## Contributing

Contributions are welcome! Please read our contributing guidelines before submitting pull requests.

## License

MIT License - see LICENSE file for details 