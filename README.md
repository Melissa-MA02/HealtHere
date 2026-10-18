# HealtHere
Multilingual mobile app helping older migrants in Victoria find nearby health services, language-matched doctors, translation help, and offline emergency support. Built with Flutter, FastAPI, PostgreSQL and Azure. Monash FIT5120 Industry Experience project

google dirve link: https://drive.google.com/drive/folders/1AsEVdpx2-AWBTKyGAeConWNeTmDWIlrr?usp=sharing 
HealtHere

Find care. Understand it. Get help fast — in your language.

HealtHere is a multilingual mobile app that helps older migrants in Victoria, Australia, find nearby health services, communicate with health workers, and act quickly in an emergency. It was built by a six-person team for the Monash University FIT5120 Industry Experience Studio (July – October 2026).

The Problem

Many older migrants in Victoria have limited English. This makes it hard to:

Find a nearby clinic, GP, or hospital
Find a practitioner who speaks their language
Explain symptoms or understand health information
Call for help in an emergency

HealtHere brings these tasks into one simple, multilingual app.

Features
Health facility finder – search and map 4,000+ Victorian health facilities, with opening hours and contact details
Language-matched practitioners – see which practices list doctors who speak the user's language (75 languages)
Translation help – translate typed text, voice, and images into simpler, clearer language
Emergency assistance – a built-in emergency phrase library that works offline, plus guided Call 000 support
Multilingual interface – the app itself is available in multiple languages
Reminders and health information – simple tools to support everyday health tasks
Tech Stack
Layer	Technology
Mobile app	Flutter
Backend API	Python, FastAPI
Hosting	Azure App Service
Database	PostgreSQL (Neon), Alembic migrations
Data pipeline	Python ETL, nightly refresh via GitHub Actions
Backup	Docker local PostgreSQL
Text translation	Azure Translator v3
Simplify / voice / image	Groq-hosted Qwen, Whisper, Qwen Vision
Data Sources
ID	Source	Used for
D2	Geoscience Australia – National Health Services Directory extract	Core facility records
D4 / D5	Vicmap (Victorian Government)	Location and facility features
D12	Healthdirect Service Finder (manually collected)	Practitioner languages
D13	Healthdirect Service Finder (scripted collection)	Opening hours, contact details

The database holds 8 tables, including 4,000+ facilities and 2,900+ practitioner-language records.

Licensing note: Healthdirect content may not be republished without Healthdirect's written permission. Check the Data Management Plan before any public release.

Getting Started

Update the paths and commands below to match this repository's structure.

Prerequisites
Flutter SDK
Python 3.11+
PostgreSQL (or a Neon connection string)
Docker (optional, for the local backup database)
Backend
bash
cd backend
pip install -r requirements.txt
cp .env.example .env        # add DB URL and API keys
alembic upgrade head        # apply database migrations
uvicorn app.main:app --reload
Mobile app
bash
cd frontend
flutter pub get
flutter run
Environment variables

Never commit real keys. Typical values include:

DATABASE_URL
AZURE_TRANSLATOR_KEY and AZURE_TRANSLATOR_REGION
GROQ_API_KEY
CORS_ORIGINS
Project Documentation

This project was delivered with a full Project Governance Portfolio, including:

Personas, empathy maps, and design thinking artefacts
User story mapping and customer journey maps
Conceptual ERD and system architecture diagrams
Ethics canvas and AI design report
Data Management Plan (all three iterations)
Database management and handover guide

Disclaimer

HealtHere is a student project. It does not provide medical advice. In an emergency, always call 000.
How We Worked
Agile delivery across three iterations
Daily standups, sprint reviews, and retrospectives
Usability testing fed directly into the backlog
