# MoneyPrinterTurbo 💸</h1>

<p align="center">
  <a href="https://github.com/harry0703/MoneyPrinterTurbo/stargazers"><img src="https://img.shields.io/github/stars/harry0703/MoneyPrinterTurbo.svg?style=for-the-badge" alt="Stars"></a>
  <a href="https://github.com/harry0703/MoneyPrinterTurbo/issues"><img src="https://img.shields.io/github/issues/harry0703/MoneyPrinterTurbo.svg?style=for-the-badge" alt="Open Issues"></a>
  <a href="https://github.com/harry0703/MoneyPrinterTurbo/network/members"><img src="https://img.shields.io/github/forks/harry0703/MoneyPrinterTurbo.svg?style=for-the-badge" alt="Forks"></a>
  <a href="https://github.com/harry0703/MoneyPrinterTurbo/blob/main/LICENSE"><img src="https://img.shields.io/github/license/harry0703/MoneyPrinterTurbo.svg?style=for-the-badge" alt="License"></a>
</p>

<h3>English | <a href="./README-zh.md">简体中文</a></h3>

  <a href="https://trendshift.io/repositories/8731" target="_blank"><img src="https://trendshift.io/api/badge/repositories/8731" alt="Trendshift Badge" style="width: 250px; height: 55px;" width="250" height="55"/></a>

## Features 🚀

- **AI-Powered Script Generation**: Automatically creates video scripts from keywords
- **Multi-Source Material Integration**: Supports Pexels, Pixabay, and local files
- **Smart Editing**: Auto-adds subtitles, background music, and transitions
- **Multi-Platform Ready**: Outputs vertical (9:16) and horizontal (16:9) formats
- **Batch Processing**: Generates multiple variants simultaneously

## Quick Start 🛠️

```bash
# Clone repo
git clone https://github.com/harry0703/MoneyPrinterTurbo.git
cd MoneyPrinterTurbo

# Install dependencies
pip install -r requirements.txt

# Configure (edit before starting!)
cp config.example.toml config.toml
nano config.toml

# Launch WebUI
python -m webui
```

## Docker Deployment 🐳

```bash
docker-compose up
```

Access at: <http://localhost:8501>

## Configuration ⚙️

Essential `config.toml` settings:

```toml
[app]
llm_provider = "deepseek"  # Options: openai, moonshot, azure, deepseek
pexels_api_keys = ["your_pexels_key"] 
pixabay_api_keys = ["your_pixabay_key"]

[openai]
api_key = "sk-xxx"
base_url = "https://api.deepseek.com"
model_name = "deepseek-chat"
```

## Common Questions ❓

### Q: Getting "No ffmpeg exe found" error?

```bash
# Linux
sudo apt install ffmpeg imagemagick

# Mac
brew install ffmpeg imagemagick
```

### Q: How to use free GPT-3.5?

```bash
docker run -p 3040:3040 missuo/freegpt35
```

Then set in config.toml:

```toml
[openai]
base_url = "http://localhost:3040/v1/"
model_name = "gpt-3.5-turbo" 
```

## License 📄

MIT Licensed. See [LICENSE](/LICENSE) for details.

[![Star History Chart](https://api.star-history.com/svg?repos=harry0703/MoneyPrinterTurbo&type=Date)](https://star-history.com/#harry0703/MoneyPrinterTurbo&Date)

## Security Best Practices

1. Never commit sensitive files:
```bash
git update-index --assume-unchanged config.toml
```
2. Use environment variables for secrets:
```python
import os
API_KEY = os.getenv('PEXELS_API_KEY')
```
3. Rotate API keys quarterly
4. Enable 2FA on your GitHub account
