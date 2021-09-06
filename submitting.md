## Performance
The expected use for most of these intro screens is that they will be ran inside of an OBS browser source, while OBS is encoding at up to 8000kbps, and you don't want to step on OBS's toes while it's encoding or else it will cause OBS to drop frames.

## Testing
The most accurate way for you to test if your intro screen performs well is to load it into OBS as a browser source yourself, and set your encoding settings to the following:
- Bitrate: 8000kbps
- Encoder: Software (x264)
- Encoder Preset: Slow

*These are the settings [moonmoon](https://twitch.tv/moonmoon) uses as of July 2021.*

After your settings are dialed in, switch to the scene with your intro screen as a browser source, hit "Start Recording", and see if OBS drops any frames. Moonmoon also has a Ryzen 5950x and a 3090, so if you get a framerate of around 50FPS on a non god-tier CPU like that, you're probably good to go.

## Submitting
You will need to be a subscriber to [moonmoon on twitch](https://twitch.tv/moonmoon) and be in his subscriber only discord, once there you can ask about who you'll need to reach out to in #programming or #game_dev to see who's available to get you set up. At that point your intro screen will be reviewed by other users, they might have some performance, visual, or otherwise stream appropriateness feedback, as well as get you started with the next steps.

We'd prefer to have the repository for your intro screen hosted on this account so that we can spin up a netlify site from it, but don't worry, you'll still be able to easilly make changes. Once the site is live, a new `.md` file can be created in the [whitelist repository], which will then cause the intro screen to pop up in moons OBS next time he opens it.

Once the intro screen is added to the whitelist, the community aspect will be complete, and you can reach out to moon in discord DMs all "i made this :)" like, and if he's happy with the result he'll pay you appropriately.
