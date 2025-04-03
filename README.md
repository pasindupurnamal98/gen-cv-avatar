# 🛍️ Interactive AI Shopping Experience with Azure AI Avatar

This project is a full-stack AI-powered shopping assistant built using **Azure OpenAI**, **Cognitive Search**, **Azure Speech**, **Blob Storage**, **SQL**, and **Talking Avatars**.

> 🌟 Ask product questions, get answers from an avatar, view real-time responses, and browse with voice and vision.

---

## 📸 Live Demo (Optional)

> 🔪 

```
https://your-avatar-shop.azurestaticapps.net
```

---

## 🧱 Architecture

- **Frontend**: Vanilla HTML/CSS/JS
- **Backend**: Azure Functions (Python)
- **AI Stack**:
  - Azure OpenAI (GPT-3.5 / GPT-4o)
  - Azure Cognitive Search (vector + keyword)
  - Azure Speech + TTS Avatar
- **Data**: Azure SQL + Blob Storage
- **Streaming**: WebRTC via Azure Communication Services

---

## ✨ Features

👉 Talking avatar assistant  
👉 Multilingual speech-to-text & synthesis  
👉 Smart product Q&A using GPT + vector search  
👉 Image rendering from blob storage  
👉 SQL-backed customer & order data  
👉 Seamless voice interaction (mic button)

---

## 🚀 Setup Instructions

### 1. Clone the Repo

```bash
git clone https://github.com/yourname/azure-ai-avatar-shop.git
cd azure-ai-avatar-shop
```

### 2. Create Azure Resources

Required Azure services:

- ✅ Azure OpenAI (GPT + embeddings)
- ✅ Azure AI Search
- ✅ Azure SQL Database
- ✅ Azure Blob Storage
- ✅ Azure Speech (TTS)
- ✅ Azure Communication Services

You can find a full list [in the original repo](https://github.com/Azure-Samples/gen-cv-avatar) or Azure Portal.

---

### 3. Prepare Environment Config

⚠️ Create a file called: `interactive/api/local.settings.json` (not committed!)

```json
{
  "IsEncrypted": false,
  "Values": {
    "FUNCTIONS_WORKER_RUNTIME": "python",
    "AZURE_OPENAI_API_KEY": "<your-key>",
    "AZURE_SEARCH_API_KEY": "<your-key>",
    "AZURE_SEARCH_ENDPOINT": "https://<your-search>.search.windows.net",
    "AZURE_OPENAI_ENDPOINT": "https://<your-openai>.openai.azure.com/",
    "AZURE_OPENAI_API_VERSION": "2023-07-01-preview",
    "AZURE_OPENAI_EMBEDDINGS_DEPLOYMENT": "text-embedding-ada-002",
    "AZURE_OPENAI_CHAT_DEPLOYMENT": "gpt-35-turbo",
    "AZURE_SPEECH_REGION": "<your-region>",
    "AZURE_SPEECH_API_KEY": "<your-key>",
    "BLOB_SAS_URL": "https://...container?...",
    "SQL_DB_SERVER": "xxx.database.windows.net",
    "SQL_DB_USER": "xxx",
    "SQL_DB_PASSWORD": "xxx",
    "SQL_DB_NAME": "OutdoorEquipmentShop"
  }
}
```

Add this file to `.gitignore`.

---

### 4. Deploy to Azure Static Web Apps

Install the CLI:

```bash
npm install -g @azure/static-web-apps-cli
az login
```

Then deploy:

```bash
cd interactive
swa deploy --app-location src --api-location api
```

---

### 5. Run Locally (Dev Mode)

```bash
cd interactive
swa start src --api-location api
```

Open browser → `http://localhost:4280`

---

## 📦 Folder Structure

```
interactive/
├── src/        → Frontend HTML/JS/CSS
├── api/        → Azure Functions (Python)
├── data/       → Embedding files / csvs
├── README.md   → This file
```

---

## 📸 Screenshots

| Avatar Assistant | Product Cards |
|------------------|----------------|
| ![](docs/avatar.png) | ![](docs/products.png) |

*(Add your own screenshots if available)*

---

## 🛡️ Security Notes

- Do not commit `local.settings.json` or real API keys.
- Use Azure Static Web App **Configuration** for secret management.

---

## 🧠 Built With

- [Azure OpenAI](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/)
- [Azure AI Search](https://learn.microsoft.com/en-us/azure/search/)
- [Azure Speech + Avatars](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/)
- [Azure Static Web Apps](https://learn.microsoft.com/en-us/azure/static-web-apps/)
- [Azure Functions (Python)](https://learn.microsoft.com/en-us/azure/azure-functions/functions-reference-python)

---


