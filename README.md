# Discord Badge Scraper

A small Rust CLI that connects to Discord’s Gateway over WebSockets and collects **user badges** (Partner, HypeSquad, Bug Hunter, Early Supporter, Bot Developer, etc.) from a server’s member list. Output is saved to `results.txt`.

## What it does

- Connects to Discord via WebSocket (Gateway v9) and requests the guild member list.
- Parses user **public flags** and maps them to badge names.
- Appends each user (username, ID, badges) to `results.txt` as they’re received.

## Setup & run

1. **Clone the repo**
   ```bash
   git clone https://github.com/stincgraiy/stincgraiy-scraper.git
   cd stincgraiy-scraper
   ```

2. **Install Rust** (if needed): [rust-lang.org/tools/install](https://www.rust-lang.org/tools/install)

3. **Add config**  
   In the project root, create `config.json`:
   ```json
   {
       "token": "YOUR_DISCORD_ACC_TOKEN",
       "guild_id": "TARGET_GUILD_ID",
       "channel_id": "A_TEXT_CHANNEL_ID_FROM_THE_GUILD"
   }
   ```
   Use your account token, the target server ID, and any text channel ID from that server.

4. **Run**
   ```bash
   cargo run --release
   ```

5. **Results**  
   Open `results.txt` for the scraped users and their badges.
