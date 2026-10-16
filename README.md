## Project Structure

```
StudySpark/
├── StudySpark.py                   
├── env.example                     # Environment template
├── pyproject.toml                  # Dependencies (uv)
├── pages/                          # Additional UI pages
│   ├── 1_Document_Upload.py        # Document upload page
│   ├── 2_Summary.py                # Summary page
│   ├── 3_QA.py                     # Questions/Answers page
│   └── 4_Quiz.py                   # Quiz page
├── services/                       
│   ├── ai_service.py               # All Gemini API calls
│   └── pdf_processing_service.py   # PDF processing (NOTE: as of now, pdf processing is done using ai_service, making this file obsolete)
└── utils/                          # Shared utilities
    └── lang_tracing.py             # Langfuse configuration
```
### My Contributions

**AI Feature Development**
- Developed the document summarisation and interactive quiz-generation features using Python, Streamlit and Google's Gemini API.
- Extended the existing `AIService` class to support AI-powered summarisation and multiple-choice question generation.
- Implemented configurable prompts for different summary formats and lengths, as well as structured quiz generation and JSON response parsing.

**Application Development**
- Built interactive Streamlit interfaces for the Summary and Quiz modules.
- Implemented session-state management to maintain quiz progression, user submissions and answer feedback.
- Developed answer-validation logic, sequential question navigation and configurable learning options.

**Testing and Debugging**
- Participated in application testing, debugging and optimisation to improve functionality and usability.

### Collaboration

Study-Spark was developed collaboratively with [@Jur1ng](https://github.com/Jur1ng).

My project partner established the initial AI service architecture and developed other application components, while I extended the shared service with the 
AI functionality required for the document summarisation and quiz-generation modules.

The application deployment and hosting were managed by my project partner.
## Streamlit.io App Link - https://studyspark-8sj2nxw3ptg8heauugzyps.streamlit.app/


## User Guide
### 1. Open the app (be it with the link or locally)
### 2. Upload a PDF document
### 3. Now you can do one of the following:
#### 3.1 Generate document summary - choose your preferred summary format and length, and press "Generate Summary"
#### 3.2 Chat with an "Assistant" - just ask a question regarding the paper, and receive an answer
#### 3.3 Generate a quiz - Pick a number of questions, press "Generate Quiz" and you get to solve a quiz about the document


## Local Setup Instructions
### 1. Clone and Navigate

```bash
git clone https://github.com/emmohan/Study-Spark.git
```
```bash
cd StudySpark
```
### 2. Install Dependencies

Using `uv` (recommended):
```bash
uv sync
```

Or using pip:
```bash
pip install (all of the dependancies listed in the pyproject.toml file)
```
### 3. Configure Environment

Create `.env` file and add your API keys:
```
GOOGLE_API_KEY=your_gemini_api_key_here
```
Get your Gemini API key at: https://aistudio.google.com/apikey

### 4. (Optional) Configure Langfuse Tracing

For observability, add Langfuse keys to `.env`:
```
LANGFUSE_PUBLIC_KEY=your_public_key
LANGFUSE_SECRET_KEY=your_secret_key
LANGFUSE_BASE_URL=https://cloud.langfuse.com
```

Sign up at: https://cloud.langfuse.com

### 5. Run the App

```bash
uv run streamlit run StudySpark.py
```

Or:
```bash
streamlit run StudySpark.py
```

The app will open in your browser at `http://localhost:8501`
