# 🏗️ INVESTMENT HUNTER V2.0 - MİMARİ YAPI VE SİSTEM TASARIMI
**Comprehensive System Architecture & Design Specifications - Updated with n8n v1.111.0**

## 🎯 **SİSTEM GENEL BAKIŞ**

### **Mimari Prensipler**
- **Microservices Architecture:** Modüler, scalable yapı
- **Event-Driven Design:** Real-time data flow
- **API-First Approach:** Decoupled frontend/backend
- **Database-Centric:** PostgreSQL as single source of truth
- **Automation-First:** n8n workflow automation (v1.111.0)

### **Teknoloji Stack'i**
```
Frontend: React 18 + TypeScript + Vite + Shadcn-ui + Tailwind CSS
Backend: Node.js + Express + PostgreSQL + Prisma ORM
Automation: n8n v1.111.0 (Self-hosted Docker + SQLite)
AI: OpenAI GPT-4 API
Real-time: WebSocket + Server-Sent Events
Caching: Redis (optional)
Deployment: Docker + VDS hosting
```

---

## 🗄️ **DATABASE TASARIMI**

### **PostgreSQL Schema**
```sql
-- Ana Vehicles Tablosu
CREATE TABLE vehicles (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  listing_number VARCHAR UNIQUE NOT NULL,
  brand VARCHAR NOT NULL,
  model VARCHAR NOT NULL,
  year INTEGER NOT NULL,
  listing_price DECIMAL(12,2) NOT NULL,
  fair_price DECIMAL(12,2),
  quick_sale_price DECIMAL(12,2),
  quick_buy_price DECIMAL(12,2),
  mileage INTEGER,
  city VARCHAR NOT NULL,
  district VARCHAR,
  days_on_market INTEGER DEFAULT 0,
  price_drop_percent DECIMAL(5,2),
  price_drop_amount DECIMAL(12,2),
  description TEXT,
  image_url VARCHAR,
  damage_painted INTEGER DEFAULT 0,
  damage_replaced INTEGER DEFAULT 0,
  heavy_damage BOOLEAN DEFAULT FALSE,
  opportunity_score INTEGER CHECK (opportunity_score >= 0 AND opportunity_score <= 100),
  potential_profit DECIMAL(12,2),
  estimated_sale_days INTEGER,
  seller VARCHAR,
  seller_type VARCHAR CHECK (seller_type IN ('Galeri', 'Sahibinden', 'Ekspertiz')),
  is_todays_opportunity BOOLEAN DEFAULT FALSE,
  fuel_type VARCHAR,
  transmission VARCHAR,
  engine_size VARCHAR,
  horsepower VARCHAR,
  color VARCHAR,
  body_type VARCHAR,
  yearly_return DECIMAL(5,2),
  holding_period INTEGER,
  risk_level VARCHAR CHECK (risk_level IN ('Düşük', 'Orta', 'Yüksek')),
  tramer_amount DECIMAL(12,2),
  -- Normalization fields
  raw_data JSONB, -- Original scraped data
  normalized_at TIMESTAMP DEFAULT NOW(),
  data_source VARCHAR DEFAULT 'sahibinden',
  scrape_batch_id VARCHAR,
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);
```

### **Environment Configuration**
```bash
# Application
NODE_ENV=development
PORT=3000
APP_URL=http://localhost:3000

# Database
DATABASE_URL=postgresql://username:password@localhost:5432/investment_hunter
DB_HOST=localhost
DB_PORT=5432
DB_NAME=investment_hunter
DB_USER=postgres
DB_PASSWORD=your_password
DB_SSL=false

# OpenAI API
VITE_OPENAI_API_KEY=your_openai_api_key_here
OPENAI_MODEL=gpt-4
OPENAI_MAX_TOKENS=2000
OPENAI_TEMPERATURE=0.7

# n8n Integration (v1.111.0)
N8N_BASE_URL=https://n8n.yatirimavcisi.com.tr/api/v1
N8N_VERSION=1.111.0
N8N_DEPLOYMENT=docker-sqlite
N8N_WEBHOOK_URL=https://n8n.yatirimavcisi.com.tr/webhook/
```

---

**📅 Doküman Tarihi:** 2025-01-27  
**🏗️ Mimari Versiyon:** v2.0 (Updated with n8n v1.111.0)  
**🔄 Son Güncelleme:** n8n integration, normalization scripts, environment config  
**📊 Kapsam:** Full-stack system architecture with data processing pipeline  
**🎯 Durum:** Ready for implementation with enhanced n8n workflows