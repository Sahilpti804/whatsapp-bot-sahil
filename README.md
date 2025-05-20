# WhatsApp Bot with ChatGPT Integration

A WhatsApp bot that uses OpenRouter API to provide AI-powered responses.

## Features
- Real-time message responses
- Sentiment analysis with emojis
- Automatic retry mechanism
- Friendly and engaging responses
- Group chat support
- Bot control commands

## Quick Deployment Guide (Fly.io)

### Step 1: Install Fly CLI
```bash
# For Windows (PowerShell)
iwr https://fly.io/install.ps1 -useb | iex

# For Mac
curl -L https://fly.io/install.sh | sh

# For Linux
curl -L https://fly.io/install.sh | sh
```

### Step 2: Sign Up and Login
1. Go to [fly.io](https://fly.io)
2. Sign up for a free account
3. Login via CLI:
```bash
fly auth signup  # If you haven't signed up
fly auth login   # If you already have an account
```

### Step 3: Deploy the Bot
1. **Initialize Fly App**
```bash
# Make sure you're in your project directory
fly launch
```
- Choose a unique app name
- Select "No" for PostgreSQL
- Select "No" for Redis
- Choose Singapore (sin) as region

2. **Set Environment Variables**
```bash
fly secrets set OPENROUTER_API_KEY="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"
fly secrets set NODE_ENV="production"
```

3. **Deploy the App**
```bash
fly deploy
```

4. **Check Logs for QR Code**
```bash
fly logs
```

### Step 4: Connect WhatsApp
1. Open WhatsApp on your phone
2. Go to Settings > Linked Devices
3. Tap "Link a Device"
4. Scan the QR code from Fly.io logs

### Step 5: Verify Deployment
1. **Check Status**
```bash
fly status
```

2. **Test the Bot**
- Send a message to your WhatsApp
- Bot should respond within seconds
- Try the command: `sahil bot stop`

### Common Issues & Solutions
1. **QR Code Not Showing**
```bash
fly logs
fly restart
```

2. **Bot Not Responding**
```bash
fly status
fly logs
```

3. **Connection Lost**
- Rescan QR code
- Check status: `fly status`

## Local Development
```bash
# Install dependencies
npm install

# Start the bot
npm start
```

## Bot Commands
- `sahil bot stop` - Deactivate the bot
- `sahil bot start done` - Reactivate the bot

## Fly.io Free Tier Benefits
- 3 shared-cpu-1x 256mb VMs
- 3GB persistent volume storage
- 160GB outbound data transfer
- Global edge network
- Automatic HTTPS
- Free subdomain

## Important Notes
- Keep your API keys secure
- Monitor Fly.io dashboard for usage
- Check logs if bot stops responding
- Rescan QR code if connection drops 

## Heroku Deployment

### Step 1: Install Heroku CLI
- Download from: https://devcenter.heroku.com/articles/heroku-cli
- Run the installer
- Open a new PowerShell window

### Step 2: Login to Heroku
```powershell
heroku login
```

### Step 3: Create Heroku App
```powershell
# Make sure you're in your project directory
cd "C:\Users\User\Desktop\WhatsApp Bot"

# Create Heroku app
heroku create whatsapp-bot-sahil

# Set environment variables
heroku config:set OPENROUTER_API_KEY="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"
heroku config:set NODE_ENV="production"
```

### Step 4: Deploy to Heroku
```powershell
# Initialize git if not already done
git init
git add .
git commit -m "Initial commit"

# Add Heroku remote
heroku git:remote -a whatsapp-bot-sahil

# Push to Heroku
git push heroku main
```

### Step 5: Check Logs for QR Code
```powershell
heroku logs --tail
```

### Step 6: Connect WhatsApp
- Open WhatsApp on your phone
- Go to Settings > Linked Devices
- Tap "Link a Device"
- Scan the QR code from Heroku logs

### Step 7: Verify Deployment
1. **Check Status**
```powershell
heroku status
```

2. **Test the Bot**
- Send a message to your WhatsApp
- Bot should respond within seconds
- Try the command: `sahil bot stop`

### Common Issues & Solutions
1. **QR Code Not Showing**
```powershell
heroku logs
heroku restart
```

2. **Bot Not Responding**
```powershell
heroku status
heroku logs
```

3. **Connection Lost**
- Rescan QR code
- Check status: `heroku status`

## Local Development
```bash
# Install dependencies
npm install

# Start the bot
npm start
```

## Bot Commands
- `sahil bot stop` - Deactivate the bot
- `sahil bot start done` - Reactivate the bot

## Heroku Free Tier Benefits
- 1 dyno (1x CPU, 512MB RAM)
- 500MB persistent volume storage
- 10,000 dyno hours per month
- Global edge network
- Automatic HTTPS
- Free subdomain

## Important Notes
- Keep your API keys secure
- Monitor Heroku dashboard for usage
- Check logs if bot stops responding
- Rescan QR code if connection drops 