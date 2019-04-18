Work with [input-overlay](https://github.com/univrsal/input-overlay) on [obs studio](https://github.com/obsproject/obs-studio).

Preview: ![](preview.gif)

License: [CC0](https://creativecommons.org/publicdomain/zero/1.0/legalcode.txt)

Notes: record a gif using obs, ffmpeg and gifsicle

```sh
ffmpeg -y -i a.flv a.mp4
ffmpeg -y -i a.mp4 -ss 00:00:19.50 -t 00:00:02 b.mp4 # -t / -to
ffmpeg -i b.mp4 -vf palettegen palette.png
ffmpeg -y -i b.mp4 -i palette.png -lavfi "fps=15,scale=640:360,paletteuse" b.gif
gifsicle -i b.gif --scale 0.5 -O3 -o c.gif
```
