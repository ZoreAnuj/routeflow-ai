# RouteFlow AI

Autonomous logistics optimization platform built with generative AI agents. The system models multi-city freight networks and uses AI-driven route planning to minimize cost, transit time, and carbon footprint across complex supply chains.

## Architecture

- **Agent Layer** (`src/agent.py`) - Orchestrates route decisions using LLM-based reasoning with tool calls for geocoding, distance computation, and constraint satisfaction
- **Service Layer** (`src/services.py`) - Geospatial utilities (Geopy), Folium map rendering, and route scoring with weighted multi-objective optimization
- **Data Models** (`src/models.py`) - Pydantic schemas for shipments, carriers, route segments, and optimization constraints

## Stack

Python 3.10+ / OpenAI / Streamlit / Geopy / Folium / Pydantic

## Quick Start

```bash
pip install -r requirements.txt
cp .env.example .env  # add OPENAI_API_KEY
streamlit run main.py
```

## How It Works

1. User defines shipment parameters (origin, destination, weight, urgency)
2. Agent decomposes the problem into sub-routes and evaluates carrier options
3. Multi-objective scorer ranks routes by cost, time, and emissions
4. Interactive Folium map visualizes the optimized route with waypoints
