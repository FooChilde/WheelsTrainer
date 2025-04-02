# WheelsTrainer  
An OSC-to-YouTube 360° Controller  
Control spherical YouTube videos with OSC devices like the NODO Inertia Wheels

## Installation
1. Download the `dist/` folder from the latest release for your OS.
2. Install using `WheelsTrainer Setup 0.1.0-beta.exe` for Windows or `WheelsTrainer-0.1.0-beta-arm64.dmg` for macOS.

## Usage  
1. Open `WheelsTrainer`. For Windows, check the `WheelsTrainer` folder in the Start Menu or the created shourtcut on your desktop. For macOS, check for `WheelsTrainer.app` in your Applications.
2. Make sure your OSC controller is connected and is running a server.
3. In `WheelsTrainer`, click the `OSC Settings` button near the bottom right corner of the player.
4. In the Settings pop-up window, verify that the `IP Address` and `Port` settings match your OSC server's settings. Click the `Save Settings` button.
5. Under the player, you should now see numerical degree values in the `Pan:`, `Tilt:` and `Roll:` fields. You should also have full control over the player's viewport via your OSC controller.
6. To load a video, copy the url of the video you'd like to play into the `URL:` field near the bottom left corner of the player and click the `Load` button. Your video should automatically play.

# Development
- For Development access, contact the developer. Information in the `Contact` section of this README.
- Download the `WheelsTrainer/` folder from the desired branch.

## Install dependencies
- `npm ci`

## Run in Dev Mode
- `npm run dev`

## Package for Windows 64-bit or macOS 64-bit
- `npm run build:win` or `npm run build:mac`

## License
MIT License - See the included LICENSE file for full terms.

## Contact
For support or questions:
- Discord: `https://discord.com/users/139956315316420608`