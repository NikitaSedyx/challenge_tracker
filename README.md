# Challenge Tracker 🎯

A simple, mobile-first Progressive Web App (PWA) for tracking daily challenges and building great habits. Built with React and designed to work offline on any device.

![Challenge Tracker](https://img.shields.io/badge/React-18.2.0-blue) ![PWA](https://img.shields.io/badge/PWA-Enabled-green) ![Mobile First](https://img.shields.io/badge/Mobile-First-orange)

## ✨ Features

- **📱 Mobile-First Design**: Optimized for smartphones with responsive layout
- **🚀 Progressive Web App**: Install on any device like a native app
- **💾 Offline Support**: Works without internet connection
- **� Mini-Games**: Complete fun mini-games before marking days as complete
- **�🎉 Interactive Completion**: Animated day completion with motivational quotes
- **📊 Visual Progress**: Beautiful progress bars and completion tracking
- **🔒 Privacy-Focused**: All data stored locally, no cloud sync required
- **⚡ Lightweight**: Fast loading and minimal data usage

## 🚀 Quick Start

### Prerequisites

- **Node.js** (version 14 or higher)
- **npm** or **yarn** package manager

### Local Development Setup

1. **Clone or download** this project to your computer

2. **Navigate to the project directory**:
   ```bash
   cd challenge_tracker
   ```

3. **Install dependencies**:
   ```bash
   npm install
   ```

4. **Start the development server**:
   ```bash
   npm start
   ```

5. **Open your browser** and visit: `http://localhost:3000`

The app will automatically reload when you make changes to the code.

### Building for Production

To create an optimized production build:

```bash
npm run build
```

The optimized files will be in the `build` folder.

**Note**: The app is configured to be hosted at `/challenge_tracker/` subfolder. All asset paths in the built files will be prefixed with `/challenge_tracker/`.

### Serving the Production Build Locally

To test the production build locally with subfolder configuration:

```bash
npm install -g serve
npm run build
serve -s build -l 3000
```

Then visit `http://localhost:3000/challenge_tracker/` to see the production version.

## 📱 Installing on Your Phone

The Challenge Tracker is a Progressive Web App (PWA), which means you can install it on your phone like a native app. Here's how:

### iPhone (iOS Safari)

1. **Open Safari** and navigate to your app's URL
2. **Tap the Share button** (square with arrow pointing up) at the bottom of the screen
3. **Scroll down** and tap "Add to Home Screen"
4. **Customize the name** if desired, then tap "Add"
5. The app icon will appear on your home screen

### Android (Chrome)

1. **Open Chrome** and navigate to your app's URL
2. **Tap the menu** (three dots) in the top-right corner
3. **Tap "Add to Home screen"** or look for an "Install" banner at the bottom
4. **Confirm** by tapping "Add" or "Install"
5. The app will be installed and appear in your app drawer

### Alternative Method (Both Platforms)

Many modern browsers will show an **"Install App" banner** automatically when you visit the PWA. Simply tap "Install" when prompted.

## 🌐 Deploying Your App

To make your Challenge Tracker accessible on phones, you need to deploy it to a web server. Here are several free options:

### Subfolder Deployment

The app is configured to work when deployed to a `/challenge_tracker/` subfolder. This is useful when hosting multiple apps on the same domain.

**Important**: After deployment, your app will be accessible at `https://yourdomain.com/challenge_tracker/`

### Option 1: Netlify (Recommended)

1. **Build the project**: `npm run build`
2. **Drag the `build` folder** to [netlify.com/drop](https://netlify.com/drop)
3. **Get your URL** and share it with users
4. For automatic deployments, connect your GitHub repository to Netlify

### Option 2: Vercel

1. **Install Vercel CLI**: `npm i -g vercel`
2. **Run**: `vercel` in your project directory
3. **Follow the prompts** to deploy
4. Your app will be live at the provided URL

### Option 3: GitHub Pages

1. **Install gh-pages** (if not already installed): `npm install --save-dev gh-pages`
2. **Deploy**: `npm run deploy` (this will automatically build and deploy)
3. **Access**: Your app will be live at `https://yourusername.github.io/challenge_tracker/`

**Note**: The current configuration automatically works with GitHub Pages since the repository name matches the subfolder path. The `predeploy` script automatically runs the build before deployment.

### Option 4: Firebase Hosting

1. **Install Firebase CLI**: `npm install -g firebase-tools`
2. **Initialize**: `firebase init hosting`
3. **Deploy**: `firebase deploy`

## 💡 How to Use

### Creating a Challenge

1. **Tap the "+" button** on the home screen
2. **Enter your challenge name** (e.g., "Morning Workout", "Read 30 minutes")
3. **Set the number of days** (1-365)
4. **Tap "Create Challenge"**

### Completing Daily Tasks

1. **Open a challenge** by tapping on it
2. **Tap "Complete Day X"** or tap on the current day in the grid
3. **Play a mini-game** to prove you're engaged! Games include:
   - **Reaction Time**: Tap when the circle turns green
   - **Memory Sequence**: Remember and repeat button patterns
   - **Quick Math**: Solve simple addition problems
   - **Pattern Memory**: Remember highlighted squares
   - **Fast Tap**: Tap as many times as possible in 3 seconds
4. **Enjoy the celebration** and motivational quote after success!
5. **Track your progress** visually with the progress bar

### Managing Challenges

- **View all challenges** on the home screen with progress bars
- **Delete challenges** using the trash icon in challenge details
- **Track completion** with the visual day grid

## 🛠 Technical Details

### Built With

- **React 18.2** - UI framework
- **Vanilla CSS** - Styling (no external CSS frameworks)
- **localStorage** - Data persistence
- **Service Worker** - Offline functionality
- **Web App Manifest** - PWA installation

### Browser Support

- **Chrome** 60+ (Android & Desktop)
- **Safari** 11+ (iOS & macOS)
- **Firefox** 60+ (Android & Desktop)
- **Edge** 79+ (Windows & Mobile)

### PWA Features

- ✅ **Service Worker** for caching and offline support
- ✅ **Web App Manifest** for installation
- ✅ **Responsive Design** for all screen sizes
- ✅ **Touch-Friendly** interface
- ✅ **Fast Loading** with optimized assets

### Data Storage

All data is stored locally using `localStorage`:

- **Challenges**: Basic challenge information (name, days, creation date)
- **Progress**: Completion status for each day of each challenge
- **No Cloud Sync**: Your data stays on your device

## 🎨 Customization

### Customizing the Deployment Path

If you need to deploy to a different subfolder path, update the `homepage` field in `package.json`:

```json
{
  "homepage": "/your-custom-path"
}
```

This will make all asset paths use `/your-custom-path/` instead of `/challenge_tracker/`.

### Changing Colors

Edit the CSS custom properties in `src/index.css`:

```css
:root {
  --primary-color: #4f46e5;
  --success-color: #22c55e;
  --danger-color: #ef4444;
}
```

### Adding More Motivational Quotes

Edit `src/utils/quotes.js` to add your own motivational messages:

```javascript
export const motivationalQuotes = [
  "Your custom quote here! 🌟",
  // ... more quotes
];
```

### Modifying the App Name

Update these files:
- `public/manifest.json` - Change `name` and `short_name`
- `public/index.html` - Update `<title>` tag
- `src/components/HomeScreen.js` - Change header title

## 🐛 Troubleshooting

### App Not Installing on Phone

- Ensure you're using HTTPS (required for PWA installation)
- Check that the manifest.json is accessible
- Try refreshing the page and looking for install prompts

### Data Not Persisting

- Check if localStorage is enabled in your browser
- Make sure you're not in incognito/private browsing mode
- Clear browser cache and try again

### Offline Not Working

- Ensure the service worker is registered successfully
- Check browser developer tools for service worker errors
- Try reloading the page when online first

## 📄 License

MIT License - feel free to use this project for personal or commercial purposes.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Commit changes: `git commit -am 'Add feature'`
4. Push to branch: `git push origin feature-name`
5. Submit a pull request

## 📞 Support

If you encounter any issues:

1. Check the troubleshooting section above
2. Open an issue on GitHub
3. Make sure you're using a supported browser
4. Try clearing your browser cache

---

**Happy habit building! 🎯✨**
