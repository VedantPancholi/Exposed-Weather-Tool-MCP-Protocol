# MCP (Model Context Protocol) Project

## 🚀 What is MCP?

**MCP (Model Context Protocol)** is a powerful, flexible protocol for building **tool-augmented AI systems**. It enables you to expose Python functions as tools that can be accessed over different transports like **SSE**, **stdio**, or **HTTP**, allowing seamless interaction between servers, clients, and large language models (LLMs).

---

## 🧠 Project Highlights

- 🔧 **Built an MCP server from scratch** with FastMCP to serve real-time weather tools.
- 📡 **Integrated with clients** using both **SSE** and **stdio**.
- 🤖 **Connected to Google Gemini via LangChain**, enabling conversational AI that uses tools.
- 🐳 **Dockerized environment** for easy deployment and portability.

---

## 📁 Project Structure

### Root
| File | Description |
|------|-------------|
| `main.py` | Entry script printing a greeting. |
| `README.md` | This documentation. |
| `pyproject.toml` | Project dependencies. |
| `uv.lock` | Lock file for deterministic installs. |

### `mcpserver/`
| File | Description |
|------|-------------|
| `server.py` | Main MCP server with weather tools (`get_alerts`, `get_forecast`). |
| `client-sse.py` | Client using SSE to list and invoke server tools. |
| `client-stdio.py` | Client using stdio to interact with server tools. |
| `Dockerfile` | Docker setup to run the MCP server in a container. |
| `requirements.txt` | Python package dependencies. |

### `server/`
| File | Description |
|------|-------------|
| `weather.py` | Alternative MCP server with weather tools and a custom resource. |
| `client.py` | LangChain + Google Gemini integration with conversational tool usage. |
| `weather.json` | Configuration file for launching the weather server. |

---
# 🖼️ Screenshot of Running Weather get_alert() Function 
![Screenshot 2025-06-19 224919](https://github.com/user-attachments/assets/fd7b570b-079d-46f1-ac00-420d63e98ee7)
![image](https://github.com/user-attachments/assets/becc4dd6-435a-4ba4-b351-a5d2121aa2b5)


## 🔍 How It Works

### 1. MCP Server
- Exposes weather-related tools using `@mcp.tool()` decorators.
- Can run on transports like SSE and stdio.

### 2. Client Integration
- **SSE Client**: Connects over SSE to discover and invoke tools.
- **Stdio Client**: Uses stdin/stdout for command-line interaction.

### 3. LLM Integration
- **LangChain** connects Gemini to the MCP server.
- Enables LLMs to reason and invoke tools dynamically during conversation.

### 4. Dockerized Deployment
- All code and dependencies are containerized.
- Runs MCP server easily on any platform via Docker.

---

## 🧪 How to Run

### Run Locally (Python)
```bash
pip install -r mcpserver/requirements.txt
uv run mcpserver/server.py 


