# ZIP

## AZZOTTO Stream  AI TICKETING INTELLIGENCE PLATFORM

_The  First Predictive Pricing Engine with Multi-Source RAG_


**ZIP** is a fully functional, production-ready AI ticketing intelligence system deployed as a standalone microservice. The system includes a dynamic pricing engine powered by XGBoost and LSTM ensemble models, a hybrid RAG pipeline for contextual price retrieval, and a reinforcement learning promotion optimizer that learns optimal discount strategies. All core AI components are operational and communicating over HTTP/WebSocket, with real-time price updates, demand forecasting, and personalized promotions working end-to-end.

The infrastructure is containerized with Docker Compose and deployed to Vercel as a separate project from `azzotto-movies`. **ZIP** runs in development and on its own domain in production, with full CORS configuration allowing seamless cross-service communication. The mock server phase has been validated, and the service is ready to accept API calls for dynamic pricing (`/api/v1/pricing/current`), promotions (`/api/v1/promotions/optimize`), demand forecasts, and event schedules.

The integration layer with `azzotto-movies` is complete. The client library (`ticketing-api.client.ts`) reads environment variables to switch between localhost and production URLs, ensuring zero-code-change deployment. The two CyclingAds and TicketService components have been enhanced to fetch AI-powered prices and promotions in parallel while gracefully falling back to static data when ZIP is unavailable.

**ZIP** is in production - https://www.azzottomovies.com/globalmovie/1311031 . The system successfully tags users, tracks revenue, enforces purchase controls, and calculates earnings across multiple models (markup, commission, transaction fee). Database schemas, API endpoints, and admin dashboards are implemented. **ZIP** represents a complete, deployable AI ticketing solution that supersedes existing market offerings through intelligent pricing, real-time adaptability, and full operational control.

## Features

https://github.com/kukuu/AZZOTTO-STREAM-AI-TICKETING-INTELLIGENCE-PLATFORM/blob/main/features.md


## STATUS AI TICKETING PLATFORM 

https://github.com/kukuu/AZZOTTO-STREAM-AI-TICKETING-INTELLIGENCE-PLATFORM/blob/main/status.md


### 📋 DETAILED BREAKDOWN PER PHASE


https://github.com/kukuu/AZZOTTO-STREAM-AI-TICKETING-INTELLIGENCE-PLATFORM/blob/main/tasks-breakdown.md


### 🎯 DELIVERABLE STATUS KEY

https://github.com/kukuu/AZZOTTO-STREAM-AI-TICKETING-INTELLIGENCE-PLATFORM/blob/main/deliverables.md



## Technologies

https://github.com/kukuu/AZZOTTO-STREAM-AI-TICKETING-INTELLIGENCE-PLATFORM/blob/main/technologies.md


### 🚀 DEPLOYMENT FOOTPRINT

#### Minimum Production Requirements:
```
CPU: 16 cores (distributed across 8 services)
RAM: 32 GB
GPU: 1x NVIDIA T4 (or better) for TensorFlow.js
Storage: 100 GB (models + vectors + logs)
Network: 1 Gbps
```

#### Auto-scaling Configuration:
```
API Gateway:     3-20 replicas (based on RPS)
Price Engine:    3-15 replicas (CPU > 70%)
Demand Predictor: 2-10 replicas (memory > 80%)
RAG Pipeline:    2-8 replicas (queue depth)
Others:          2-5 replicas each
```


### ✅ TECHNOLOGY VERIFICATION

All technologies have been verified for:
- ✅ **Production readiness** (stable versions)
- ✅ **TypeScript compatibility** (types available)
- ✅ **Docker support** (official images)
- ✅ **Kubernetes compatibility** (helm charts available)
- ✅ **Monitoring support** (Prometheus exporters)
- ✅ **Commercial support** (enterprise-grade)

## Vault 

- https://github.com/kukuu/azzotto-ticketing-ai (PRIVATE)

**The stack represents state-of-the-art in AI-powered ticketing systems, combining real-time ML inference, RAG-based contextual intelligence, and cloud-native scalability.**


