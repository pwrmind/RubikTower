
🗼 Rubik's Tower Game

Rubik's Tower is an innovative 2D puzzle game built with Three.js that transforms the classic 3D geometry of a Rubik's Cube into a linear vertical tower. The project is named Mudra and uses the ultra-fast uv package manager for its development workflow.
By displaying 6 interconnected clones of a single Rubik's Cube stacked on top of each other, the game allows players to interact with a 3D system using simple 2D linear gestures.

🕹️ Core Game Mechanics

Instead of rotating a heavy 3D camera or handling complex circular gestures, the player interacts with a seamless 2D layout:
• The Stack: Six 3 × 3 faces are stacked vertically (ROOF, FRONT, FLOOR, BACK, LEFT, RIGHT). Each section represents a different perspective of a single underlying cube state.
• 4-Way Swipes: Players execute simple vertical or horizontal swipes (LEFT, RIGHT, UP, DOWN) directly on any visible square.
• Symmetric Rotations: Moving a row or column on one face triggers instant, physically accurate 3D updates across all other visible clones. Face-turning operations (clockwise/counterclockwise) happen automatically as a mathematical consequence of horizontal or vertical actions applied elsewhere on the tower.

🛠️ Tech Stack & Key Features

• Three.js Core: Utilizes an orthographic camera (THREE.OrthographicCamera) to eliminate perspective distortion, translating true 3D matrices into clean, scalable, pixel-perfect 2D vector layouts.
• Manhattan Distance Metric: Progress is evaluated using a true 3D spatial heuristic. Instead of just tracking face stickers, the game measures the Manhattan distance of all 27 sub-cubes from their origin coordinates. This ensures a reliable progress bar that tracks structural clarity without misleading the player.
• State Preservation (Save System): Leverages browser localStorage along with 3D quaternions (THREE.Quaternion) to encode spatial geometry into stable text formatting. Progress is safely stored after every turn and reloaded upon page refresh.
• Atomic Animation Engine: Leverages a THREE.Group dynamic pivot system to handle multi-axis operations. While an animation is executing, an automated queue acts as an input firewall to prevent geometric desynchronization.

🚀 Getting Started


Prerequisites

Make sure you have Python and uv installed on your system.

Installation & Running Locally

1. Clone the repository:bash
git clone https://github.com
cd rubiks-tower
Use code with caution.
2. Run the local development server:
Since the codebase fits within a lightweight, self-contained index.html structure, you can launch a local server instantly using Python's built-in engine powered by uv:bash
uv run python -m http.server 8000
Use code with caution.
3. Play the game:
Open your browser and navigate to http://localhost:8000.

📂 Project Structure

text
├── index.html       # Self-contained game client (HTML5, CSS layout, and Three.js logic)
└── README.md        # Documentation
Use code with caution.
Would you like to include an Installation section for hosting this project directly on GitHub Pages, or should we expand the README with specific instructions for the game design rules?
