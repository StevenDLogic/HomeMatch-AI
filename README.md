# HomeMath-AI

HomeMath-AI is an intelligent, AI-driven platform designed to provide personalized real estate guidance and financial insights tailored to each user's unique situation. Leveraging advanced language models and real‑world property data, the system helps users make informed decisions about housing options and investments.

![HomeMath-AI Screenshot](./public/screenshot.png)

---

## 🚀 Key Features

- **Personalized Recommendations** – Input your life circumstances, budget, and preferences to receive custom property suggestions.
- **Real Estate Data Integration** – Aggregates listings from Czech real‑estate portal, with filtering and scoring based on user criteria.
- **AI Powered Reasoning** – Combines multiple large language models to analyze data, estimate affordability, and explain suggestions in natural language.
- **Modular Backend** – Built with FastAPI, allowing easy extension with new data sources or additional AI services.
- **Optional MongoDB Storage** – Persist scraped listing data locally or in the cloud for offline analysis and faster responses.

## 🏗️ Architecture Overview

1. **Frontend** – A Next.js/TypeScript web application that collects user input and displays AI-generated recommendations.
2. **API Layer** – FastAPI providing endpoints for request handling, model orchestration, and data access.
3. **AI Models** – Utilizes state-of-the-art reasoning models such as Mixtral and Llama 3 via Groq API (configurable).
4. **Data Pipeline** – Optional scraper (external repo) gathers listing information from sreality.cz and stores it in MongoDB.

## 💻 Development Setup

1. **Clone the repository**
   ```sh
   git clone <repository-url>
   cd home-ai-advisor
   ```
2. **Environment configuration**
   - Copy `.env.example` to `.env` and populate the variables.
   - `GROQ_API_KEY` – obtain from your Groq account.
   - `NEXT_PUBLIC_API_BASE_URL` – e.g. `http://localhost:8000` for local API.
3. **Install dependencies**
   ```sh
   npm install      # frontend
   pip install -r requirements.txt  # backend
   ```
4. **Run services**
   - Start backend: `uvicorn api.index:app --reload`
   - Start frontend: `npm run dev`
   - Access UI at localhost port 3000; API docs available at localhost port 8000 under /docs.

## ☁️ Deployment

- **Vercel** for frontend: Connect the repository and configure environment variables (`GROQ_API_KEY`, `NEXT_PUBLIC_API_BASE_URL`).
- **FastAPI backend** can be deployed to any Python-friendly platform (Heroku, DigitalOcean, AWS). Use environment variables for sensitive keys.

For a quick start, you can use the existing deployment configuration included in this README.

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/your-change`).
3. Commit your changes (`git commit -m "Add useful feature"`).
4. Push to the branch (`git push origin feature/your-change`).
5. Open a pull request detailing your improvements.

Please follow standard code style and include tests when appropriate.

## 📄 License

This project is licensed under the MIT License. See the LICENSE file for details.

---

*Created and maintained by the HomeMath-AI team.*