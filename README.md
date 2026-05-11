# Discord Account Humanizer

A high-performance Discord account humanizer script that updates accounts' profiles (display names, bios, pronouns, avatars, and HypeSquad) using a multi-threaded approach with proxy support.

## Setup

1. **Install Dependencies:**
   Ensure you have Python 3.10+ installed, then run:
   ```bash
   pip install -r requirements.txt
   ```

2. **Configuration:**
   Update `config.json` with your desired settings:
   - `max_threads`: Number of simultaneous accounts to process.
   - `update_display_name`, `update_bio`, etc.: Choose which fields to update.

3. **Input Data:**
   The script expects the following directory structure:
   - `input/tokens.txt`: Discord tokens (one per line).
   - `input/proxies.txt`: Proxies (one per line).
   - `input/success.txt`: Successfully processed tokens.
   - `input/failed.txt`: Failed tokens.
   - `data/names.txt`: Potential display names (one per line).
   - `data/bios.txt`: Potential bios (one per line).
   - `data/pronouns.txt`: Potential pronouns (one per line).
   - `avatar/`: Place avatar images here.
   - `banners/`: Place profile banners here (Nitro only).

## Usage

Run the script:
```bash
python humanizer.py
```

## Features
- **High Performance:** Rust-powered HTTP client (`primp`) for speed.
- **Proxy Support:** Integrated proxy rotations and automatic bad proxy removal.
- **Concurrent Execution:** Multi-threaded processing for tokens.
- **Retry Logic:** Intelligent retries on transient errors and proxy failures.
- **Real-Time Logging:** Beautifully formatted console logs with `colorama`.
- **HypeSquad Selection:** Randomly assigns a HypeSquad house.
- **Avatar Optimization:** Automatically resizes and compresses avatars to fit Discord's 1MB limit.
