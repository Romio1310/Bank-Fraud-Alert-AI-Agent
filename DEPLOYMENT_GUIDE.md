# GitHub Deployment Guide

## Prerequisites
- Git installed on your system
- GitHub account
- Repository created: https://github.com/Romio1310/01VoiceAgent.git

## Step 1: Initialize Git (if not already done)
```bash
cd /Users/codname_gd/ten-days-of-voice-agents-2025
git init
```

## Step 2: Add Remote Repository
```bash
git remote add origin https://github.com/Romio1310/01VoiceAgent.git
```

## Step 3: Check What Will Be Committed
Before committing, verify that no sensitive files will be pushed:
```bash
git status
```

**✅ Make sure you DON'T see:**
- `.env.local` files
- Any files containing API keys
- `node_modules/` or `.venv/` directories

**✔️ You SHOULD see:**
- `.env.example` files (these are safe - they're templates without actual keys)
- Source code files
- Configuration files

## Step 4: Stage All Files
```bash
git add .
```

## Step 5: Commit Your Changes
```bash
git commit -m "Initial commit: Day 1 - Working voice agent with LiveKit, Murf TTS, Google Gemini, and Deepgram STT"
```

## Step 6: Push to GitHub
```bash
git branch -M main
git push -u origin main
```

If prompted for credentials, use your GitHub username and a **Personal Access Token** (not your password).

## Step 7: Verify on GitHub
1. Go to https://github.com/Romio1310/01VoiceAgent
2. Check that all files are there
3. **IMPORTANT:** Verify that `.env.local` files are NOT visible

## 🔒 Security Checklist
Before pushing, double-check:
- [ ] `.gitignore` files are in place (backend and frontend)
- [ ] `.env.local` files are NOT staged for commit
- [ ] API keys are NOT visible in any committed files
- [ ] Only `.env.example` files (without real keys) are included

## 📝 Setting Up for Others
When someone else clones your repo, they should:
1. Clone the repository
2. Copy `.env.example` to `.env.local` in both `backend/` and `frontend/`
3. Add their own API keys to the `.env.local` files
4. Follow the setup instructions in `README.md`

## 🚨 If You Accidentally Commit Sensitive Data
If you accidentally push API keys:
1. **Immediately revoke/regenerate all exposed API keys**
2. Remove the sensitive data from Git history
3. Force push the cleaned history

Never leave exposed API keys active, even if you remove them from Git!
