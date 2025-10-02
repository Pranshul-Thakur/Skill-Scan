# SkillScan ATS

AI-powered career preparation platform with resume analysis, interview question generation, and personalized study plans using Google Gemini.

## Features

### Resume Checker
- ATS score calculation and optimization suggestions
- PDF/DOCX file support
- Three analysis modes: Quick Scan, Detailed Analysis, ATS Optimization
- Job description matching
- Keyword density analysis

### Interview Questions
- Role-specific interview questions scraped from GeeksforGeeks
- Instant answers for each question
- 9 technical roles supported

### Study Plan Generator
- Customizable preparation timeline (1-12 weeks)
- Role-specific learning roadmap
- Daily practice problems from LeetCode
- Resource recommendations (books, videos, articles)

## Tech Stack

### Backend
- Flask REST APIs (3 separate services)
- Google Gemini 1.5 Flash for AI analysis
- BeautifulSoup for web scraping
- PyMuPDF for PDF parsing
- python-docx for DOCX parsing

### Frontend
- React 19 with React Router
- Lottie animations
- Deployed on Vercel

## Project Structure

```
├── Advanced-ATS-Resume-Checker/
│   ├── app.py           # Resume analysis API
│   ├── app2.py          # Study plan generator API
│   ├── app3.py          # Interview questions API
│   └── requirements.txt
├── React_FrontEnd/my-app/
│   ├── src/
│   │   ├── App.js       # Main React components
│   │   └── App.css      # Styling
│   └── package.json
└── README.md
```

## Setup

### Backend Setup

1. Navigate to backend directory:
```bash
cd Advanced-ATS-Resume-Checker
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Create `.env` file:
```
GOOGLE_API_KEY=your_gemini_api_key
```

4. Run all three services (separate terminals):
```bash
python app.py      # Port 5000
python app2.py     # Port 5002
python app3.py     # Port 5001
```

### Frontend Setup

1. Navigate to frontend directory:
```bash
cd React_FrontEnd/my-app
```

2. Install dependencies:
```bash
npm install
```

3. Start development server:
```bash
npm start
```

Access at `http://localhost:3000`

## Live Demo

Frontend: [https://skill-scan-ats.vercel.app/](https://skill-scan-ats.vercel.app/)

Backend endpoints:
- Resume: `https://backend-skill-ihvv.onrender.com`
- Study Plan: `https://backend-skill-1.onrender.com`
- Questions: `https://backend-skill-2.onrender.com`

## API Endpoints

### Resume Analysis
```http
POST /analyze
Content-Type: multipart/form-data

Fields:
- resume: file (PDF/DOCX)
- job_description: text
- analysis_option: string
```

### Study Plan Generation
```http
POST /generate-study-plan
Content-Type: application/json

{
  "role": "Software Engineer",
  "weeks": 4
}
```

### Interview Questions
```http
POST /get-interview-questions
Content-Type: application/json

{
  "role": "Backend Engineer"
}
```

## Supported Roles

- Backend Engineer
- Frontend Engineer
- Fullstack Engineer
- AI/ML Engineer
- MLOps Engineer
- SDE
- Data Scientist
- Data Analyst
- HR Interview Questions

## Requirements

- Python 3.8+
- Node.js 14+
- Google API key with Gemini access

## Notes

- All three Flask services must run simultaneously
- Backend services deployed on Render (may have cold start delays)
- Frontend uses React 19 features
