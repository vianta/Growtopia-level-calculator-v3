# Calculator Bot v3

> A powerful Discord bot for XP calculations, level progression tracking, and economy management.

**Created by wendos**

[![Discord.js](https://img.shields.io/badge/discord.js-v14-blue.svg)](https://discord.js.org/)
[![Node.js](https://img.shields.io/badge/node.js-v16+-green.svg)](https://nodejs.org/)
[![License](https://img.shields.io/badge/license-MIT-orange.svg)](LICENSE)

---

## Overview

Calculator Bot v3 is a comprehensive Discord bot designed for servers with level-based progression systems. It provides intelligent XP pack recommendations, cost optimization strategies, and complete economy management tools.

### Key Features

- **Smart XP Calculator** - Calculate exact XP requirements between any two levels
- **Strategy Optimizer** - Get 3 different strategies: Cheapest, Fastest, and Balanced
- **Visual Progress Bar** - Track your progression with custom emoji indicators
- **Favorites System** - Save frequently used calculations for quick access
- **History Tracking** - View your last 5 calculations
- **Interactive UI** - Dropdown menus and buttons for seamless navigation
- **User Access Control** - Only you can interact with your own calculations
- **Premium System** - Role-based unlimited access for admins and VIPs
- **Seed Distribution** - Admin tools for jar/seed economy management
- **Comprehensive Logging** - All transactions logged to dedicated channels

---

## What's New in v3

### Planned Features

*Share your planned features here and I'll add them to the README*

- [ ] Feature 1
- [ ] Feature 2
- [ ] Feature 3

---

## Screenshots

### Calculator with Custom Banner
![Calculator Example](https://i.imgur.com/s3CLujb.png)
*Modern calculator interface with custom banner, separators, and colorful XP display*

### Features Showcase
- ✨ **Custom Banner Support** - Add your own branded banner image
- 🎨 **Visual Separators** - Clean dividers between sections
- 🌈 **Colorful XP Display** - Rainbow-colored XP numbers in ANSI format
- 📊 **Strategy Dropdown** - Easy navigation between 4 different strategies
- 💾 **Save & History** - Save favorites and view calculation history
- ⚙️ **Custom Strategy Builder** - Create your own pack combinations

---

## Installation

### Prerequisites

- Node.js v16.9.0 or higher
- npm or yarn
- Discord Bot Token
- Discord Server with Administrator permissions

### Quick Start

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd calculator-bot
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure the bot**
   ```bash
   # Copy the example config
   cp config.example.js config.js
   
   # Edit config.js with your values
   ```

4. **Deploy slash commands**
   ```bash
   # For testing (instant, guild-only)
   node deploy-guild-commands.js
   
   # For production (global, takes up to 1 hour)
   node deploy-commands.js
   ```

5. **Start the bot**
   ```bash
   # Windows
   start.bat
   
   # Linux/Mac
   ./start.sh
   
   # Or directly
   node index.js
   ```

---

## Configuration

### Required Settings

Edit `config.js` with your Discord IDs:

```javascript
{
  "token": "YOUR_BOT_TOKEN",              // Bot token from Discord Developer Portal
  "clientId": "YOUR_CLIENT_ID",           // Application ID
  "guildId": "YOUR_GUILD_ID",             // Your server ID
  "CALCULATOR_CHANNEL_ID": "CHANNEL_ID",  // Channel where bot works
  "OWNER_ID": ["YOUR_USER_ID"],           // Bot owner(s)
  "ADMIN_ROLE": "ROLE_ID",                // Admin role ID
  "WEEKLY_ADMIN_ROLE": "ROLE_ID",         // Weekly admin role ID
  "WORLD_ADMIN_ROLE": "ROLE_ID",          // World admin role ID
  "JAR_LOG_CHANNEL": "CHANNEL_ID"         // Transaction log channel
}
```

### XP Pack Prices

Customize XP pack prices to match your server economy:

```javascript
"XP_PACK_PRICES": {
  "SMALL_125K": 700,    // 125,000 XP = 700 jars
  "BIG_250K": 1100,     // 250,000 XP = 1,100 jars
  "HUGE_500K": 1600,    // 500,000 XP = 1,600 jars
  "SUPREME_1M": 3000    // 1,000,000 XP = 3,000 jars
}
```

### Seed System Settings

Configure multipliers and limits:

```javascript
"SEED_SETTINGS": {
  "MULTIPLIERS": {
    "OWNER": 50,         // Owner multiplier
    "WEEKLY_ADMIN": 42,  // Weekly admin multiplier
    "ADMIN": 40          // Admin multiplier
  },
  "LIMITS": {
    "DAILY_JAR_LIMIT": 50000,      // Daily jar distribution limit
    "WEEKLY_JAR_LIMIT": 500000,    // Weekly jar distribution limit
    "COOLDOWN_MINUTES": 2          // Cooldown between commands
  },
  "TAX": {
    "FOOD_TAX_PERCENTAGE": 30      // Tax on food purchases
  }
}
```

---

## Commands

### User Commands

#### `/calculator`
Opens the interactive XP calculator panel.

**Features:**
- Calculate XP needed between any two levels (1-125)
- View 3 optimized strategies
- Save favorite calculations
- View calculation history
- Switch strategies with dropdown menu
- Visual progress indicator

**Usage:**
1. Run `/calculator`
2. Enter current level and target level
3. Browse strategies using buttons or dropdown
4. Save favorites for quick access later

---

### Admin Commands

#### `/jar-calc`
Advanced jar calculator for seed distribution.

**Permissions:** Admin, Weekly Admin, World Admin, Owner

**Features:**
- Calculate seed rewards based on jar contributions
- Track food sales (Gingerbread Cookie, Coconut Tart)
- Automatic tax calculation
- Role-based multipliers
- Comprehensive logging

#### `/seed-settings`
Configure seed system settings.

**Permissions:** Owner only

**Features:**
- Adjust role multipliers
- Set daily/weekly limits
- Configure cooldown periods
- Update food prices and tax rates
- Test settings before applying

#### `/cleanup`
Manage slash commands.

**Permissions:** Owner only

**Subcommands:**
- `list` - List all registered commands
- `clear-global` - Remove all global commands
- `clear-guild` - Remove all guild commands

---

## Strategy Types

### Cheapest Strategy
- Minimizes total cost
- Uses optimal pack combinations
- Best for budget-conscious users
- May require more packs

### Fastest Strategy
- Minimizes number of packs
- Uses largest packs available
- Slightly more expensive
- Quickest to apply

### Balanced Strategy
- Middle ground between cost and speed
- Uses medium-sized packs
- Recommended for most users
- Good value for money

---

## Premium System

### Free Users
- 3 calculations per day
- Full access to all features
- History and favorites included
- Resets daily at 00:00 UTC

### Premium Users
- Unlimited calculations
- No daily limits
- Priority support
- Same great features

**How to get Premium:**
Contact server admins or owners to receive premium access.

---

## Database

The bot uses SQLite to store:
- User favorites
- Calculation history
- Seed transaction logs
- Jar balances
- Usage statistics

**Database file:** `json.sqlite`

**Important:** Backup this file regularly to prevent data loss.

---

## Security

### Critical Security Rules

- **NEVER** commit `config.js` to GitHub
- **NEVER** share your bot token
- **ALWAYS** use `.gitignore` to exclude sensitive files
- **ONLY** share `config.example.js` publicly

### If Your Token Leaks

1. Go to [Discord Developer Portal](https://discord.com/developers/applications)
2. Select your application
3. Go to "Bot" section
4. Click "Regenerate" to get a new token
5. Update your `config.js` with the new token
6. Restart the bot

---

## Troubleshooting

### Bot is offline

**Possible causes:**
- Invalid token in `config.js`
- Bot not added to server
- Missing intents in Developer Portal

**Solution:**
1. Verify token is correct
2. Check bot is in your server
3. Enable these intents in Developer Portal:
   - Presence Intent
   - Server Members Intent
   - Message Content Intent

### Slash commands not showing

**Possible causes:**
- Commands not deployed
- Missing `applications.commands` permission
- Commands still propagating (global commands take up to 1 hour)

**Solution:**
```bash
# Use guild commands for instant deployment
node deploy-guild-commands.js
```

### Buttons not working

**Possible causes:**
- Missing bot permissions
- Trying to use someone else's calculation
- Event handler not loaded

**Solution:**
1. Grant bot these permissions:
   - Send Messages
   - Embed Links
   - Use External Emojis
2. Use your own `/calculator` command
3. Check console for errors

### "Access Denied" error

This is a feature, not a bug! You can only interact with your own calculations.

**Solution:** Run `/calculator` yourself to create your own calculation panel.

---

## Contributing

Contributions are welcome! Here's how you can help:

### Ways to Contribute

- Report bugs
- Suggest new features
- Improve documentation
- Submit pull requests
- Add translations
- Optimize performance

### Development Workflow

1. Fork the repository
2. Create a feature branch
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. Make your changes
4. Test thoroughly
5. Commit with clear messages
   ```bash
   git commit -m "Add amazing feature"
   ```
6. Push to your fork
   ```bash
   git push origin feature/amazing-feature
   ```
7. Open a Pull Request

### Code Standards

- Write clean, readable code
- Add comments for complex logic
- Follow existing code style
- Test your changes
- Update documentation

---

## Support

Need help? Here's how to get support:

- **Discord:** wendos
- **GitHub Issues:** Open an issue in this repository
- **Pull Requests:** Contributions welcome!

---

## Changelog

### v3.0.0 (Upcoming)
- *Features to be announced*

### v2.0.0
- Added favorites system
- Added calculation history
- Added dropdown strategy selector
- Added visual progress bar
- Added user access control
- Improved UI with Components v2
- Enhanced logging system

### v1.0.0
- Initial release
- Basic XP calculator
- 3 strategy types
- Seed distribution system
- Admin tools

---

## Roadmap

### Planned Features

- [ ] Statistics dashboard
- [ ] Leaderboard system
- [ ] Automatic backup system
- [ ] Web dashboard
- [ ] Multi-language support
- [ ] Custom strategy builder
- [ ] XP history tracking
- [ ] Notification system

Have a suggestion? Open an issue!

---

## License

MIT License - Feel free to use, modify, and distribute.

**What this means:**
- ✅ Commercial use allowed
- ✅ Modification allowed
- ✅ Distribution allowed
- ✅ Private use allowed
- ⚠️ No warranty provided
- ⚠️ License and copyright notice must be included

---

## Credits

**Created by wendos**

Special thanks to:
- Discord.js team for the amazing library
- All users who provided feedback
- Contributors who helped improve the bot

---

## Stats

![GitHub stars](https://img.shields.io/github/stars/yourusername/calculator-bot?style=social)
![GitHub forks](https://img.shields.io/github/forks/yourusername/calculator-bot?style=social)
![GitHub issues](https://img.shields.io/github/issues/yourusername/calculator-bot)

---

<div align="center">

**⭐ Star this repo if you find it useful! ⭐**

Made with ❤️ by **wendos**

*"Started with 'I'm tired of calculating', ended up here."*

</div>
