# poke-cli

A command-line interface to quickly select and stream Pokémon episodes directly from your terminal.

## Features

- **Interactive Selection:** Uses `fzf` to easily browse and select from all 9 Generations of Pokémon, organized by Season and Episode.
- **Resolution Control:** Choose your preferred video quality (360p, 480p, 720p, 1080p, etc., depending on availability).
- **History Tracking:** Automatically saves your progress to a `.hst` file. Resume exactly where you left off the next time you run the script!
- **Audio Fallback:** Tries to play English audio by default; if unavailable, it will automatically fall back to the Japanese audio track.
- **In-Player Navigation Menu:** After an episode finishes, a menu lets you easily:
  - Play the next or previous episode.
  - Replay the current episode.
  - Select an entirely new episode or change the resolution.
  - Quit.

## Dependencies

Make sure you have the following installed on your system:

- `bash` (v4.0 or higher is recommended)
- [`fzf`](https://github.com/junegunn/fzf): For the interactive fuzzy-finding selection menus.
- [`mpv`](https://mpv.io/): The media player used for streaming the video and audio tracks together.
- `curl`: Used by the script to check audio stream availability before playback.

## Installation & Usage

1. Clone or download the repository to your local machine.
2. Make the script executable:
   ```bash
   chmod +x poke-cli
   ```
3. Run the script:
   ```bash
   ./poke-cli
   ```
4. Follow the interactive `fzf` prompts to search and select your desired Pokémon generation, season, episode, and video resolution.

## How It Works

The script fetches HLS video streams from `pkflx.com`. It dynamically maps the video tracks with the corresponding audio tracks and relies on `mpv` to synchronize and play them. Progress is kept in an easy-to-read `.hst` file located in the same directory.
