# Auto Prompt Veo3 — n8n Workflow

**Auto Prompt Veo3** adalah workflow otomatis berbasis **n8n** yang dirancang untuk menghasilkan prompt video AI untuk **Google Veo 3**, berdasarkan analisis tren konten **ASMR di TikTok Indonesia**.  
Proyek ini mengintegrasikan **Google Sheets**, **Google Gemini (PaLM)**, dan **LangChain Agent** untuk membangun alur kerja analisis, generasi konten, dan penyimpanan data secara otomatis.

---

## Fitur Utama

- **Otomatisasi penuh**
  - Mengambil data jenis ASMR dari Google Sheets.
  - Menganalisis tren konten menggunakan model Gemini.
  - Menghasilkan prompt video Veo 3 berdurasi 8 detik dalam format JSON terstruktur.
  - Menyimpan hasil akhir ke Google Sheets secara otomatis.

- **Integrasi AI Multi-Layer**
  - Menggunakan **Google Gemini (PaLM)** untuk analisis dan generasi prompt.
  - Memanfaatkan **LangChain Agent** untuk pemrosesan bertahap:
    1. Analisis tren konten ASMR.
    2. Pembuatan prompt video Veo 3.
    3. Klasifikasi jenis objek ASMR.

- **Integrasi Spreadsheet**
  - Data input dan output disimpan di Google Sheets (`todo nanda / Sheet3`).
  - Semua hasil disimpan dalam format tabel yang terstruktur.

---

## Diagram Alur

![Workflow Preview](https://github.com/NandaBahtiar/n8n-auto-prompt-veo3/blob/main/Screenshot_6-11-2025_145058_cytopathogenic-degreeless-dahlia.ngrok-free.dev.jpeg)

---

## Alur Kerja (Flow Summary)

```mermaid
graph TD
  A[Manual Trigger] --> B[Get Row(s) from Google Sheets]
  B --> C[Code Node - Format Data]
  C --> D[AI Agent 1 - Social Media Analyst]
  D --> E[AI Agent 2 - Veo 3 Prompt Generator]
  E --> F[Code Node - Parse JSON]
  F --> G[AI Agent 3 - ASMR Object Classifier]
  G --> H[Append Result to Google Sheets]
