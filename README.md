# Green-Sheet---Green-Reads[README.md](https://github.com/user-attachments/files/33506430/README.md)
# Putt Map

Turn a golf green sheet into a 3D elevation model, then roll a simulated ball on it to get the aim for every putt around a pin.

- `putt-map-app/` is a page in your browser: load a green sheet, click the pin, enter the Stimpmeter reading, and get a map of how many balls outside the cup to aim from every spot within 10 feet.
- `green-sheet-to-3d/` reads a green sheet (arrow-and-number sheets, and StrackaLine sheets via `putt-map-app/strackaline.py`) and rebuilds the green as an elevation grid and a 3D mesh.
  Arrow-and-number sheets also need a `digit_templates.npz` file you build yourself (see that folder's README).
- `putting-physics/` rolls a golf ball across an elevation grid and solves for the aim and pace that hole the putt.

The Southern Hills hole 18 StrackaLine sheet is included as an example (`examples/southern_hills_18.webp`), already read into `putt-map-app/data/greens/southern_hills_18`.

## Start it on a Mac

You need Python 3 and an internet connection the first time.

1. Download this repository (green **Code** button, then **Download ZIP**) and unzip it, or `git clone` it.
2. Open Terminal: press Command + Space, type Terminal, press Return.
3. Type `cd` and a space. Don't press Return yet.
4. Drag the unzipped folder from Finder into the Terminal window. Its path appears after `cd `. Now press Return.
5. Type `python3 start.py` and press Return.

Your browser opens the Putt Map page at http://127.0.0.1:8765. The first start installs the libraries it needs (numpy, scipy, opencv, matplotlib) into a private `.venv` folder, which takes a few minutes. Keep Terminal open while you use the app; press Ctrl+C or close it to stop.

If a box says "python3 requires the command line developer tools", click Install, wait for it to finish, then do step 5 again.

The double-click file `Start Putt Map (Mac).command` also works, but macOS blocks it the first time. To allow it: try to open it, click Done, then open System Settings > Privacy & Security, scroll down and click "Open Anyway". (If you downloaded a ZIP, you may first need `chmod +x "Start Putt Map (Mac).command"` in Terminal.)

## Start it on Windows

Double-click `Start Putt Map (Windows).bat`, or run `python start.py` in this folder. If Python isn't installed, get it from https://www.python.org/downloads/ (tick "Add python.exe to PATH").

## Use it

1. Pick `southern_hills_18` to try the example, or choose your own green sheet photo and press *Read this green sheet* (about 30 seconds).
2. Click the green to place the pin. The dashed circle is the 10 ft radius.
3. Enter the Stimpmeter reading and press *Make the putt map* (about a minute).

Each number is how many balls outside the edge of the cup to aim: blue = left, red = right, black 0 = inside the cup. Maps are saved in `putt-map-app/data/maps`.

More detail is in each folder's README.

## License

MIT, see [LICENSE](LICENSE). `putting-physics/` is adapted from [imran31415/putty](https://github.com/imran31415/putty) (MIT License, Copyright (c) 2025 Putty Golf Simulator); that notice is kept in `LICENSE` and `putting-physics/README.md`.

Green sheets are copyrighted by their publishers. Only use sheets you have the rights to.
