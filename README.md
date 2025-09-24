# Investment Hunter v3.0

AI-Powered Vehicle Investment Analysis Platform with Real-time Data Processing

## 🎯 Project Overview

Investment Hunter v3.0 is a comprehensive vehicle investment analysis platform that leverages AI, real-time data processing, and automated workflows to identify profitable vehicle investment opportunities.

### Key Features

- **AI-Powered Analysis**: OpenAI GPT-4 integration for intelligent vehicle analysis
- **Real-time Data Processing**: n8n v1.111.0 workflows for automated data collection
- **Advanced Search**: Multi-criteria search with smart query builder
- **Price Monitoring**: Real-time price change detection and notifications
- **Investment Scoring**: Automated opportunity score calculation
- **Data Normalization**: Python scripts for data cleaning and processing

## 🏗️ Architecture

- **Frontend**: React 18 + TypeScript + Vite + Shadcn-ui + Tailwind CSS
- **Backend**: Node.js + Express + PostgreSQL + Prisma ORM
- **Automation**: n8n v1.111.0 (Self-hosted Docker + SQLite)
- **AI**: OpenAI GPT-4 API
- **Real-time**: WebSocket + Server-Sent Events
- **Deployment**: Docker + VDS hosting

## 📊 Current Status

- **Phase**: Foundation Setup (Phase 1)
- **Progress**: 0/67 tasks completed (0%)
- **Active Task**: 1.1.1 - Git Repository Setup
- **Branch Strategy**: Git-flow with feature branches

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- PostgreSQL 14+
- Python 3.9+
- Docker (for n8n)

### Installation

```bash
# Clone repository
git clone git@github.com:07salih07/investment-hunter-v3.git
cd investment-hunter-v3

# Install dependencies
npm install

# Setup environment
cp .env.example .env
# Edit .env with your configuration

# Setup database
npm run db:setup

# Start development server
npm run dev
```

## 📋 Development Workflow

### Branch Strategy

```
main (Production-ready)
├── develop (Integration branch)
├── feature/[task-id]-[description] (Feature branches)
├── hotfix/[issue-description] (Critical fixes)
└── release/v[version] (Release preparation)
```

### Task Management

All development follows the detailed progress tracker:
- 67 total tasks across 4 phases
- Each task has specific deliverables and test criteria
- Systematic progression: 1.1.1 → 1.1.2 → 1.1.3...

## 🔧 Environment Configuration

Key environment variables:

```bash
# Database
DATABASE_URL=postgresql://user:pass@localhost:5432/investment_hunter
DB_HOST=localhost
DB_PORT=5432

# n8n Integration
N8N_BASE_URL=https://n8n.yatirimavcisi.com.tr/api/v1
N8N_VERSION=1.111.0
N8N_WEBHOOK_URL=https://n8n.yatirimavcisi.com.tr/webhook/

# OpenAI API
OPENAI_API_KEY=sk-proj-...
OPENAI_MODEL=gpt-4

# API Configuration
API_BASE_URL=http://localhost:3001/api
PROXY_API_URL=http://your-vds-ip:3001/proxy
```

## 📚 Documentation

- `docs/1_ALEX_GIT_CALISMA_KURALLARI.md` - Git workflow rules
- `docs/2_PROGRESS_TRACKER_DETAYLI.md` - Detailed progress tracking
- `docs/3_MIMARI_YAPI_VE_SISTEM_TASARIMI_GUNCELLENMIS.md` - System architecture
- `docs/4_HATA_ANALIZI_VE_YENI_BASLANGIÇ_PROTOKOLU.md` - Error analysis and protocols

## 🤝 Contributing

1. Read the Git workflow rules in `docs/1_ALEX_GIT_CALISMA_KURALLARI.md`
2. Check the progress tracker for available tasks
3. Create feature branch: `git checkout -b feature/[task-id]-[description]`
4. Follow conventional commits format
5. Test thoroughly before merge
6. Update progress tracker and create completion report

## 📈 Progress Tracking

Development progress is tracked in `REPORTS/` directory:
- Task completion reports
- Daily progress summaries
- Issue tracking and resolution
- Performance metrics

## 🔒 Security

- SSH key-based Git authentication
- Environment variable protection
- Database security with RLS policies
- API rate limiting and authentication

## 📄 License

MIT License - see LICENSE file for details

## 🚀 Deployment

Production deployment uses:
- Docker containers
- PostgreSQL database
- n8n automation workflows
- Nginx reverse proxy
- SSL/TLS encryption

---

**Created**: 2025-01-27  
**Version**: 3.0.0  
**Status**: In Development  
**Next Milestone**: Foundation Complete (Week 1)