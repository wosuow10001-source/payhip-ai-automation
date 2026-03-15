# payhip-ai-automation
# 🚀 PayHip AI Automation System

**AI-powered automation to automatically generate and upload digital products to PayHip**

## ✨ Features

✅ **AI Content Generation**
- 🎵 Music Generation with Suno AI (lo-fi, hip-hop, ambient, etc.)
- 🖼️ Image Generation with Stability AI (product photos, thumbnails)
- 📚 Ebook Generation with GPT-4 (comprehensive guides, tutorials)

✅ **Automatic PayHip Upload**
- Playwright-based browser automation
- Auto-login to PayHip dashboard
- Instant product creation and publishing
- Metadata and pricing auto-configuration

✅ **Scheduling & Notifications**
- Daily/weekly automated generation
- Slack notifications on successful uploads
- Error logging and monitoring
- Dashboard tracking

## 🛠️ Installation

### Prerequisites
- Python 3.9+
- pip
- Node.js (optional, for n8n)

### Quick Start

```bash
# Clone the repository
git clone https://github.com/yourusername/payhip-ai-automation.git
cd payhip-ai-automation

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Setup environment variables
cp .env.example .env
# Edit .env with your API keys

# Run the automation
python main.py
```

## 📋 Configuration

Create a `.env` file:

```env
# PayHip Credentials
PAYHIP_EMAIL=your-email@example.com
PAYHIP_PASSWORD=your-password
PAYHIP_API_KEY=your-api-key

# AI Service Keys
SUNO_API_KEY=your-suno-key
STABILITY_API_KEY=your-stability-key
OPENAI_API_KEY=your-openai-key

# Notifications
SLACK_WEBHOOK_URL=https://hooks.slack.com/...

# Schedule
SCHEDULE_TIME=0 0 * * *  # Daily at midnight
```

## 🎯 Usage

### Manual Execution

```python
from payhip_automation import PayHipAutomation

automation = PayHipAutomation()

# Generate music
music = automation.generate_music_with_suno('lo-fi hip-hop')

# Generate image
image = automation.generate_image_with_stability('Professional product photo')

# Generate ebook
ebook = automation.generate_ebook_with_gpt('AI & Digital Marketing')

# Upload all to PayHip
automation.upload_product_to_payhip(music)
automation.upload_product_to_payhip(image)
automation.upload_product_to_payhip(ebook)
```

### Scheduled Automation

```python
automation.setup_schedule('0 0 * * *')  # Run daily at midnight
automation.run_daily_automation()
```

### Using n8n Workflow

Import the provided `workflow.json` to n8n for visual workflow management.

## 📊 Architecture

```
AI Content Generators
    ├─ Suno AI (Music)
    ├─ Stability AI (Images)
    └─ GPT-4 (Ebooks)
         ↓
    File Storage
    (Google Drive/Local)
         ↓
    PayHip Uploader
    (Playwright Automation)
         ↓
    PayHip Dashboard
         ↓
    Notifications (Slack/Email)
```

## 📁 Project Structure

```
payhip-ai-automation/
├── main.py                      # Main entry point
├── payhip_automation.py         # Core automation class
├── ai_generators.py             # AI content generation
├── payhip_uploader.py          # PayHip upload logic
├── scheduler.py                 # Scheduling logic
├── requirements.txt             # Dependencies
├── .env.example                 # Environment variables template
├── workflow.json                # n8n workflow export
├── README.md                    # This file
└── logs/
    └── payhip_automation.log    # Application logs
```

## 🔐 Security

- API keys are stored in `.env` file (never commit this!)
- Use environment variables for sensitive data
- Passwords are not logged
- Regular API key rotation recommended

## 📈 Pricing Generated Products

- Music: $4.99
- Images: $7.99
- Ebooks: $6.99

(Fully customizable in code)

## 🐛 Troubleshooting

### PayHip Login Fails
- Verify email and password in .env
- Check if 2FA is enabled (disable temporarily)
- Ensure PayHip account is active

### AI Generation Fails
- Verify API keys are correct
- Check API rate limits
- Ensure sufficient account credits

### File Upload Issues
- Check file size (max 5GB for PayHip)
- Verify file format is supported
- Check disk space

## 📊 Monitoring

Check `logs/payhip_automation.log` for detailed execution logs.

## 🤝 Contributing

Pull requests welcome! Please follow the code style and add tests.

## 📄 License

MIT License - feel free to use commercially

## 💡 Tips

- Start with small daily generation batches
- Monitor initial uploads manually
- Adjust pricing based on market feedback
- Use scheduled automation for passive income

## 📞 Support

For issues and questions, open a GitHub issue.

---

**Happy automating! 🎉**
