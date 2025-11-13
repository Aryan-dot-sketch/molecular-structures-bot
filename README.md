# 🧪 Molecular Structures Telegram Bot

A simple Telegram bot that sends interactive 3D molecular structure HTML files to users.

## 📋 Features

- ✨ Interactive inline keyboard with all compounds
- 📄 Sends HTML files directly to users
- 🔄 Pagination for easy browsing
- ⚡ Fast and lightweight
- 🎯 Simple one-repo, two-branch structure

## 🗂️ Repository Structure

```
Repository: molecular-structures-bot

Branch: main (Bot Code)
├── bot.py
├── compounds.json
├── requirements.txt
├── .env.example
├── .github/workflows/bot.yml
└── README.md

Branch: compounds (HTML Files)
├── CH4-methane.html
├── H2O-water.html
├── CO2-carbon-dioxide.html
└── ... (all your HTML files)
```

## 🚀 Quick Start

### 1. Create Telegram Bot

1. Open Telegram and search for [@BotFather](https://t.me/BotFather)
2. Send `/newbot` command
3. Follow instructions to create your bot
4. Copy the **Bot Token** (looks like: `123456789:ABCdefGHIjklMNOpqrsTUVwxyz`)

### 2. Setup GitHub Repository

#### Option A: Fork/Clone This Repo

```bash
git clone https://github.com/YOUR_USERNAME/molecular-structures-bot.git
cd molecular-structures-bot
```

#### Option B: Create New Repo

1. Create a new repository on GitHub
2. Upload all files from the `main` branch
3. Create a new branch called `compounds`
4. Upload all your HTML files to the `compounds` branch

### 3. Configure GitHub Secrets

Go to your repository → Settings → Secrets and variables → Actions → New repository secret

Add these secrets:

| Secret Name | Value | Example |
|------------|-------|---------|
| `BOT_TOKEN` | Your Telegram bot token | `123456789:ABCdefGHI...` |
| `GITHUB_USERNAME` | Your GitHub username | `john_doe` |
| `GITHUB_REPO` | Your repository name | `molecular-structures-bot` |

### 4. Add Compounds to JSON

Edit `compounds.json` and add your compounds:

```json
{
  "compounds": [
    {
      "formula": "CH4",
      "name": "Methane",
      "file": "CH4-methane.html"
    },
    {
      "formula": "H2O",
      "name": "Water",
      "file": "H2O-water.html"
    }
  ]
}
```

### 5. Upload HTML Files

1. Switch to `compounds` branch
2. Upload all your HTML files
3. Make sure filenames match exactly with `compounds.json`

### 6. Run Bot

#### For Testing (GitHub Actions):

1. Go to **Actions** tab in your repository
2. Click on **Run Telegram Bot** workflow
3. Click **Run workflow** → **Run workflow**
4. Bot will start running!

#### For Production (Railway):

1. Go to [Railway.app](https://railway.app)
2. Sign up with GitHub
3. Click **New Project** → **Deploy from GitHub repo**
4. Select your repository
5. Add environment variables:
   - `BOT_TOKEN`
   - `GITHUB_USERNAME`
   - `GITHUB_REPO`
6. Deploy! 🚀

## 🎮 Bot Commands

| Command | Description |
|---------|-------------|
| `/start` | Show welcome message and compound list |
| `/help` | Show help message |
| `/list` | Show all compounds |

## 📱 How Users Use It

1. User starts the bot with `/start`
2. Bot shows a list of compounds with inline buttons
3. User clicks on any compound (e.g., "CH4 - Methane")
4. Bot sends the HTML file
5. User downloads and opens in browser
6. Interactive 3D molecule appears! 🎉

## ➕ Adding New Compounds

### Step 1: Create HTML File

Create your 3D molecule HTML file (e.g., `C6H6-benzene.html`)

### Step 2: Upload to `compounds` Branch

```bash
git checkout compounds
git add C6H6-benzene.html
git commit -m "Add benzene molecule"
git push origin compounds
```

### Step 3: Update `compounds.json`

```bash
git checkout main
```

Edit `compounds.json`:

```json
{
  "formula": "C6H6",
  "name": "Benzene",
  "file": "C6H6-benzene.html"
}
```

```bash
git add compounds.json
git commit -m "Add benzene to compound list"
git push origin main
```

### Step 4: Done!

Bot automatically picks up the new compound! Users can now select it.

## 🛠️ Local Development

### Run Locally

1. Clone the repository
2. Create `.env` file (copy from `.env.example`)
3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Run the bot:

```bash
python bot.py
```

## 🐛 Troubleshooting

### Bot not responding?

- Check if Bot Token is correct
- Make sure GitHub secrets are set properly
- Check GitHub Actions logs for errors

### File not sending?

- Verify filename in `compounds.json` matches actual file
- Check if file exists in `compounds` branch
- Make sure file is accessible (not in subfolder)

### GitHub Actions timeout?

- Default timeout is 6 hours
- For 24/7 operation, use Railway or similar service

## 📊 File Naming Convention

Use this format for HTML files:

```
FORMULA-name.html
```

Examples:
- `CH4-methane.html` ✅
- `H2O-water.html` ✅
- `C6H12O6-glucose.html` ✅
- `methane.html` ❌ (missing formula)
- `CH4_Methane.html` ❌ (use hyphen, not underscore)

## 🔄 Migration from GitHub Actions to Railway

When ready for production:

1. Go to Railway.app
2. Import your GitHub repository
3. Add environment variables
4. Deploy
5. **Optional:** Disable GitHub Actions workflow

No code changes needed! Same code works on both platforms.

## 📝 License

MIT License - Feel free to use and modify!

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📧 Support

For issues or questions:
- Open an issue on GitHub
- Contact: [Your Contact Info]

## 🎉 Credits

Created with ❤️ for chemistry enthusiasts!

---

**⭐ If you find this useful, please star the repository!**
