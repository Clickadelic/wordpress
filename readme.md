## WordPress Docker Image with WP-CLI

This is a WordPress Docker environment for developing WordPress themes.

## Setup

1. Clone this repository **with submodules** and enter the folder
   ```bash
   git clone --recurse-submodules git@github.com:Clickadelic/sweat-off.git
   cd sweat-off
   ```
   If you already cloned without `--recurse-submodules`, initialize them manually:
   ```bash
   git submodule update --init
   ```
2. Copy the env template
   ```bash
   cp .env.template .env
   ```
3. Start the Docker environment
   ```bash
   docker-compose up -d
   ```
4. Open http://localhost:8080 and complete the WordPress install

## Theme submodules

The theme repos are registered as git submodules with `ignore = all`, meaning **changes inside the theme folders never produce diffs in this repo**. You can commit and push freely inside any theme without touching this repo.

| Submodule | Path |
|---|---|
| sweat-off-parent | `themes/sweat-off-parent` |
| sweat-off-child | `themes/sweat-off-child` |
| sweat-off-by-hand | `themes/sweat-off-by-hand` |

### Working on themes

```bash
cd themes/sweat-off-parent   # or any other theme
git add .
git commit -m "your message"
git push
```

### Adding a new theme submodule

```bash
git submodule add git@github.com:Clickadelic/<repo-name>.git themes/<repo-name>
git config -f .gitmodules submodule.themes/<repo-name>.ignore all
```

Then whitelist the path in `.gitignore`:
```
!themes/<repo-name>
```
