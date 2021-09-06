# Intro Screen Guidelines
Some things to keep in mind when creating an [intro screen](README.md)

# Visual Suggestions

An intro screen doesn't have to be the most impressive over-the-top visual animation that keeps 100% of the viewer's attention drawn to it. The streamer is supposed to be the main attraction after all. That said, as long as things don't look obnoxious, and won't trigger anyone's epilepsy, you can have a lot of movement going on at once without getting to the point of being overwhelming.

Most of the intro screens developed so far fall more into the "zen garden" category of a slow, subtle, and/or constant animation which viewers could watch for an hour without getting motion sick or bored.

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
