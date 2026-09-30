# Forest Frenzy

Forest Frenzy is a real-time 8-bit bluffing party game for 2–8 players. Players create a room, share its four-character invite code, roll a secret forest attack, then tell the truth or bluff. Targets can call the bluff or spend a shield.

## Upload to GitHub

Upload the project files and folders in this repository to your GitHub repository. Keep the root-level `package.json`, `package-lock.json`, and `netlify.toml`, along with the `public/`, `netlify/`, and `scripts/` folders. Local dependencies, caches, scratch files, and the generated Netlify ZIP are excluded by `.gitignore`.

## Deploy from GitHub to Netlify

In Netlify, choose **Add new site → Import an existing project**, select the GitHub repository, and deploy. Netlify uses the included `netlify.toml` to run `npm run build`, publish `public/`, and build the function in `netlify/functions/`.

The room API runs at `/.netlify/functions/game`. Room state is stored in the site-wide `forest-frenzy-rooms` Netlify Blobs store with strong consistency and conditional writes. A room closes when its last human player leaves.

## Project files

- `public/` — the game UI, artwork, and browser code.
- `netlify/functions/game.ts` — the Netlify Function endpoint.
- `netlify/game-handler.ts` and `netlify/game-logic.ts` — server helpers kept outside the functions directory.
- `netlify.toml` — publish directory, build command, and function settings.
- `scripts/` — production-source compilation and the three-round game check.
