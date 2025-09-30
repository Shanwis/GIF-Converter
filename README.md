# Video to GIF Creator (Name is a work in progress)

A command-line tool to quickly create high-quality animated GIFs from video files using Python. You can trim the video, adjust speed and FPS, resize the output, and add custom text overlays. 

It seemed like a fun idea honestly!

![Demonstration of the GIF Creator](./assets/program.gif)

## Features

* Clip a specific segment from any video file.
* Adjust the speed and frame rate (FPS) of the resulting GIF.
* Resize the output to a specific scale (e.g., 50% of original size).
* Overlay custom text with control over font, size, color, and position.
* Cross-platform support (Windows, macOS, Linux).
* Interactive warning for potentially large file sizes with an option to adjust settings.

## Core Dependencies

This tool relies on a few key Python libraries to work its magic:
* MoviePy (v1.0.3): The core library for video editing, used for clipping, composing, and rendering the final GIF.
* Pillow (v9.5.0): A powerful image processing library that MoviePy uses for tasks like resizing frames.

**A Note on Versions:** This project is intentionally pinned to these specific library versions in the requirements.txt file. This ensures stability and avoids breaking changes introduced in newer versions of moviepy, providing a consistent and reliable experience

## Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/Shanwis/GIF-Converter](https://github.com/Shanwis/GIF-Converter)
    cd GIF-Converter
    ```

2.  **Install the required Python libraries:**
    All dependencies are listed in the `requirements.txt` file.
    ```bash
    pip install -r requirements.txt
    ```
    That's it! No other external software is needed.

## Usage

The script is run from the command line. The only required argument is the path to the video file.

```bash
python3 GIFCreator.py -f <path_to_video> [options]
```

### Examples

**Create a simple 5-second GIF from the beginning of a video:**
```bash
python3 GIFCreator.py -f "my_video.mp4" -d 5
```

**Create a high-quality GIF starting at 10 seconds, with red text at the top left:**
```bash
python3 GIFCreator.py -f "input.mp4" -s 10 -d 3 -fp 25 -t "Hello World!" -p top_left -c "red" -fs 70
```

**Create a half-sized GIF that runs at 1.5x speed:**
```bash
python3 GIFCreator.py -f "cool_movie.mkv" -s 65 -d 4 -r 0.5 -sp 1.5
```

### All Options

```
usage: GIFCreator.py [-h] -f FILE [-s START] [-d DURATION] [-fp FPS] [-sp SPEEDUP] [-r RESIZE] [-t TEXT] [-p POSITION]
                     [-fo FONT] [-fs FONTSIZE] [-op OPACITY] [-c COLOR] [--loop LOOP] [-o OUTPUT]

Make video into GIFS

options:
  -h, --help            show this help message and exit
  -f FILE, --file FILE  Enter the .mp4 file location
  -s START, --start START
                        Enter the start time
  -d DURATION, --duration DURATION
                        Enter the length of GIF
  -fp FPS, --fps FPS    Enter the fps value you want
  -sp SPEEDUP, --speedup SPEEDUP
                        Enter the speedup of the clip
  -r RESIZE, --resize RESIZE
                        Scale the video (e.g., 0.5, 1.0, etc)
  -t TEXT, --text TEXT  Enter the tagline text
  -p POSITION, --position POSITION
                        Text position. Choices: top_left, top_right, bottom_left, bottom_right, center, top, bottom, left, right
  -fo FONT, --font FONT
                        Font name or path to TTF file
  -fs FONTSIZE, --fontsize FONTSIZE
                        Font size of the text
  -op OPACITY, --opacity OPACITY
                        Enter the opacity of the text
  -c COLOR, --color COLOR
                        Color of the text
  --loop LOOP           Number of times to loop GIF (0 = infinite)
  -o OUTPUT, --output OUTPUT
                        Output GIF file name
```
