# 📊 AI Marketing Performance Report Automation

## 📌 Overview
Project ini merupakan sistem end-to-end automation untuk menghasilkan laporan kinerja pemasaran digital secara otomatis menggunakan AI.

Sistem ini mengintegrasikan data dari berbagai sumber (Ads, Analytics, CRM), melakukan analisis menggunakan AI, dan menghasilkan laporan PDF lengkap yang langsung dikirim ke stakeholder.

## 🚨 Problem
- Pengumpulan data marketing memakan waktu lama
- Perhitungan metrik rawan error
- Analisis dilakukan manual
- Reporting lambat dan tidak real-time

## 💡 Solution
Membangun sistem automation berbasis n8n untuk:
- Mengambil data dari berbagai sumber
- Menggabungkan dan membersihkan data
- Menghitung metrik utama (CPL, Bounce Rate)
- Melakukan analisis strategis menggunakan AI
- Menghasilkan laporan PDF otomatis
- Mengirim laporan ke stakeholder via email
- Mengirim alert ke Slack jika terjadi anomaly

## ⚙️ Tech Stack
- n8n
- AI Agent (Gemini / LLM)
- Google Sheets
- QuickChart (Visualization)
- PDFco (PDF generation)
- Gmail API
- Slack API

## 🔍 Key Features
- Automated data pipeline (Ads, Analytics, CRM)
- AI-generated insights (KEEP & IMPROVE)
- Real-time anomaly detection (CPL alert)
- Automated report generation (PDF)
- Multi-channel distribution (Email + Slack)

## 📊 Impact
- Mengurangi waktu reporting dari 4–8 jam → < 15 menit
- Menghilangkan human error dalam perhitungan
- Insight langsung tersedia secara otomatis
- Monitoring performa secara real-time

## ⚠️ Limitations
- Bergantung pada API eksternal
- Perlu validasi hasil AI
- Setup awal kompleks

## 📄 Documentation

See full documentation in report.pdf

## 🧠 Workflow Architecture

```mermaid
flowchart TD
    A[Schedule Trigger] --> B[n8n Workflow]

    B --> C[Fetch Marketing Data]
    C --> D[Data Cleaning and Merge]

    D --> E[Metric Calculation]
    E --> F{CPL Threshold Check}

    F -->|High CPL| G[Send Slack Alert]
    F -->|Normal| H[AI Analysis]

    H --> I[Generate Insights]
    I --> J[Create Charts]

    J --> K[Generate PDF Report]
    K --> L[Send Email to Stakeholder]

    L --> M[Logging to Google Sheets]
