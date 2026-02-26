# Social Casino Games - Setup Guide

## Repository Structure

Upload the following to your GitHub repository:

```
social-casino-games/
├── images/                    # All 382 game cover images (.webp)
│   ├── 15-crystal-roses--a-tale-of-love.webp
│   ├── 24k-dragon.webp
│   ├── ... (382 files total)
│   └── zz-top-roadside-riches.webp
├── games.json                 # Full JSON with all game data (formatted)
├── games.min.json             # Minified JSON (smaller file size)
└── README.md                  # This file
```

## Quick Setup

### Step 1: Clone your repository
```bash
git clone https://github.com/ArenaEntertainment/social-casino-games.git
cd social-casino-games
```

### Step 2: Create images folder and copy images
```bash
mkdir -p images
# Copy all .webp files from GAMESCOVERS folder to images/
cp /path/to/GAMESCOVERS/*.webp images/
```

### Step 3: Copy JSON files
```bash
# Copy games.json and games.min.json to the root
```

### Step 4: Push to GitHub
```bash
git add .
git commit -m "Add game covers and JSON data"
git push origin main
```

## JSON Structure

```json
{
  "totalGames": 382,
  "games": [
    {
      "id": 1,
      "name": "Game Name",
      "image": "https://raw.githubusercontent.com/ArenaEntertainment/social-casino-games/main/images/game-name.webp",
      "iframeUrl": "https://asccw.playngonetwork.com/casino/ContainerLauncher?..."
    }
  ]
}
```

## Usage Examples

### Fetch JSON in JavaScript
```javascript
fetch('https://raw.githubusercontent.com/ArenaEntertainment/social-casino-games/main/games.json')
  .then(response => response.json())
  .then(data => {
    console.log(`Total games: ${data.totalGames}`);
    data.games.forEach(game => {
      console.log(game.name, game.image, game.iframeUrl);
    });
  });
```

### Display Game in iframe
```html
<img src="https://raw.githubusercontent.com/ArenaEntertainment/social-casino-games/main/images/fire-joker.webp" alt="Fire Joker">
<iframe src="https://asccw.playngonetwork.com/casino/ContainerLauncher?pid=2&gid=firejoker&lang=en_GB&practice=1&channel=desktop&demo=2" 
        width="800" height="600" frameborder="0"></iframe>
```

## Public URLs

Once uploaded, your files will be accessible at:

- **JSON (formatted):** `https://raw.githubusercontent.com/ArenaEntertainment/social-casino-games/main/games.json`
- **JSON (minified):** `https://raw.githubusercontent.com/ArenaEntertainment/social-casino-games/main/games.min.json`
- **Images:** `https://raw.githubusercontent.com/ArenaEntertainment/social-casino-games/main/images/{filename}.webp`

## File Sizes

- `games.json`: ~145 KB (formatted, human-readable)
- `games.min.json`: ~115 KB (minified, for production)
- Images folder: ~10 MB total (382 .webp files)
