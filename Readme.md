# FastAPI Learning Labs

A comprehensive collection of FastAPI labs designed to teach modern Python web API development from fundamentals to advanced concepts.

## 📋 Table of Contents

- [What is FastAPI?](#what-is-fastapi)
- [FastAPI vs Flask](#fastapi-vs-flask)
- [API Documentation](#api-documentation)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Labs Overview](#labs-overview)
- [Running the Labs](#running-the-labs)
- [Next Steps](#next-steps)

## What is FastAPI?

FastAPI is a modern, fast (high-performance), web framework for building APIs with Python 3.7+ based on standard Python type hints. It's designed to be easy to use, fast to code, and production-ready.

### Key Features:
- **Fast**: Very high performance, on par with NodeJS and Go
- **Fast to code**: Increase development speed by 200-300%
- **Fewer bugs**: Reduce human-induced errors by 40%
- **Intuitive**: Great editor support with auto-completion
- **Easy**: Designed to be easy to use and learn
- **Short**: Minimize code duplication
- **Robust**: Get production-ready code with automatic interactive documentation
- **Standards-based**: Based on and fully compatible with OpenAPI and JSON Schema

## FastAPI vs Flask

| Feature | FastAPI | Flask |
|---------|---------|--------|
| **Performance** | Very High (async support) | Moderate |
| **Type Hints** | Built-in support | Manual implementation |
| **Data Validation** | Automatic with Pydantic | Manual with extensions |
| **Documentation** | Auto-generated (Swagger/ReDoc) | Manual setup required |
| **Async Support** | Native async/await | Limited (with extensions) |
| **Learning Curve** | Moderate | Easy |
| **API Standards** | OpenAPI 3.0 compliant | Manual implementation |
| **Request/Response** | Automatic serialization | Manual handling |

### When to Choose FastAPI:
- Building modern APIs with automatic documentation
- Need high performance and async support
- Want built-in data validation and serialization
- Prefer type safety and IDE support
- Building microservices or data-heavy applications
### What is uvicorn

Uvicorn is a lightning-fast ASGI (Asynchronous Server Gateway Interface) server designed to run asynchronous Python web applications. It’s the preferred server for frameworks like FastAPI that are built to handle asynchronous code efficiently.

#### Why Uvicorn with FastAPI?
FastAPI leverages Python’s async/await syntax to maximize concurrency and speed, especially when dealing with I/O-bound operations like database queries or external API calls. To run this async code properly, you need an ASGI server like Uvicorn, which can handle asynchronous event loops and concurrency seamlessly.

#### How is this different from Flask and Node.js?
Flask is synchronous and built on WSGI (Web Server Gateway Interface). It doesn’t require an ASGI server because it handles requests one at a time in a blocking manner. Running async code in Flask isn’t native or efficient.

Node.js is built on an asynchronous event-driven architecture by default, so it doesn’t need an extra server like Uvicorn. It’s designed to handle async operations natively.



## API Documentation

One of FastAPI's most powerful features is automatic API documentation generation:

### Interactive Documentation
Once your application is running, you can access:

- **Swagger UI**: `http://localhost:8000/docs`
  - Interactive API documentation
  - Test endpoints directly in the browser
  - View request/response schemas
  - Generate code examples

- **ReDoc**: `http://localhost:8000/redoc`
  - Alternative documentation interface
  - Clean, professional appearance
  - Better for API reference documentation

### OpenAPI Schema
- **JSON Schema**: `http://localhost:8000/openapi.json`
  - Raw OpenAPI 3.0 specification
  - Use for generating client SDKs
  - Integration with API tools

### Documentation Features:
- Automatic schema generation from type hints
- Parameter descriptions and examples
- Response model documentation
- Error response documentation
- Authentication requirements
- Endpoint grouping and tagging


## Installation

### Prerequisites
- Python 3.7 or higher
- pip (Python package installer)

### Setup Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/madiha-ahmed-chowdhury/FastAPI.git
   cd FastAPI
   ```

2. **Navigate to any lab directory (e.g., lab01)**
   ```bash
   cd lab01
   ```

3. **Create a virtual environment**
   ```bash
   python -m venv venv
   ```

4. **Activate the virtual environment**
   
   **Windows:**
   ```bash
   venv\Scripts\activate.bat
   ```
   
   **macOS/Linux:**
   ```bash
   source venv/bin/activate
   ```

5. **Install required packages**
   ```bash
   pip install fastapi
   pip install uvicorn
   ```

6. **Run the application**
   ```bash
   uvicorn app.main:app --reload
   ```

The `--reload` flag enables auto-reload during development, so the server restarts automatically when you make changes to your code.

## Project Structure

```
fastapi-labs/
├── README.md
├── lab01/
│   ├── app/
│   │   └── main.py
│   └── venv/
├── lab02/
│   ├── app/
│   │   └── main.py
│   └── venv/
├── lab03/
│   └── ...
├── ...
└── lab12/
    └── ...
```

## Labs Overview

| Lab | Topic | Key Concepts |
|-----|-------|--------------|
| **Lab 01** | FastAPI Fundamentals | Path parameters, Query parameters, Validation |


## Running the Labs
### FastAPI Development Setup Guide

#### Windows Setup for VS Code Terminal

**Important**: For Windows users working with multiline commands in VS Code, you'll need to configure Git Bash as your default terminal.

##### VS Code Terminal Configuration

Add this to your VS Code `settings.json`:

```json
{
  "terminal.integrated.profiles.windows": {
    "Git Bash": {
      "path": "C:\\Program Files\\Git\\bin\\bash.exe"
    }
  },
  "terminal.integrated.defaultProfile.windows": "Git Bash"
}
```

**Prerequisites**: 
- Install Git for Windows (includes Git Bash)
- This enables proper handling of Unix-style commands and multiline scripts

### Development Commands

#### Development Mode
```bash
# Navigate to any lab directory
cd lab01

# Activate virtual environment
venv\Scripts\activate.bat  # Windows Command Prompt
# or
source venv/bin/activate   # Git Bash/macOS/Linux

# Run with auto-reload
uvicorn app.main:app --reload
```

### Production Mode
```bash
# Run without reload for better performance
uvicorn app.main:app --host 0.0.0.0 --port 8000
```

#### Custom Configuration
```bash
# Run on different host/port
uvicorn app.main:app --host 127.0.0.1 --port 3000 --reload

# Run with specific log level
uvicorn app.main:app --log-level debug
```
