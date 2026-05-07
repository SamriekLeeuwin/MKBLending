# SME Lending Platform

A cloud-native fintech platform for processing small business loan applications.

## What It Does

Business owners submit loan applications through a web form. The platform automatically:

- Validates and stores the application
- Calculates a credit risk score based on financial data
- Makes an approve/reject decision using business rules
- Sends status notifications

## Architecture

Built on AWS with serverless services:

- Frontend: React + TypeScript
- API: API Gateway + Lambda functions
- Events: EventBridge for async communication between services
- Database: DynamoDB for application and scoring data
- Infrastructure: AWS CDK (TypeScript) for managing all resources

## Services

| Service | What It Does | How It's Triggered |
| --- | --- | --- |
| Submit Application | Validates input, stores in DB, publishes event | API call from frontend |
| Credit Scoring | Calculates risk score (0-100) | Event from submit service |
| Decision Engine | Approves or rejects based on score | Event from scoring service |
| Notification | Logs events, sends alerts | All events |
| Dashboard API | Returns application data for UI | API call from frontend |

## Tech Stack

- AWS Lambda (Node.js 20)
- Amazon EventBridge
- Amazon DynamoDB
- API Gateway
- React + Vite
- AWS CDK

## Project Structure

```text
sme-lending-platform/
├── cdk/              # Infrastructure (AWS resources)
├── src/              # Lambda functions (business logic)
├── frontend/         # React web app
└── shared/           # Common types
```

## Status

In development. Currently building core infrastructure and services.
