<div align="center">
  <h1>🪙 KUBERA</h1>
  <p><strong>AI-Powered Stock Analysis Chatbot for Indian Markets (NSE/BSE)</strong></p>

  <p>
    <img src="https://img.shields.io/badge/python-3.11+-blue.svg" alt="Python">
    <img src="https://img.shields.io/badge/FastAPI-0.109.0-009688.svg" alt="FastAPI">
    <img src="https://img.shields.io/badge/React-18-61DAFB.svg?logo=react" alt="React">
    <img src="https://img.shields.io/badge/TypeScript-5-3178C6.svg?logo=typescript" alt="TypeScript">
    <img src="https://img.shields.io/badge/PostgreSQL-Supabase-3ECF8E.svg?logo=supabase" alt="Supabase">
    <img src="https://img.shields.io/badge/Docker-ready-2496ED.svg?logo=docker" alt="Docker">
  </p>

  <p>
    <a href="https://kubera-frontend-olive.vercel.app/"><strong>🌐 Live App</strong></a> ·
    <a href="https://kubera007.duckdns.org/docs"><strong>📖 API Docs</strong></a> ·
    <a href="https://hub.docker.com/r/tejascm/kubera-backend"><strong>🐳 Docker Hub</strong></a>
  </p>
</div>

---

## 📁 Repository Structure

```
kubera/                          ← Monorepo root
├── kubera-frontend/             ← React + TypeScript frontend
│   ├── src/
│   │   ├── components/          ← Reusable UI components (shadcn/ui)
│   │   ├── pages/               ← Route-level page components
│   │   ├── hooks/               ← Custom React hooks
│   │   ├── contexts/            ← React context providers
│   │   └── lib/                 ← Utilities & helpers
│   ├── public/
│   ├── index.html
│   ├── vite.config.ts
│   └── package.json
│
├── Kubera-Backend/              ← FastAPI Python backend
│   ├── app/
│   │   ├── api/                 ← REST API route handlers
│   │   ├── core/                ← Config, database, security
│   │   ├── models/              ← SQLAlchemy / DB models
│   │   ├── schemas/             ← Pydantic request/response schemas
│   │   ├── services/            ← Business logic layer
│   │   ├── background/          ← APScheduler background jobs
│   │   ├── mcp/                 ← MCP tool integrations
│   │   ├── websocket/           ← WebSocket handlers
│   │   ├── utils/               ← Shared utility functions
│   │   └── exceptions/          ← Custom exception handlers
│   ├── mcp_servers/             ← Standalone MCP server definitions
│   ├── scripts/                 ← DB init, migration, utility scripts
│   ├── main.py                  ← FastAPI application entry point
│   ├── requirements.txt
│   ├── Dockerfile
│   ├── docker-compose.yml
│   └── .env.example
│
├── .gitignore                   ← Root gitignore (Python + Node)
└── README.md                    ← This file
```

---

## ✨ Features

| Category | Details |
|---|---|
| 🤖 **AI Chat** | Real-time streaming conversations via OpenRouter (Llama 3.3, Claude, GPT-4) |
| 📊 **Stock Analysis** | Comprehensive NSE/BSE analysis with 45+ MCP tools |
| 💼 **Portfolio** | Track investments with live price updates |
| 📈 **Technical Analysis** | Charts & graphs powered by Plotly |
| 📰 **News & Sentiment** | Real-time market news with AI sentiment analysis |
| 🔐 **Auth** | 3-step OTP email registration + JWT access/refresh tokens |
| ⚡ **Rate Limiting** | 4-level DB-driven rate limiting (burst / per-chat / hourly / daily) |
| 📧 **Email** | 15+ automated email triggers via async SMTP |
| 🔌 **WebSocket** | Real-time bidirectional chat streaming |

---

## 🛠️ Tech Stack

### Frontend (`kubera-frontend/`)
| Technology | Purpose |
|---|---|
| React 18 + TypeScript | UI framework |
| Vite | Build tool & dev server |
| Tailwind CSS + shadcn/ui | Styling & component library |
| React Router v6 | Client-side routing |
| TanStack Query | Server state management |
| React Hook Form + Zod | Form validation |
| Recharts | Data visualisation |
| Vercel | Deployment |

### Backend (`Kubera-Backend/`)
| Technology | Purpose |
|---|---|
| FastAPI | Web framework |
| Python 3.11+ | Runtime |
| PostgreSQL / Supabase | Primary database |
| asyncpg | Async DB driver |
| Pydantic v2 | Data validation |
| python-jose | JWT authentication |
| APScheduler | Background jobs |
| LangChain + MCP | AI orchestration |
| OpenRouter | LLM gateway |
| yfinance | Stock market data |
| Docker + AWS EC2 | Deployment |

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** ≥ 18 & npm (or bun)
- **Python** ≥ 3.11
- **PostgreSQL** (or a [Supabase](https://supabase.com) project)

---

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/kubera.git
cd kubera
```

---

### 2. Backend Setup

```bash
cd Kubera-Backend

# Create & activate virtual environment
python -m venv venv
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Configure environment variables
cp .env.example .env
# → Edit .env with your Supabase, JWT, SMTP, and OpenRouter credentials

# Initialise the database
python scripts/init_db.py

# Start the backend (development)
uvicorn main:app --reload --port 8000
```

The API will be available at `http://localhost:8000`  
Interactive docs: `http://localhost:8000/docs`

---

### 3. Frontend Setup

```bash
cd kubera-frontend

# Install dependencies
npm install        # or: bun install

# Start the dev server
npm run dev        # or: bun dev
```

The app will be available at `http://localhost:5173`

> **Tip:** Make sure `VITE_API_URL` in your frontend `.env` points to `http://localhost:8000`

---

### 4. Full Stack with Docker (Optional)

```bash
cd Kubera-Backend
cp .env.example .env   # fill in your values

docker compose up --build
```

---

## 🌍 Live Deployment

| Service | URL |
|---|---|
| Frontend | [kubera-frontend-olive.vercel.app](https://kubera-frontend-olive.vercel.app/) |
| Backend API | [kubera007.duckdns.org](https://kubera007.duckdns.org) |
| API Docs | [kubera007.duckdns.org/docs](https://kubera007.duckdns.org/docs) |
| Docker Hub | [tejascm/kubera-backend](https://hub.docker.com/r/tejascm/kubera-backend) |

---

## 📖 API Documentation

Once the backend is running, interactive API docs are available at:

- **Swagger UI**: `http://localhost:8000/docs`
- **ReDoc**: `http://localhost:8000/redoc`

Key endpoint groups:

| Prefix | Description |
|---|---|
| `/api/v1/auth` | Registration, login, OTP, token refresh |
| `/api/v1/users` | User profile management |
| `/api/v1/chats` | Chat session CRUD |
| `/api/v1/portfolio` | Portfolio tracking |
| `/api/v1/admin` | Admin panel & rate-limit config |
| `/ws` | WebSocket chat endpoint |

---

## 🔧 Environment Variables

See [`Kubera-Backend/.env.example`](./Kubera-Backend/.env.example) for the full list of required backend variables, including:

- `DATABASE_URL` — Supabase/PostgreSQL connection string
- `SECRET_KEY` — JWT signing secret
- `OPENROUTER_API_KEY` — LLM gateway key
- `SMTP_*` — Email configuration
- `ALLOWED_ORIGINS` — CORS origins (add your frontend URL)

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m "feat: add your feature"`
4. Push to your branch: `git push origin feature/your-feature-name`
5. Open a Pull Request

Please follow [Conventional Commits](https://www.conventionalcommits.org/) for commit messages.

---

## 📄 License

This project is licensed under the **MIT License**.  
See [LICENSE](./LICENSE) for details.

---

<div align="center">
  <p>Built with ❤️ for Indian stock market enthusiasts</p>
</div>
