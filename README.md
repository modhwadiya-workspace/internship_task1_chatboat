# Workflow-Based Chatbot Platform

This project is a **rule-based chatbot platform** where chatbot conversations are created using **visual workflows** instead of AI or NLP.

Each chatbot is defined as a **directed graph**.  
Admins design the conversation flow visually, and users interact with the chatbot by selecting predefined options.

---

## Purpose

The purpose of this project is to demonstrate how a chatbot system can be built using **deterministic workflow logic** rather than artificial intelligence.

The system focuses on:
- Predictable chatbot behavior
- Full control over conversation flow
- Visual chatbot design
- Clean backend-driven architecture

---

## How the Chatbot Works

- Every chatbot is represented as a directed graph
- Each node contains a chatbot reply
- Edges define how the conversation moves forward
- One node is marked as the start node
- User interaction moves the chatbot from one node to another

The chatbot response is determined by traversing the graph based on the user’s selection.

---

## Main Concepts

### Chatbot
A container that holds a single workflow.

### Node
- Represents one chatbot response
- Contains:
  - Bot reply text
  - User option text
  - UI position for visual editor
- One node is marked as the start node

### Edge
- Connects two nodes
- Defines the direction of conversation flow

---

## Technology Stack

### Backend
- FastAPI
- PostgreSQL
- SQLAlchemy
- GraphQL using Strawberry
- python-dotenv

### Frontend
- Next.js with App Router
- TypeScript
- Apollo Client v4
- React Flow
- Tailwind CSS

---

## User Roles

### Admin
- Create and delete chatbots
- Design chatbot workflows visually
- Create, move, connect, and delete nodes
- Set the start node
- Save workflow layout

### User
- View available chatbots
- Interact with chatbot using buttons
- Stateless conversation

---

## Database Schema

### chatbot
Stores chatbot metadata.

| Field | Description |
|------|------------|
| id | Unique chatbot ID |
| name | Chatbot name |

### workflow_node
Stores chatbot nodes.

| Field | Description |
|------|------------|
| id | Node ID |
| chatbot_id | Parent chatbot |
| user_message | Button text |
| bot_reply | Bot response |
| is_start | Start node flag |
| position_x | UI X coordinate |
| position_y | UI Y coordinate |

### workflow_edge
Stores connections between nodes.

| Field | Description |
|------|------------|
| id | Edge ID |
| chatbot_id | Parent chatbot |
| from_node_id | Source node |
| to_node_id | Destination node |

---

## Features

### Admin Features
- Chatbot creation and deletion
- Visual workflow editor
- Node and edge management
- Drag-and-drop node positioning
- Start node selection
- Persistent storage

### User Features
- Chatbot listing
- Button-based chat interface
- Deterministic conversation flow
- Automatic fallback to start node

---

## Running the Project

### Backend Setup

```bash
cd backend
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload  

```

### GraphQL endpoint:

```bash
http://localhost:8000/graphql

```

### Frontend Setup

```bash
cd frontend
npm install
npm run dev

```

### Application URL:
http://localhost:3000




