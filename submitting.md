## Performance
The expected use for most of these intro screens is that they will be ran inside of an OBS browser source, while OBS is encoding at up to 8000kbps, and you don't want to step on OBS's toes while it's encoding or else it will cause OBS to drop frames.

## Testing
The most accurate way for you to test if your intro screen performs well is to load it into OBS as a browser source yourself, and set your encoding settings to the following:
- Bitrate: 8000kbps
- Encoder: Software (x264)
- Encoder Preset: Slow

*These are the settings [moonmoon](https://twitch.tv/moonmoon) uses as of July 2021.*

After your settings are dialed in, switch to the scene with your intro screen as a browser source, hit "Start Recording", and see if OBS drops any frames. Moonmoon also has a Ryzen 5950x and a 3090, so if you get a framerate of around 50FPS on a non god-tier CPU like that, you're probably good to go.
