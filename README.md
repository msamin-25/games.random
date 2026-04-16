# games.random

Build your dream game with AI, then learn how it works--one line at a time.

An AI-powered game development platform that generates complete, playable games in seconds, 
then teaches you programming through interactive code exploration. Watch your code come alive 
with real-time highlighting, AI assistance, and educational features.

## What Is This?

games.random is an educational platform that makes game programming accessible. You describe 
a game in plain English, and AI generates fully functional code. Then you can modify it, 
learn from it, and understand how it works through live highlighting and explanations.

The goal is simple: turn curiosity into coding skills by letting you play with real, 
working games while learning the patterns that make them tick.

## Features

### AI Generation
- Describe your game in natural language
- Get complete, functional code in seconds
- Supports p5.js and Phaser game engines
- Clean, readable, well-structured code

### Educational Tools
- Live code highlighting shows function execution in real-time
- Interactive tooltips explain programming patterns on hover
- Event filtering to focus on specific game mechanics
- Automatic documentation of your game's architecture
- Flow visualization shows execution paths

### Code Editor
- Monaco editor (same as VS Code)
- Syntax highlighting with customizable themes
- Live editing with instant preview
- Import custom editor themes

### AI Assistant
- Chat interface for questions and modifications
- Natural language commands: "add more enemies", "make it harder"
- Code explanations and pattern recognition
- One-click feature additions

### Export
- Download as JavaScript file
- Export as standalone HTML (shareable, no dependencies)
- Copy to clipboard
- Reset to original at any time

## Installation

### Requirements
- Node.js 18 or higher
- Anthropic API key
- MongoDB instance
- Google OAuth credentials

### Setup

Clone and install:

```bash
git clone https://github.com/Shayan-Mazahir/games-random.git
cd games-random
npm install
```

Create `.env` file:

```env
PORT=3000
ANTHROPIC_API_KEY=your_key_here
MONGODB_URI=mongodb://localhost:27017/games-random
GOOGLE_CLIENT_ID=your_client_id
GOOGLE_CLIENT_SECRET=your_client_secret
SESSION_SECRET=random_string_here
```

Start server:

```bash
npm run dev
```

## Getting API Keys

### Anthropic API
- Sign up at console.anthropic.com
- Create API key under settings

### Google OAuth
- Go to console.cloud.google.com
- Create project, enable Google+ API
- Create OAuth credentials
- Add redirect URI: `http://localhost:3000/auth/google/callback`

### MongoDB
- Local: Install MongoDB Community Edition
- Cloud: Free tier at mongodb.com/cloud/atlas

## Architecture

Directory structure:

```
games-random/
├── back-end/server/
│   ├── main.js       # AI generation logic
│   └── server.js     # Express API
├── front-end/public/
│   ├── index.html    # Landing/generator
│   ├── play.html     # Editor interface
│   └── styles.css    # Styles
└── package.json
```

Flow:

```
User Input → Claude API → Code Generation → Monaco Editor → Live Game
```

Code is instrumented to trigger highlights when functions execute.
AI assistant can modify code through natural language commands.

## Tech Stack

**Frontend:** Monaco Editor, p5.js, Phaser, Mermaid.js, vanilla JavaScript

**Backend:** Node.js, Express, MongoDB, Mongoose, Passport.js

**AI:** Claude Sonnet 4.5 with prompt caching (90% cost reduction)

## How Live Highlighting Works

Game functions are wrapped to trigger highlights:

```javascript
// Original
function collectCoin() {
    score += 10;
}

// Wrapped (automatic)
function collectCoin() {
    highlightCodeFunction('collectCoin', 3000);
    return _original_collectCoin.apply(this, arguments);
}
```

When `collectCoin()` runs, the editor highlights that line for 3 seconds.

## Performance

- Generation: 3-8 seconds average
- Prompt caching: 90% cost reduction on repeats
- Highlight latency: <50ms
- Typical code size: 50-500 lines

## Contributing

Bug reports and pull requests welcome on GitHub.

### Development Process
1. Fork the repo
2. Create feature branch: `git checkout -b feature-name`
3. Commit: `git commit -m 'Add feature'`
4. Push: `git push origin feature-name`
5. Open pull request

### Code Style
- Use meaningful variable names
- Add comments for complex logic
- Follow existing patterns
- Test before submitting

### Future Refactoring Needed
- Split play.html into modules
- Extract CSS to separate files
- Add TypeScript definitions
- Unit tests
- Add mobile support

## Known Issues

- Doesn't work on mobile
- Needs better rate limiter
- Highlighting issues
- Some other minor bugs (non-performance issues)

See GitHub Issues for complete list (coming soon).

## License

GPL-3.0 or later. See LICENSE file.

This means you can use, modify, and distribute this code, even commercially,
but you must open-source any modifications under the same license.

## Credits

**Team:**
- [Mohammad Samin](https://github.com/msamin-25) - (Front-End & Backend)
- [Shayan Mazahir](https://github.com/Shayan-Mazahir) - (Back-end)
- [Rayyan Moosani](https://github.com/Muhammad-Rayyan-Moosani) - (Back-End)

**Built with:** Claude AI, Monaco Editor, p5.js, Phaser, Mermaid

**Inspired by:** Khan Academy's interactive learning, CodePen's instant preview, Scratch's educational approach and much much more

## Contact

- GitHub: https://github.com/Shayan-Mazahir/games-random
- Issues: https://github.com/Shayan-Mazahir/games-random/issues

---
