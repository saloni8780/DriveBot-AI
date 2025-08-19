# DriveBot-AI

A powerful chatbot built with n8n that allows you to manage your Google Drive files and generate AI-powered summaries directly from WhatsApp.

## Demo



---

## Features

- **List Files:** `LIST /FolderName` - See all files and folders in a directory.
- **Delete Files:** `DELETE /FolderName/FileName.pdf` - Delete a specific file.
- **Move Files:** `MOVE /SourceFolder/File.pdf /DestinationFolder` - Move a file to a new location.
- **Upload Files:** Attach a file directly in WhatsApp to upload it to a pre-configured folder.
- **Summarize Documents:** `SUMMARY /FolderName` - Get a concise, AI-generated summary for every document (PDF, TXT) in a folder.

---

## Tech Stack

- **Automation & Backend:** n8n 
- **Messaging Channel:** Twilio Sandbox for WhatsApp
- **File Storage:** Google Drive API
- **AI Summarization:** Google Vertex AI (Gemini) / OpenAI / Ollama
- **Local Tunneling (for development):** ngrok

---

## Setup & Installation

To run this project locally, you will need n8n, ngrok, and all necessary API credentials.

1.  **Prerequisites:**
    - n8n installed and running on your machine.
    - An ngrok account and authtoken installed.

2.  **Clone the Repository:**
    ```bash
    git clone https://github.com/saloni8780/DriveBot-AI.git
    cd DriveBot-AI
    ```

3.  **Set Up Credentials:**
    - In n8n, create new credentials for Google (Service Account), Twilio, and your chosen AI service using the `.env.sample` file as a guide for what is needed.

4.  **Import the Workflow:**
    - In the n8n canvas, import the `workflow.json` file.
    - Go through each relevant node (e.g., Google Drive, Twilio, AI nodes) and link it to the credentials you just created.

5.  **Run the Bot:**
    - Start a public tunnel to your n8n instance: `ngrok http 5678`
    - Copy the ngrok Forwarding URL and your n8n webhook path.
    - Paste the full URL into your Twilio Sandbox settings under "When a message comes in".
    - Activate your n8n workflow.

---

## How to Use

Connect your phone to the Twilio Sandbox and send commands directly in the WhatsApp chat.

- `LIST /ProjectX`
- `DELETE /ProjectX/Filename
- To upload, simply attach a document and send it.
- MOVE /ProjectX/Filename/Archive
- SUMMARY /ProjectX
