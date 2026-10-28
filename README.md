# 3D Endless Runner Game (Python + OpenGL)

A 3D endless-runner game built in Python with PyOpenGL, GLU, and GLUT. The game renders an endless road with three lanes, a running player, obstacles, collectible coins, power-ups, weather effects, and a small HUD.

## Features visible in the current source

- Endless three-lane road with buildings and randomly generated obstacles.
- Player lane switching, jumping, and sliding.
- Coins, score, distance, and a three-bullet special attack for clearing obstacles.
- Magnet power-up that attracts coins.
- Lightning power-up that temporarily grants invincibility and a speed boost.
- Day, night, and rainy weather modes.
- First-person/third-person camera toggle.
- Pause, restart, and quit UI controls.

See [`FEATURES.md`](FEATURES.md) for the full feature description provided with the project and notes about features that are not evident in the uploaded source file.

## Requirements

- Python 3.10 or newer (Python 3.11 is a reasonable choice for a coursework project).
- PyOpenGL (`OpenGL.GL`, `OpenGL.GLU`, and `OpenGL.GLUT`).
- A working OpenGL driver and a GLUT/FreeGLUT runtime. On Windows, if the game reports that `glut` or a GLUT DLL cannot be found, install a compatible FreeGLUT runtime and ensure its DLL is discoverable by Windows.
- Visual Studio Code is recommended, with the Python extension.

## Run in VS Code on Windows

1. Download or clone this repository and open its folder in VS Code.
2. Open **Terminal → New Terminal** in VS Code.
3. Create a virtual environment:

   ```powershell
   py -m venv .venv
   ```

4. Activate it in PowerShell:

   ```powershell
   .\.venv\Scripts\Activate.ps1
   ```

   If PowerShell blocks activation, you can skip activation and use `.\.venv\Scripts\python.exe` for the following commands instead.

5. Install the Python dependency:

   ```powershell
   python -m pip install --upgrade pip
   python -m pip install -r requirements.txt
   ```

6. In VS Code, select the `.venv` interpreter using **Python: Select Interpreter**.
7. Run the game:

   ```powershell
   python endless_runner.py
   ```

   If FreeGLUT is missing, installing the Python package alone may not be enough; the system GLUT runtime must also be installed and discoverable.

## Controls

| Input | Action |
|---|---|
| `A` / `D` | Switch lanes (the current source's movement mapping may feel reversed compared with the on-screen hint) |
| `W` | Jump |
| Hold `S` | Slide |
| `Space` | Fire a bullet to clear an obstacle in the current lane; three shots are available per run |
| `1` | Day weather |
| `2` | Night weather |
| `3` | Rainy weather |
| Right mouse button | Toggle first-person / third-person camera |
| Arrow keys | Adjust camera angle/height |
| `R` | Restart after game over |
| On-screen buttons | Pause/resume, restart, or quit |

## Project structure

```text
3d-endless-runner-opengl/
├── endless_runner.py   # Main game source
├── requirements.txt   # Python package dependencies
├── FEATURES.md         # Feature description and implementation notes
├── README.md           # Setup and controls
└── .gitignore
```

## Notes

- The game is a desktop OpenGL application; it will not run as a normal web page or inside a notebook cell.
- Keep `endless_runner.py` and the project files together in the same project folder in VS Code. PyOpenGL is installed in the selected Python environment; it does not need to be copied into this folder.
- The source was checked for Python syntax, but runtime behavior depends on your machine's graphics drivers and GLUT/FreeGLUT setup.
