# NextRound.ai 🎯

An intelligent career acceleration platform powered by Google Generative AI. NextRound.ai bridges the gap between candidate resumes and job postings by automating job description scraping, performing deep semantic resume analysis, and dynamically generating predictive mock interview questions.

## 🏗️ System Architecture & Workflow

NextRound.ai integrates robust document parsing, headless browser automation, and LLM orchestration into a unified Node.js backend:

1.  **Resume Parsing:** Extracts and normalizes unstructured text from candidate PDF documents using `pdf-parse`[cite: 3].
2.  **Dynamic Web Scraping:** Leverages headless automation via `puppeteer` to fetch live Job Descriptions (JDs) directly from target URLs[cite: 3].
3.  **AI Intelligence Engine:** Passes parsed profiles and JDs through the `@google/genai` SDK to evaluate skill alignment gaps and synthesize tailored technical/behavioral mock interview questions[cite: 3].
4.  **Secure Persistence:** Handles credential hashing via `bcrypt` and manages application data structures with MongoDB and Mongoose[cite: 3].

## 💻 Tech Stack

*   **Runtime & Server:** Node.js, Express.js[cite: 3]
*   **Database & ODM:** MongoDB, Mongoose[cite: 3]
*   **AI Integration:** Google Generative AI SDK (`@google/genai`)[cite: 3]
*   **Automation & Parsing:** Puppeteer[cite: 3], PDF-Parse[cite: 3]
*   **Security:** Bcrypt[cite: 3]

## 🚀 Getting Started

### Prerequisites
*   Node.js (v18+)
*   MongoDB instance (Local or Atlas)
*   Google Gemini API Key

### Installation & Setup

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/yashp007-nerd/NextRound.ai.git](https://github.com/yashp007-nerd/NextRound.ai.git)
    cd NextRound.ai/Backend
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

3.  **Configure Environment Variables:**
    Update your `.env` file inside the `Backend` directory[cite: 3] with your configuration:
    ```env
    PORT=5000
    MONGODB_URI=mongodb://localhost:27017/nextround-ai
    GEMINI_API_KEY=your_google_genai_api_key
    ```

4.  **Launch the Backend Service:**
    ```bash
    npm run dev
    # or
    npm start
    ```

## 📡 Core API Capabilities

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/api/analyze` | Ingests resume files and target JDs, returning a comprehensive match score. |
| `POST` | `/api/interview/generate` | Triggers the Google GenAI pipeline to create role-specific mock questions. |

## 🛠️ Future Optimizations

*   **Asynchronous Worker Queues:** Offload heavy Puppeteer scraping and LLM generation tasks to a background queue (like BullMQ with Redis) to keep HTTP response times instant.
*   **Voice Simulation Layer:** Introduce real-time speech-to-text integration to evaluate oral mock interview responses dynamically.

---
*Designed and developed by Yash Patel*