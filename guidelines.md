[back-to-index](readme.md)

# Technical Guidelines

## Movement
You should base any movement in your intro screen off of something that isn't framerate dependant, such as the current time in milliseconds, or the amount of time that has passed since the last frame was rendered.

OBS can occasionally encounter stutters while encoding at high settings, and making your movement stay consistent through framerate dips can make it so viewers don't even notice something went wrong. In the far off future, streaming services may even start adding higher refresh rates, this would future-proof against that as well.

Here's an example using the time elapsed since the last frame:
```js

let lastFrame = Date.now();
function draw() { // Called once per frame

    // number of seconds since the last frame was drawn
    const delta = (Date.now() - lastFrame) / 1000;
    ...

    emote.position.x += delta * 10; 
    // `delta` will be a very small number, usually around 0.0166
    // you may need to multiply it to get the right movement speed

    ...
    lastFrame = Date.now();
}
```

## Performance
The expected use for most of these intro screens is that they will be ran inside of an OBS browser source, while OBS is encoding at up to 8000kbps, and you don't want to step on OBS's toes while it's encoding or else it will cause OBS to drop frames.

The templates on this GitHub account include a stats library which can be activated by adding `?stats=true` to the end of the URL of your page, it includes a readout in milliseconds of how long each frame takes to render. At 60FPS (which most streams run at, even if the streamer has a higher refresh rate monitor) your project should take less than 16 milliseconds (1000/60 = 16.66666666666667) to render.

Keep in mind that an OBS browser source can eat into your performance budget more than a seperate browser window while OBS is encoding, this is probably due to process priotization in Windows, but usually it doesn't diminish too much. The best way to test things out is to record a video in OBS (or just stream) your browser source at similar settings to what the stream will be running at.

# Visual Suggestions

The following are tips for "Intro screens" or "Break/BRB screens", meant to take up the full video feed.

An intro screen doesn't have to be the most impressive over-the-top visual animation that keeps 100% of the viewer's attention drawn to it. The streamer is supposed to be the main attraction after all. That said, as long as things don't look obnoxious, and won't trigger anyone's epilepsy, you can have a lot of movement going on at once without getting to the point of being overwhelming.

Most of the intro screens developed so far fall more into the "zen garden" category of a slow, subtle, and/or constant animation which viewers could watch for an hour without getting motion sick or bored.

## Stream alerts
Streamers may appreciate having a clear spot for things like subscriber alerts to pop up in, or at least a spot that won't frustrate viewers if your composition is engaging enough (I guess that's a good problem to have)

This could be a spot deliberately left clear of motion and detail, or you could distribute motion and detail across the whole screen, making alert popups not feel out of place.
