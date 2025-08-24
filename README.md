# PKT Reminder Bot

A simple chat-based reminder bot that connects a static **frontend (HTML/JS)** with an **n8n backend**.  
It extracts reminder details using an AI Agent and creates Google Calendar events in **Pakistan Standard Time (PKT, UTC+05:00)**.

---

## 🚀 Demo

- **Frontend (GitHub Pages):** https://<your-username>.github.io/pkt-reminder-bot/frontend/
- **n8n Production Webhook:** https://<your-n8n-subdomain>.app.n8n.cloud/webhook/chatbot  
- **n8n Test Webhook:** https://<your-n8n-subdomain>.app.n8n.cloud/webhook-test/chatbot  

---

## 📸 Screenshots

Frontend UI:
<img width="1919" height="867" alt="image" src="https://github.com/user-attachments/assets/d454f15e-9560-4447-b61b-bbf5ec71dc7d" />
<img width="1094" height="676" alt="image" src="https://github.com/user-attachments/assets/c6bf8cfe-0c5d-425d-b05e-059f85f8af32" />

n8n Workflow:
<img width="1167" height="439" alt="image" src="https://github.com/user-attachments/assets/184418ca-4ec2-4708-af9c-d6754b7ee1d3" />

---

## ⚙️ How it Works

1. User types a message in the chat UI (e.g. *"Set a reminder for Aug 24, 2025 from 10am–11am, Team meeting"*).
2. The frontend POSTs to an n8n Webhook.
3. The **AI Agent** parses the message and outputs JSON:
   ```json
   {
     "startTime": "2025-08-24T10:00:00+05:00",
     "endTime": "2025-08-24T11:00:00+05:00",
     "summary": "Team meeting"
   }
