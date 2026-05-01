## WordPress Docker Image with WP-CLI

This is a WordPress Docker environment for developing WordPress themes.

## Setup

1. Clone this repository and enter the folder
   ```bash
   git clone git@github.com:Clickadelic/sweat-off.git
   cd sweat-off
   ```
2. Copy the env template
   ```bash
   cp .env.template .env
   ```
3. Clone the theme repos into `themes/`
   ```bash
   git clone git@github.com:Clickadelic/sweat-off-base.git themes/sweat-off-theme
   git clone git@github.com:Clickadelic/sweat-off-by-hand.git themes/sweat-off-by-hand
   ```
4. Start the Docker environment
   ```bash
   docker-compose up -d
   ```
5. Open http://localhost:8080 and complete the WordPress install

## Theme development workflow

The `themes/` directory is gitignored in this repo — the two theme repos are fully independent.
Commit and push changes freely inside either theme folder without ever touching this repo.

```bash
cd themes/sweat-off-theme   # or sweat-off-by-hand
git add .
git commit -m "your message"
git push
```

This repo (`sweat-off`) only manages the Docker environment. Theme changes never affect it.
