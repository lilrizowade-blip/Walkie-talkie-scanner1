WalkieTalkie & Scanner Pro

A premium Android walkie-talkie and scanner application featuring live police, fire, rescue, and weather scanner feeds with secure private channels and volume-button push-to-talk functionality.

Overview

WalkieTalkie & Scanner Pro is a cutting-edge mobile application that brings professional-grade scanner monitoring and secure communication to your Android device. Built with React Native and Expo, the app provides real-time access to public safety scanner feeds across the United States, organized by geography for easy discovery and monitoring.

Key Features

📡 Live Scanner Feeds

•
Police Dispatch Channels: Real-time access to law enforcement communications

•
Fire & Rescue: Emergency services dispatch and unit activity

•
EMS Communications: Emergency medical services channels

•
Weather Radio: NOAA weather alerts and forecasts

•
National & Local Coverage: Browse channels by state, county, and locality

🗺️ Geographic Organization

•
State-Level Browsing: Browse all 50 US states and territories

•
County-Level Filtering: Drill down to specific counties and jurisdictions

•
Local Channel Discovery: Find channels in your area instantly

•
Listener Statistics: See how many people are monitoring each channel

•
Frequency Display: View technical details (frequency, system type, agency)

📱 Push-to-Talk (PTT) Walkie-Talkie

•
Volume Button Control: Press volume button once to transmit, twice to adjust volume

•
Screen-Off Operation: Full PTT functionality even with screen locked

•
Haptic Feedback: Tactile confirmation of transmission start/stop

•
Activity Indicator: Real-time transmission status display

•
Transmission Timer: Track talk duration

🔒 Secure Private Channels

•
End-to-End Encryption: Military-grade encryption for private communications

•
Password Protection: Secure channel access with customizable passwords

•
Member Management: Invite and manage team members

•
QR Code Sharing: Easy channel sharing via QR codes

•
Local Storage: All private channel data stored securely on device

⭐ Favorites & Customization

•
Star Channels: Save favorite channels for quick access

•
Channel Groups: Organize channels into custom groups

•
Recent Activity: Quick access to recently monitored channels

•
Notification Alerts: Get notified when favorite channels go active

•
Custom Themes: Dark/light mode with tactical color schemes

⚙️ Advanced Settings

•
Rdio Scanner Integration: Connect to Rdio Scanner backend for live feeds

•
Audio Preferences: Configure output device and notification sounds

•
Quiet Hours: Schedule notification-free periods

•
Permission Management: Control app access to microphone, location, notifications

•
API Configuration: Set custom Rdio Scanner server URLs and API keys

Technical Stack

•
Framework: React Native 0.81 with Expo SDK 54

•
Language: TypeScript 5.9

•
Styling: NativeWind (Tailwind CSS for React Native)

•
State Management: React Context + AsyncStorage

•
Audio: expo-audio for playback and recording

•
API Integration: Rdio Scanner API client for live feeds

•
Encryption: TweetNaCl.js for end-to-end encryption

•
Build System: EAS Build for Android APK generation

Installation & Setup

Prerequisites

•
Node.js 18+ and npm/pnpm

•
Expo CLI (npm install -g expo-cli)

•
EAS CLI (npm install -g eas-cli)

•
Android device or emulator

•
Expo account (free at https://expo.dev )

Development Setup

Bash


# Clone the repository
git clone https://github.com/Lilrizowade-blip/walkie-talkie-scanner.git
cd walkie-talkie-scanner

# Install dependencies
pnpm install

# Start the development server
pnpm dev

# For Android device testing
pnpm android

# For iOS (if available )
pnpm ios



Building the APK

Bash


# Install EAS CLI
npm install -g eas-cli

# Authenticate with your Expo account
eas login

# Build development APK
eas build --platform android --profile development

# Build production APK (optimized)
eas build --platform android --profile production



After the build completes, you'll receive a download link for your APK file.

Testing with Expo Go

For rapid development and testing without building an APK:

Bash


# Start the dev server
pnpm dev

# Scan the QR code with Expo Go app on your Android device
# App will load and hot-reload on code changes



Project Structure

Plain Text


walkie-talkie-scanner/
├── app/                          # Expo Router app directory
│   ├── (tabs)/                  # Tab-based navigation
│   │   ├── index.tsx            # Home screen
│   │   ├── browse.tsx           # Geographic channel browser
│   │   ├── favorites.tsx        # Favorites management
│   │   ├── private.tsx          # Private channels
│   │   └── settings.tsx         # App settings
│   ├── channel.tsx              # Channel detail screen
│   └── _layout.tsx              # Root layout with providers
├── components/                   # Reusable UI components
│   ├── screen-container.tsx     # SafeArea wrapper
│   ├── themed-view.tsx          # Theme-aware view
│   └── ui/                      # UI component library
├── hooks/                        # Custom React hooks
│   ├── use-audio-player.ts      # Audio playback management
│   ├── use-colors.ts            # Theme color hook
│   └── use-color-scheme.ts      # Dark/light mode detection
├── lib/                          # Utility libraries
│   ├── rdio-scanner-api.ts      # Rdio Scanner API client
│   ├── theme-provider.tsx       # Global theme context
│   └── utils.ts                 # Helper functions
├── constants/                    # App constants
├── assets/                       # Images, fonts, icons
├── app.config.ts                # Expo app configuration
├── eas.json                      # EAS Build configuration
├── tailwind.config.js           # Tailwind CSS configuration
├── theme.config.js              # Color theme tokens
└── package.json                 # Dependencies and scripts



Color Scheme (Tactical Dark Theme)

The app uses a professional tactical color scheme optimized for readability and battery efficiency:

•
Primary: Bright Cyan (#00D9FF) - Buttons, highlights, active states

•
Background: Deep Black (#0A0E27) - Main screen background

•
Surface: Dark Navy (#1A1F3A) - Cards, elevated surfaces

•
Foreground: Off-White (#E8EAED) - Primary text

•
Success: Lime Green (#00FF41) - Active/online status

•
Warning: Orange (#FF9500) - Warnings, inactive status

•
Error: Red (#FF3B30) - Errors, disconnected status

Configuration

Rdio Scanner Backend

To connect to a live Rdio Scanner instance:

1.
In Settings, enter your Rdio Scanner server URL

2.
Provide your API key (stored securely in device keystore)

3.
Channels will load from your configured backend

Example configuration:

Plain Text


Server URL: https://your-rdio-scanner.com
API Key: your-api-key-here



Environment Variables

Create a .env file in the project root:

Plain Text


EXPO_PUBLIC_RDIO_SCANNER_URL=https://your-rdio-scanner.com
EXPO_PUBLIC_RDIO_SCANNER_API_KEY=your-api-key



Features in Development

The following features are planned for future releases:




Multi-language support (Spanish, French, German )




Advanced channel filtering (by agency, frequency range)




Call recording with user consent




Integration with additional scanner platforms




Desktop companion app




Community features (channel ratings, comments)




iOS version




Apple Watch companion app

Security & Privacy

•
No Data Logging: User activity and audio are never logged

•
Secure Storage: API keys stored in device keystore

•
Encryption: End-to-end encryption for private channels

•
HTTPS Only: All server communication encrypted

•
Permission Control: Users control app permissions

•
Open Source: Code transparency for security audits

Troubleshooting

APK Won't Install

•
Ensure you have "Unknown Sources" enabled in Android settings

•
Check Android version compatibility (API 24+)

•
Try uninstalling previous versions first

Audio Not Playing

•
Verify microphone permissions are granted

•
Check device volume settings

•
Ensure audio output device is selected correctly

•
Restart the app

Connection Issues

•
Verify Rdio Scanner server URL is correct

•
Check API key validity

•
Ensure device has internet connectivity

•
Try switching between WiFi and mobile data

Build Failures

•
Run eas build --platform android --profile development --clear-cache

•
Verify Node.js version is 18+

•
Check EAS CLI is up to date: npm install -g eas-cli@latest

•
Review build logs for specific errors

Contributing

Contributions are welcome! Please follow these guidelines:

1.
Fork the repository

2.
Create a feature branch (git checkout -b feature/amazing-feature)

3.
Commit your changes (git commit -m 'Add amazing feature')

4.
Push to the branch (git push origin feature/amazing-feature)

5.
Open a Pull Request

License

This project is licensed under the MIT License - see the LICENSE file for details.

Support & Feedback

For issues, feature requests, or general feedback:

•
Open an issue on GitHub

•
Contact the development team

•
Check the documentation at /docs

Acknowledgments

•
Built with Expo and React Native

•
Scanner data integration via Rdio Scanner

•
UI components styled with NativeWind

•
Icons from Material Icons

Disclaimer

This application is for educational and monitoring purposes only. Users are responsible for complying with all applicable laws and regulations regarding scanner monitoring in their jurisdiction. Some jurisdictions restrict the monitoring of certain frequencies or types of communications.




Version: 1.0.0
Last Updated: June 2026
Status: Active Development

For the latest updates and releases, visit the GitHub repository.

