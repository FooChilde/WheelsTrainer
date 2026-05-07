# WheelsTrainer v0.2.1a

A Geared and Remote Head Trainer for YouTube Spherical Videos

A specialized training tool for camera operators that simulates real-world geared & remote head controls using either OSC-compatible wheels or mouse-style controllers.

## What's New in v0.2.1a

### Content-Scaling Zoom Control
- **Scale player and controls** - Dynamically scale the YouTube player and Controls to your window size
- **Multiple Hotkeys** - Use "Ctrl or Cmd + Mouse Wheel Up/Down or '-/+' keys" to control zoom


### VTR (Video Tape Recorder) System
- **Camera movement recording** - Record pan, tilt, roll, and FOV movements with video sync
- **Playback with timecode** - SMPTE timecode display (HH:MM:SS:FF) at 60fps
- **Frame-accurate seeking** - Jump to specific timecodes during playback
- **Keyboard shortcuts** - Ctrl+R (record), Ctrl+P (playback), Space (play/pause)
- **File management** - Save/load recordings with video metadata
- **Visual indicators** - Recording/playback status with timecode overlay

### Enhanced Overlay System
- **Multiple crosshair styles** - Cross, Small Cross, and Dot options
- **Color customization** - 9 color options for all overlay elements
- **Real-time updates** - Changes apply immediately without restart
- **Visual feedback** - Active controls highlight in selected color

## Installation

### For End Users

#### macOS
1. Download the latest `.dmg` file from Releases
2. Open the `.dmg` and drag `WheelsTrainer.app` to Applications
3. **First-time setup**: Right-click the app in Applications and select "Open"
4. If prompted, click "Open Anyway" in Privacy & Security settings to bypass Gatekeeper security

#### Windows
1. Download `WheelsTrainer-Setup-x.x.x.exe` from Releases
2. Run the installer and follow the setup wizard
3. Launch from Start Menu or desktop shortcut

### Authentication Process
1. **On launch**: Enter your email address
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

### VTR (Video Tape Recorder) System

#### Recording Camera Movements
1. **Start recording**: Click ⏺ button or press Ctrl+R
2. **Control camera**: Use mouse or OSC controller during recording
3. **Pause/play video**: Space bar toggles video during recording
4. **Stop recording**: Click ⏺ again or press Ctrl+R

#### Playback and Timecode
1. **Play recording**: Click ⏯ button or press Ctrl+P
2. **Timecode display**: SMPTE format (HH:MM:SS:FF) shows current position
3. **Pause playback**: Space bar toggles playback pause/resume
4. **Seek to timecode**: Enter timecode in format `00:00:00:00` and click jump

#### File Management
- **Save recordings**: 💾 button (Ctrl+S) - saves with video metadata
- **Load recordings**: Folder button (Ctrl+O) - browse and load previous recordings
- **Clear recording**: ⏏ button - remove current recording from memory

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
- **Toggle**: `✜` button
- **Styles**: Cross, Small Cross, or Dot (in Settings → Overlay Settings)
- **Colors**: 9 color options including Red, Blue, Green, Yellow, Orange, White, Grey, Cyan, Magenta
- **Usage**: Red crosshair guides for center framing and precise composition

#### Frame Guides  
- **Toggle**: `▭` button
- **Aspect ratios**: Set custom ratios (width:height) like 1.78:1, 2.35:1, etc.
- **Visualization**: Shows letterbox/pillarbox areas for cinematic framing
- **Color matching**: Uses same color selection as crosshairs

### Advanced Features

#### Inversion Handling
- **Automatic**: When tilt exceeds ±90°, view automatically inverts 180°
- **Seamless transition**: Maintains orientation when looking straight up/down
- **Manual override**: Available in developer tools

#### Field of View Control
- **Vertical slider**: 30° (narrow) to 120° (wide)
- **OSC support**: `/fov` channel accepts 30-120 values
- **Real-time updates**: Changes apply immediately

#### Keyboard Shortcuts
| Shortcut | Action |
|:---------|:-------|
| `Space` | Toggle video play/pause or VTR playback pause/resume |
| `Ctrl+R` | Start/stop VTR recording |
| `Ctrl+P` | Start/stop VTR playback |
| `Ctrl+S` | Save VTR recording |
| `Ctrl+O` | Load VTR recording |
| `Ctrl+Shift+Delete` | Clear current recording |
| `Ctrl+Shift+O` | Open VTR recordings folder |

## For Developers

### Development Setup
```sh
git clone https://github.com/FooChilde/WheelsTrainer
cd WheelsTrainer
npm install
npm start
```

### Development Commands
| Command           | Description                            |
|:------------------|:---------------------------------------|
| npm start         | Launch production mode (requires auth) |
| npm run build-win | Build Windows package                  |
| npm run build-mac | Build macOS package                    |
| npm run build-all | Build for all platforms                |


## Architecture

- **Modular design**: Separate modules for player, controls, overlays, VTR, content
- **VTR system**: Frame-accurate recording with timecode synchronization
- **IPC communication**: Secure main-renderer process messaging
- **Settings persistence**: JSON-based configuration storage
- **Error handling**: Comprehensive logging and error recovery

## Support & Troubleshooting

### Common Issues

- **Authentication fails**: Check internet connection and email spam folder
- **OSC not connecting**: Verify IP/port settings match your OSC server
- **Video won't load**: Ensure YouTube URL is valid and video is accessible
- **Mouse control stuck**: Press ESC key to exit control mode
- **VTR playback issues**: Ensure recording matches current video and check timecode format

### VTR Tips

- **Recordings are video-specific** - Each recording is tied to a specific YouTube video ID
- **Timecode format** - Use HH:MM:SS:FF format (00:00:00:00 to 23:59:59:59)
- **Frame rate** - All recordings use 60fps timecode
- **File location** - Recordings saved in app data folder under VTR/ directory

### Getting Help

- **Bug Reports**: Use in-app menu (Help → Bug Report) or GitHub Issues
- **Documentation**: Visit GitHub repository for latest docs
- **Feedback**: Use in-app feedback form or Discord

## System Requirements

- **macOS**: 10.14+ (Intel & Apple Silicon)
- **Windows**: 10+ (64-bit)
- **RAM**: 4GB minimum, 8GB recommended
- **Internet**: Required for authentication and YouTube videos
- **Storage**: 100MB + space for VTR recordings (varies by recording length)

## License

MIT License - See LICENSE file for full terms.

## Contact

- **Developer**: Foo_Childe
- **Discord**: https://discord.com/users/139956315316420608
- **GitHub**: https://github.com/FooChilde/WheelsTrainer
- **Feedback**: https://forms.gle/UiqrUHzf6RfW14dd6

---

*WheelsTrainer v0.2.1a - Professional camera training for spherical video environments with VTR recording and playback*