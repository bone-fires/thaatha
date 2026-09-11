<img width="1280" height="640" alt="git (1)" src="https://github.com/user-attachments/assets/8920b256-2ba8-4988-b824-5351134eb4bd" />



# icastfireball


## AAISHA
### Team Name: THAATHA


### Team Members
- Team Lead: ADWAITH H A - TKM College of Engineering, Kollam
- Member 2: AAISHA SIDHIK - TKM College of Engineering, Kollam

### Project Description
Laptop Thermal Control Bridge connects a GitHub Pages dashboard to a lightweight local Windows agent. The dashboard provides live thermal telemetry, a configurable cooling-floor control, and an on-demand thermal stress test, while the local agent safely communicates with laptop hardware.
The web interface is hosted directly through GitHub Pages, and the standalone local agent is distributed through GitHub Releases.

### The Problem (that doesn't exist)
Your laptop’s firmware already manages its fans, but it refuses to let you micromanage them while you are compiling code, running benchmarks, or pretending that opening 47 browser tabs is a valid stress test.
The ridiculous problem: How can you manually demand more cooling from your laptop without building a full desktop application or surrendering your hardware controls to a mysterious cloud service?

### The Solution (that nobody asked for)
Laptop Thermal Control Bridge places a stylish browser dashboard in front of a local hardware-control agent. The browser handles the controls and visualisation; the local .exe handles the hardware interaction that browsers are not allowed to perform.
The system enforces a cooling floor only: it can raise fan speeds above the firmware default, but it will never reduce them below the BIOS safety curve. If the dashboard closes, the connection drops, or the agent stops, fan control immediately returns to the laptop’s default firmware behaviour.


## Technical Details
### Technologies/Components Used
For Software:
- Languages used: Python (local agent), JavaScript/TypeScript
- Frameworks used: FastAPI (local agent API), React or vanilla JS
- Libraries used: psutil, pywin32/OpenHardwareMonitor (thermal/fan access), requests/fetch (HTTP comms)
- Tools used: GitHub Pages (hosting), GitHub Releases (distribution), PyInstaller (executable bundling)

For Hardware:
- (Not applicable – this is a pure software project interfacing with existing laptop hardware.)

### Implementation
For Software:
# Installation
 # Clone the repo
 git clone https://github.com/yourusername/laptop-thermal-bridge.git
 cd laptop-thermal-bridge
 # Install agent dependencies
 pip install -r requirements.txt
 # Build the executable (optional)
 pyinstaller --onefile agent.py

# Run
 # Start the local agent
 python agent.py
 # Open the dashboard (GitHub Pages link)
 # https://yourusername.github.io/laptop-thermal-bridge/

### Project Documentation
For Software:

# Screenshots (Add at least 3)
![Screenshot1](Add screenshot 1 here with proper name)
*Add caption explaining what this shows*

![Screenshot2](Add screenshot 2 here with proper name)
*Add caption explaining what this shows*

![Screenshot3](Add screenshot 3 here with proper name)
*Add caption explaining what this shows*

# Diagrams
![Workflow](Add your workflow/architecture diagram here)
*Add caption explaining your workflow*

For Hardware:

# Schematic & Circuit
![Circuit](Add your circuit diagram here)
*Add caption explaining connections*

![Schematic](Add your schematic diagram here)
*Add caption explaining the schematic*

# Build Photos
![Components](Add photo of your components here)
*List out all components shown*

![Build](Add photos of build process here)
*Explain the build steps*

![Final](Add photo of final product here)
*Explain the final build*

### Project Demo
# Video
[Add your demo video link here]
*Explain what the video demonstrates*

# Additional Demos
[Add any extra demo materials/links]

## Team Contributions
- Adwaith H A: Local agent development (Python/FastAPI), hardware interfacing, executable packaging
-Aaisha Sidhik: [Specific contributions] Dashboard UI/UX, GitHub Pages deployment, documentation 
---
Made with ❤️ at TinkerHub Useless Projects 

![Static Badge](https://img.shields.io/badge/TinkerHub-24?color=%23000000&link=https%3A%2F%2Fwww.tinkerhub.org%2F)
![Static Badge](https://img.shields.io/badge/UselessProjects--26-26?link=https%3A%2F%2Ftinkerhub.org%2Fevents%2F1M8ORET9A1%2Fuseless-projects-3.0)



