# EDA--Edge-Data-Analysis-

# 🌐 Edge Data Analytics — Text Sentiment Analysis using Azure

## 🧠 Overview
This project demonstrates how to use **Microsoft Azure Cognitive Services (Text Analytics API)** to perform **Sentiment Analysis** on a given text file.  
It reads the input text, analyzes emotional tone (Positive, Neutral, or Negative), and saves the results to a new output file.  
The solution is designed for **Edge Data Analytics**, enabling real-time sentiment detection at the network edge using cloud-powered intelligence.

---

## ⚙️ Features
- 🔍 Perform sentiment analysis on raw text data.
- ☁️ Integrates with **Azure Cognitive Services – Text Analytics API**.
- 🧩 Supports **batch processing** for multiple text entries.
- 💾 Saves processed results (with sentiment scores) to a local file.
- ⚡ Lightweight and edge-deployable for IoT/AI Edge applications.

---

## 🧰 Tech Stack
| Component | Technology |
|------------|-------------|
| Cloud Service | Microsoft Azure Cognitive Services |
| Language | Python 3.8+ |
| SDK | `azure-ai-textanalytics` |
| Deployment | Azure Edge / Local Environment |

---

Install dependencies

pip install azure-ai-textanalytics


Set up Azure credentials

export AZURE_LANGUAGE_KEY="your_azure_key"
export AZURE_LANGUAGE_ENDPOINT="your_endpoint_url"

🧩 Usage

Place your input text file (e.g., input.txt) in the project directory.

Run the script:

python sentiment_analysis.py


The results will be saved in output_results.txt, showing each line’s sentiment as:

Text: "I love AI development!"
Sentiment: Positive (Confidence: 0.98)

🧠 Sample Code
from azure.ai.textanalytics import TextAnalyticsClient
from azure.core.credentials import AzureKeyCredential

key = "your_azure_key"
endpoint = "your_endpoint_url"

client = TextAnalyticsClient(endpoint=endpoint, credential=AzureKeyCredential(key))

with open("input.txt", "r") as file:
    lines = file.readlines()

result = client.analyze_sentiment(documents=lines)

with open("output_results.txt", "w") as output:
    for idx, doc in enumerate(result):
        output.write(f"Text: {lines[idx].strip()}\nSentiment: {doc.sentiment}\n\n")

print("✅ Sentiment analysis completed successfully!")

📊 Example Output
Text: AI is the future of innovation.
Sentiment: Positive (Confidence: 0.97)

Text: The system crashed multiple times.
Sentiment: Negative (Confidence: 0.89)

🚀 Future Enhancements

Integrate Azure Stream Analytics for real-time edge inference.

Add data visualization dashboards using Power BI.

Deploy model as a containerized service on Azure IoT Edge.

👨‍💻 Author

Tanmay Sandip Khedekar
B.Tech in Computer Science (AI & Edge Computing)
📍 Pune, India
🔗 LinkedIn
 | GitHub
