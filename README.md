# WheelsTrainer
A Geared and Remote Head Trainer for YouTube Spherical Videos

A specialized training tool for camera operators that simulates real-world geared & remote head controls using either OSC-compatible wheels or mouse-style controllers.

### Key Features
- Supports both OSC (Inertia Wheels) and mouse-style (HammerHead, Black-Tek, Rexy) controllers
- Real-time spherical video playback with adjustable Field Of View
- Frame line overlays and aspect ratio guides
- Crosshair display for precise framing
- Direct URL loading from YouTube

## Installation
### For End Users
1. Download the latest release for your OS from the Releases page. For Intel Mac users, download the `x64.dmg`. For Apple Silicon users (M1, M2, etc), download the `arm64.dmg`.
2. Windows: Run `WheelsTrainer-Setup-x.x.x-Windows.exe` and complete setup wizard.
3. macOS: Open the `.dmg` and drag `WheelsTrainer.app` to Applications. Then, right-click on the Applications folder, select "New Terminal at Folder" and enter the command `xattr -c /applications/wheelstrainer.app`. This writes an attribute to the downloaded copy of the app that allows it to bypass gatekeeper and open despite it not containing an Apple Developer Certificate.

## Usage
1. Launch the application. If launching for the first time, activation may be required. 
2. Configure your controller type in Settings:
   - OSC Mode: For Inertia Wheels controllers. Match your IP Address and Port settings to your OSC server.
   - Mouse Mode: For HammerHead/Black-Tek/Rexy Wheels or other mouse-style controllers. Click on the `STBY` button in the main window for player control. Press `Esc` key to exit.
3. Load any YouTube spherical video using the URL input near the bottom left corner of the player.
4. Adjust FOV and framing tools as desired.

## Controller Setup
### OSC Controllers
1. Ensure your wheels are connected to an OSC server that is running on the same network as your machine.
2. Match the `IP Address` and `Port` settings to your running OSC server.
3. Click `Save Settings`. In the main window, a grey `ERASE` field indicates WheelsTrainer's OSC Connection is closed. A green `STBY` field indicates the OSC Connection is open, but WheelsTrainer is not receiving any OSC messages. A red `REC` are indicates WheelsTrainer is receiving OSC messages and is updating the player's properties.

### Mouse-Style Controllers
1. Select "Mouse-Style" in Controller Settings
2. Click the green `STBY` field underneath the player to enter cursor capture mode. While in this mode, a red `REC` field will appear instead, indicating cursor capture mode is enabled. Moving the cursor to the left with pan the player's viewport in the same direction. Moving the cursor down will tilt the player's viewport in the same direction. Press the `Esc` key to return to `STBY` mode.

## For Developers
`git clone [repository-url]`
`cd WheelsTrainer`
`npm ci`

### Development Commands
| Command           | Description               |
|-------------------|---------------------------|
| npm run dev       | Launch development mode   |
| npm run build:win | Build Windows package     |
| npm run build:mac | Build macOS package       |
| npm run lint      | Run code quality checks   |

## Support & Troubleshooting
- Logs: Automatically saved to system app data folder
- Bug Reports: Use the in-app reporting tool

## License
MIT License - See LICENSE for full terms.

## Contact
For support, feature requests, or collaboration:
- Discord: Foo_Childe (https://discord.com/users/139956315316420608)
- GitHub: WheelsTrainer (https://github.com/FooChilde/WheelsTrainer)