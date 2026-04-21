# AZZOTTO Stream AI TICKETING INTELLIGENCE PLATFORM

_The World's First Predictive Pricing Engine with Multi-Source RAG_

## Project Structure

```
azzotto-ticketing-ai/
├── apps/
│   ├── api-gateway/           # Express/Fastify gateway
│   ├── price-engine/          # ML pricing microservice
│   ├── demand-predictor/      # LSTM demand forecasting
│   ├── promotion-optimizer/   # RL promotion engine
│   ├── rag-pipeline/          # RAG workflow service
│   ├── event-ingestor/        # EVENT 2026 + Sports + 3rd party
│   ├── notification-service/  # Real-time messaging
│   └── monitoring/            # Prometheus + Grafana
├── libs/
│   ├── shared-types/          # TypeScript interfaces
│   ├── ai-models/             # Trained ML models
│   ├── vector-store/          # Pinecone/Qdrant client
│   └── message-bus/           # Kafka/Redis client
├── infrastructure/
│   ├── k8s/                   # Kubernetes manifests
│   ├── docker/                # Dockerfiles
│   └── terraform/             # Cloud infra
├── dashboard/
│   ├── prometheus/
│   ├── grafana/
│   └── alertmanager/
└── package.json

```

## Timeline

- 📦 PHASE 1: RAG Pipeline + EVENT 2026 Scheduler (Week 1-3)



## package.json

```
{
  "name": "azzotto-ticketing-ai",
  "version": "1.0.0",
  "private": true,
  "workspaces": [
    "apps/*",
    "libs/*"
  ],
  "scripts": {
    "dev": "concurrently \"npm run dev:gateway\" \"npm run dev:price\" \"npm run dev:demand\" \"npm run dev:promotion\" \"npm run dev:rag\" \"npm run dev:ingestor\" \"npm run dev:notification\"",
    "dev:gateway": "npm run dev -w @azzotto/api-gateway",
    "dev:price": "npm run dev -w @azzotto/price-engine",
    "dev:demand": "npm run dev -w @azzotto/demand-predictor",
    "dev:promotion": "npm run dev -w @azzotto/promotion-optimizer",
    "dev:rag": "npm run dev -w @azzotto/rag-pipeline",
    "dev:ingestor": "npm run dev -w @azzotto/event-ingestor",
    "dev:notification": "npm run dev -w @azzotto/notification-service",
    "build": "tsc --build tsconfig.json",
    "build:all": "npm run build --workspaces --if-present",
    "test": "jest --coverage",
    "test:watch": "jest --watch",
    "lint": "eslint . --ext .ts",
    "format": "prettier --write \"**/*.ts\"",
    "docker:build": "docker-compose -f infrastructure/docker/docker-compose.yml build",
    "docker:up": "docker-compose -f infrastructure/docker/docker-compose.yml up -d",
    "docker:down": "docker-compose -f infrastructure/docker/docker-compose.yml down",
    "k8s:deploy": "bash infrastructure/k8s/deploy.sh",
    "k8s:destroy": "bash infrastructure/k8s/destroy.sh",
    "model:train": "npm run train -w @azzotto/ml-models",
    "model:serve": "npm run serve -w @azzotto/ml-models",
    "benchmark": "npm run bench -w @azzotto/benchmark"
  },
  "devDependencies": {
    "@types/jest": "^29.5.5",
    "@types/node": "^20.8.0",
    "@typescript-eslint/eslint-plugin": "^6.7.0",
    "@typescript-eslint/parser": "^6.7.0",
    "concurrently": "^8.2.1",
    "eslint": "^8.50.0",
    "jest": "^29.7.0",
    "prettier": "^3.0.3",
    "ts-jest": "^29.1.1",
    "ts-node": "^10.9.1",
    "typescript": "^5.2.2"
  },
  "engines": {
    "node": ">=20.0.0",
    "npm": ">=10.0.0"
  }
}
```
