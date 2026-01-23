.NET 8 Microservices E‑Commerce Project
📌 Overview
This repository demonstrates building cloud‑native microservices with ASP.NET Core (.NET 8) using modern architectural patterns and best practices. The solution implements an e‑commerce system with independent services for Catalog, Basket, Discount, and Ordering, all orchestrated through a YARP API Gateway and containerized with Docker Compose.

🏗️ Architecture Highlights
Microservices: Catalog, Basket, Discount, Ordering, API Gateway, WebUI

Patterns & Practices:

Domain‑Driven Design (DDD)

CQRS with MediatR

Vertical Slice Architecture

Clean Architecture & SOLID principles

Communication:

gRPC for synchronous inter‑service calls

RabbitMQ + MassTransit for asynchronous messaging

Data Stores:

PostgreSQL (Marten DocumentDB)

Redis (Distributed Cache)

SQLite (Discount service)

SqlServer (Ordering service)

📦 Microservices Breakdown
Catalog Service
ASP.NET Core Minimal APIs (C# 12)

Vertical Slice + CQRS with MediatR

Marten (PostgreSQL DocumentDB)

Carter for endpoint definitions

Logging, exception handling, health checks

Basket Service
ASP.NET Web API (REST CRUD)

Redis cache with Proxy/Decorator/Cache‑aside patterns

Consumes Discount gRPC service

Publishes BasketCheckout events via RabbitMQ/MassTransit

Discount Service
ASP.NET gRPC server

Protobuf contracts for inter‑service communication

EF Core with SQLite + migrations

Containerized database

Ordering Service
DDD + Clean Architecture

CQRS with MediatR, FluentValidation, Mapster

Domain & integration events

EF Core with SqlServer (code‑first + migrations)

Consumes BasketCheckout events via RabbitMQ/MassTransit

YARP API Gateway
Reverse proxy with routing, clusters, transforms

Rate limiting (FixedWindowLimiter)

Unified entry point for WebUI and external clients

WebUI (ShoppingApp)
ASP.NET Core Razor + Bootstrap 4

Consumes APIs via Refit + HttpClientFactory

Razor tools: ViewComponents, TagHelpers, validations

⚙️ Deployment
Docker Compose orchestrates all microservices, databases, cache, and message broker.

Environment variables override configuration for cloud‑native flexibility.

Health checks ensure readiness/liveness for container orchestration.

🎯 Learning Goals
Build production‑style microservices with .NET 8

Apply DDD, CQRS, Vertical Slice, Clean Architecture

Implement sync (gRPC) and async (RabbitMQ) communication

Containerize and orchestrate services with Docker Compose

Write quality, maintainable, loosely‑coupled code following SOLID principles
