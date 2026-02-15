# 📱 Samsung Phone Advisor (AI Agent)

## 📖 Overview
The **Samsung Phone Advisor** is an intelligent AI agent designed to act as a product expert for Samsung smartphones. It solves the problem of scattered product information by providing a centralized, query-based interface for specifications and comparisons.

This project demonstrates a **Hybrid Data Architecture**, combining local database caching with real-time web scraping to ensure data availability and speed.

---

## ⚙️ How It Works (Architecture)

The system follows a "Cache-First" logic to optimize performance:

1. **User Query:** The user searches for a phone (e.g., *"Samsung S24"*).
2. **Database Check:** The agent first checks its local **PostgreSQL**.
   - ✅ *Found:* Returns data instantly (< 0.1s).
3. **Web Scraping (Fallback):**
   - ❌ *Not Found:* If the data is missing, the agent activates its **Scraper Module**.
   - It searches Wikipedia/GSMArena sources, extracts the specifications (Display, Battery, Camera, etc.), and **saves** them to the database for future use.
4. **Response:** The structured data is presented to the user.


## 🛠️ Tech Stack
- **Backend:** FastAPI
- **Database:** PostgreSQL
- **Web Scraping:** BeautifulSoup4, Requests
- **Frontend:** Bootstrap 5, JavaScript
- **Deployment:** Render Cloud

---
## Live Demo: https://samsung-phone-adviser-1.onrender.com/
---

### Output Preview

**Comparison Result :**

![photo_2026-02-05 02 24 33](https://github.com/user-attachments/assets/bf5e9849-0648-4d30-98ca-38f20a7bb906)


**Single Result :**

![photo_2026-02-05 02 24 58](https://github.com/user-attachments/assets/8a9f71ff-bd50-4fe0-807b-cd423b1f29fb)

---


## 🚀 How to Run Locally

### 1. Navigate to the directory
```bash
cd Task_2
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Start the Server
```bash
uvicorn main:app --reload
```

### 4. Access the Agent
Open your browser and go to:  
👉 http://127.0.0.1:8000

---

## 📂 Key Files
- **main.py:** The API gateway handling user requests.
- **db_utils.py:** Manages SQLite connections, creating tables, and fetching/storing data.
- **scraper_utils.py:** Contains the logic to parse HTML and extract phone specifications from the web.
- **phones.db:** The auto-generated database file storing phone specs.

---

## 📂 Project Structure

```

├── Task_2/
│   ├── main.py
│   ├── db_utils.py
│   ├── scraper_utils.py
│   ├── index.html
│   └── phones.db
|   └── requirements.txt

```


**Developed by Anukul Chandra**
