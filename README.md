# Pinch the Bug

A browser-based game that uses your webcam to track your hand movements. Point at bugs crawling across the screen and hold your finger on them to squash them!

## How to Play

1. Open `index.html` in a modern browser (Chrome, Firefox, or Edge recommended)
2. Allow camera access when prompted
3. Adjust the tracking smoothness slider if needed
4. Click "Start Game" and read the instructions
5. Point your index finger at bugs and hold to squash them
6. Score as many points as possible before time runs out!

## Features

- **Hand Tracking**: Uses MediaPipe Hands for real-time finger tracking via webcam
- **Dwell-to-Kill Mechanic**: Hold your finger on a bug to squash it - a progress ring shows your progress
- **Multiple Bug Types**: Different bugs with varying sizes, speeds, and point values
- **Leaderboard**: Scores are saved to a Supabase backend
- **Visual Feedback**: Animated bugs, squash effects, and floating point popups
- **Calibration**: Adjustable tracking smoothness for different lighting conditions

## Bug Types

| Bug | Size | Speed | Points | Dwell Time |
|-----|------|-------|--------|------------|
| Normal | Medium | Slow | 10 | 400ms |
| Fast | Small | Fast | 25 | 300ms |
| Tiny | Tiny | Medium | 30 | 350ms |
| Big | Large | Very Slow | 5 | 500ms |
| Boss | Huge | Medium | 50 | 600ms |

## Technologies

- **MediaPipe Hands** - Hand landmark detection
- **HTML5 Canvas** - Game rendering
- **Supabase** - Leaderboard backend
- **Vanilla JavaScript** - No frameworks required

## Requirements

- Modern web browser with WebGL support
- Webcam
- Desktop/laptop computer (mobile not supported)

## Local Development

Simply open `index.html` in a browser. No build process required.

For the leaderboard to work, you'll need to set up a Supabase project with a `leaderboard` table:

```sql
create table leaderboard (
  id uuid default gen_random_uuid() primary key,
  player_name text not null,
  score integer not null,
  created_at timestamp with time zone default now()
);
```

## License

MIT

## Author

[Samir Madhavan](https://www.samirmadhavan.com)
