# WheelsTrainer v0.2

A Geared and Remote Head Trainer for YouTube Spherical Videos

A specialized training tool for camera operators that simulates real-world geared & remote head controls using either OSC-compatible wheels or mouse-style controllers.

## What's New in v0.2

### Authentication System
- **Email-based authentication** with 6-digit OTP verification
- **Beta access mode** - No subscription required during beta testing
- **Secure session management** using Supabase backend

### Enhanced Control System
- **Inversion handling** - Automatic 180° offset when looking straight up/down
- **Improved mouse control** - Better sensitivity and cursor handling
- **Real-time status indicators** - Visual feedback for controller states

### YouTube Integration
- **Thumbnail click handling** - Click YouTube thumbnails to load videos directly in-app
- **Enhanced URL parsing** - Support for multiple YouTube URL formats
- **Better error handling** - Graceful fallbacks for failed video loads

### Settings & Configuration
- **Persistent settings** - Controller preferences saved between sessions
- **Mouse sensitivity** - Adjustable from 0.1 (fine) to 1.0 (coarse)
- **OSC configuration** - Customizable IP address and port settings
- **Live settings updates** - Changes apply immediately without restart

### Overlay System
- **Toggleable crosshairs** - Red crosshair guides for precise framing
- **Aspect ratio guides** - Customizable frame lines (e.g., 1.78:1, 2.35:1)
- **Visual feedback** - Active/inactive states for all overlay controls

## Installation

### For End Users

#### macOS
1. Download the latest `.dmg` file from Releases
2. Open the `.dmg` and drag `WheelsTrainer.app` to Applications
3. **First-time setup**: Right-click the app in Applications and select "Open"
4. If prompted, click "Open" to bypass Gatekeeper security

#### Windows
1. Download `WheelsTrainer-Setup-x.x.x.exe` from Releases
2. Run the installer and follow the setup wizard
3. Launch from Start Menu or desktop shortcut

### Authentication Process
1. **First launch**: Enter your email address
2. **Verification**: Check your email for a 6-digit code
3. **Access granted**: App loads after successful verification

## Usage

### Getting Started
1. **Launch the app** and complete email verification
2. **Configure controller** in Settings (⌘+, or Ctrl+,)
3. **Load a video** by:
   - Pasting a YouTube URL in the input field
   - Clicking "Load" button
   - Clicking YouTube thumbnails (opens directly in app)
4. **Control the view** using your selected controller type

### Controller Setup

#### OSC Controllers (NODO Inertia Wheels)
1. Go to Settings → Controller Type → "OSC Control"
2. Set IP address (default: 127.0.0.1) and port (default: 1234)
3. **Status indicators**:
   - 🟢 Green: OSC active, receiving messages
   - 🟡 Yellow: OSC connected, awaiting messages  
   - ⚫ Gray: OSC disconnected

#### Mouse Controllers (Hammerhead, Black-tek, Rexy Wheels)
1. Go to Settings → Controller Type → "Mouse Control"
2. Adjust sensitivity slider to preference
3. **Activation**: Click the "MOUSE" indicator below the player
4. **Control**: Move mouse to pan/tilt, press ESC to exit

### Overlay Tools

#### Crosshairs
- Toggle with the `🞡` button
- Red crosshair guides for center framing
- Useful for precise composition

#### Frame Guides  
- Toggle with the `□` button
- Set custom aspect ratios (width:height)
- Shows letterbox/pillarbox areas
- Perfect for cinematic framing

### Advanced Features

#### Inversion Handling
- **Automatic**: When tilt exceeds ±90°, view automatically inverts 180°
- **Seamless transition**: Maintains orientation when looking straight up/down
- **Manual override**: Available in developer tools

#### Field of View Control
- **Vertical slider**: 30° (narrow) to 120° (wide)
- **OSC support**: `/fov` channel accepts 30-120 values
- **Real-time updates**: Changes apply immediately

## For Developers

### Development Setup
```sh
git clone https://github.com/FooChilde/WheelsTrainer
cd WheelsTrainer
npm install
npm start
```

### Development Commands
| Command             | Description                            |
| `npm start`         | Launch production mode (requires auth) |
| `npm run build-win` | Build Windows package                  |
| `npm run build-mac` | Build macOS package                    |
| `npm run build-all` | Build for all platforms                |

## Architecture

- **Modular design**: Separate modules for player, controls, overlays, content
- **IPC communication**: Secure main-renderer process messaging  
- **Settings persistence**: JSON-based configuration storage
- **Error handling**: Comprehensive logging and error recovery

## Key Files

- `main.js` - Electron main process
- `auth.js` - Authentication management
- `ytplayer.js` - YouTube IFrame API integration
- `control.js` - Mouse/OSC input handling
- `overlays.js` - Visual guide system
- `content.js` - Main application coordinator

## Support & Troubleshooting

### Common Issues

- **Authentication fails**: Check internet connection and email spam folder
- **OSC not connecting**: Verify IP/port settings match your OSC server
- **Video won't load**: Ensure YouTube URL is valid and video is accessible
- **Mouse control stuck**: Press ESC key to exit control mode

### Getting Help

- **Bug Reports**: Use in-app menu (Help → Bug Report) or GitHub Issues
- **Documentation**: Visit GitHub repository for latest docs
- **Feedback**: Use in-app feedback form or Discord

## System Requirements

- **macOS**: 10.14+ (Intel & Apple Silicon)
- **Windows**: 10+ (64-bit)
- **RAM**: 4GB minimum, 8GB recommended
- **Internet**: Required for authentication and YouTube videos

## License

MIT License - See LICENSE file for full terms.

## Contact

- **Developer**: Foo_Childe
- **Discord**: https://discord.com/users/139956315316420608
- **GitHub**: https://github.com/FooChilde/WheelsTrainer
- **Feedback**: https://forms.gle/UiqrUHzf6RfW14dd6

---

*WheelsTrainer v0.2 - Professional camera training for spherical video environments*