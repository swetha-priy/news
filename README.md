# 📰 News Aggregator

A modern, personalized news aggregator application that fetches the latest headlines and stories from various categories (Technology, Sports, Entertainment). Users can browse, save articles to favorites, and filter news based on their interests. This app serves as a personalized digital newspaper with real-time updates and offline access to saved articles.

## ✨ Features

- **Multi-Category News**: Browse news from Technology, Sports, and Entertainment categories
- **Real-time Updates**: Fetch the latest headlines from news sources
- **Favorites System**: Save articles to your favorites for later reading
- **Search Functionality**: Search for specific articles across all categories
- **Offline Access**: All favorited articles are saved locally and available offline
- **Modern UI**: Beautiful, responsive design with smooth animations
- **Personalized Experience**: Filter and organize news based on your interests

## 🚀 Getting Started

### Prerequisites

- Node.js (v16 or higher)
- npm or yarn

### Installation

1. Clone or download this repository
2. Install dependencies:
   ```bash
   npm install
   ```

3. (Optional) Set up NewsAPI.org for real news data:
   
   **Get Your Free API Key:**
   - Visit [NewsAPI.org](https://newsapi.org/register)
   - Sign up for a free account (no credit card required)
   - Copy your API key from the dashboard
   
   **Setup API Key:**
   - Copy `.env.example` to `.env` (or create a new `.env` file)
   - Add your API key:
     ```
     VITE_NEWS_API_KEY=your_actual_api_key_here
     ```
   - Save the file
   - Restart your dev server: `npm run dev`
   
   **Note:** 
   - Free tier: 100 requests per day
   - The app works with sample Indian news data if no API key is provided
   - Your `.env` file is automatically ignored by git (already in .gitignore)

4. Start the development server:
   ```bash
   npm run dev
   ```

5. Open your browser and navigate to:
   - **Main page**: http://localhost:5173/
   - **Direct to Offline News**: http://localhost:5173/offline

## 🛠️ Tech Stack

- **React 18**: Modern React with hooks
- **React Router**: For navigation between pages
- **Vite**: Fast build tool and dev server
- **Axios**: HTTP client for API requests
- **Local Storage**: For offline favorites storage
- **CSS3**: Modern styling with gradients and animations

## 📱 Usage

1. **Browse News**: Click on category tabs (Technology, Sports, Entertainment) to view news
2. **Search**: Use the search bar to find specific articles
3. **Save Favorites**: Click the heart icon (🤍) on any article to save it
4. **View Favorites**: Navigate to the Favorites page to see all saved articles
5. **Offline Reading**: All favorited articles are stored locally and available offline

## 🎨 Features in Detail

### Category Filtering
Switch between different news categories with a single click. Each category shows relevant headlines.

### Search
Search across all news articles using keywords. Results update in real-time.

### Favorites Management
- Add articles to favorites with one click
- View all favorites in a dedicated page
- Remove favorites when no longer needed
- All favorites are stored locally for offline access

### Responsive Design
The app is fully responsive and works seamlessly on desktop, tablet, and mobile devices.

## 📝 Notes

- If you don't have a NewsAPI key, the app will use sample data for demonstration
- Favorites are stored in browser's local storage
- The app works offline for viewing saved favorites
- For real-time news updates, you'll need a NewsAPI.org API key

## 📴 Offline Access

### How to Use Offline Mode:

1. **Save Articles While Online:**
   - Open the app at `http://localhost:5173`
   - Browse news articles
   - Click the heart icon (🤍) to save articles to favorites
   - Your favorites are automatically saved to browser's localStorage

2. **Access Offline:**
   - **Method 1: Browser DevTools**
     - Open DevTools (F12) → Network tab
     - Check "Offline" checkbox
     - Refresh the page
     - Navigate to the Favorites page - your saved articles will still be visible!
   
   - **Method 2: Disconnect Internet**
     - Disconnect your Wi-Fi/Ethernet
     - The app will still work for viewing favorites
     - Note: You won't be able to fetch new news, but saved favorites remain accessible

3. **View LocalStorage:**
   - Open DevTools (F12) → Application tab (Chrome) or Storage tab (Firefox)
   - Go to Local Storage → `http://localhost:5173`
   - Find the `favorites` key to see all saved articles

### What Works Offline:
✅ View all saved favorite articles  
✅ Search through your favorites  
✅ Remove articles from favorites  
✅ Read article titles and descriptions  
✅ Navigate between pages (if Service Worker is active)

### What Doesn't Work Offline:
❌ Fetch new news articles  
❌ Search for new articles  
❌ Load article images (unless cached)

## 🔧 Build for Production

```bash
npm run build
```

The built files will be in the `dist` directory.

## 🛠️ React DevTools

React DevTools is a browser extension that helps you debug and inspect your React application.

### Installation

**For Chrome/Edge:**
1. Go to [Chrome Web Store - React DevTools](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi)
2. Click "Add to Chrome"
3. The extension will be installed automatically

**For Firefox:**
1. Go to [Firefox Add-ons - React DevTools](https://addons.mozilla.org/en-US/firefox/addon/react-devtools/)
2. Click "Add to Firefox"
3. The extension will be installed automatically

### How to Use

1. **Open Your App**: Make sure your app is running at `http://localhost:5173`
2. **Open Browser DevTools**: Press `F12` or right-click → Inspect
3. **Find React Tab**: Look for "⚛️ Components" or "⚛️ Profiler" tabs in DevTools
4. **Inspect Components**: 
   - Click on any component in the tree to see its props, state, and hooks
   - View component hierarchy
   - Check component props and state values
   - See React Router navigation

### What You Can Do with React DevTools

- **Inspect Component Tree**: See the full component hierarchy
- **View Props & State**: Check current values of props and state
- **Edit Props**: Modify props in real-time to test different scenarios
- **View Hooks**: See all React hooks (useState, useEffect, etc.) and their values
- **Performance Profiling**: Use the Profiler tab to identify performance issues
- **Component Search**: Search for specific components in large component trees
- **Highlight Updates**: See which components re-render when state changes

### Tips

- The React DevTools icon will appear in your browser toolbar when a React app is detected
- If you don't see the React tab, make sure your app is running and refresh the page
- Use the search box in DevTools to quickly find components
- Right-click on components to access additional options

## 🐛 Debug Console

The browser console is your best friend for debugging! Here's how to use it effectively.

### How to Open Console

**Windows/Linux:**
- Press `F12` or `Ctrl + Shift + I`
- Or right-click → "Inspect" → "Console" tab

**Mac:**
- Press `Cmd + Option + I`
- Or right-click → "Inspect" → "Console" tab

### Debug Logs in This App

The app includes helpful console logs (only in development mode):

- **✅ Article added**: Shows when an article is saved to favorites
- **❌ Article removed**: Shows when an article is removed from favorites
- **📰 Loading news**: Shows when news is being fetched
- **🔍 Searching**: Shows search queries
- **💾 LocalStorage**: Shows when favorites are loaded/saved
- **📊 Counts**: Shows total number of favorites

### Common Console Commands

```javascript
// View all favorites in localStorage
JSON.parse(localStorage.getItem('favorites'))

// Clear all favorites
localStorage.removeItem('favorites')

// Check if article is favorite
localStorage.getItem('favorites').includes('article-id')

// View current route
window.location.pathname

// Clear console
console.clear()

// Log component state (in React DevTools)
// Select component → See "hooks" section
```

### Debugging Tips

1. **Filter Console Messages:**
   - Use the filter box to search for specific logs
   - Filter by "Error", "Warning", or "Info"

2. **Breakpoints:**
   - Click line numbers in Sources tab to set breakpoints
   - Code will pause execution at that point

3. **Network Tab:**
   - Check API requests and responses
   - See if requests are failing
   - Check request/response headers

4. **Application Tab:**
   - View localStorage data
   - Check cookies
   - Inspect service workers

5. **Console Shortcuts:**
   - `$0` - Reference to selected element
   - `$_` - Last evaluated expression
   - `$` - jQuery (if available)

### Common Issues & Solutions

**Issue: "Cannot read property of undefined"**
- Check console for the exact line
- Add `console.log()` before the error to see what's undefined

**Issue: "localStorage is not working"**
- Check Application tab → Local Storage
- Verify data is being saved
- Check for JSON parsing errors

**Issue: "Component not updating"**
- Check React DevTools to see if state changed
- Look for console errors
- Verify event handlers are firing

### Enable Verbose Logging

To see all debug logs, make sure you're running in development mode:
```bash
npm run dev
```

Production builds (`npm run build`) won't show debug logs.

## 🔑 API Key Setup Guide

### Quick Start

1. **Get Free API Key:**
   - Visit: [https://newsapi.org/register](https://newsapi.org/register)
   - Sign up (free, no credit card)
   - Copy your API key

2. **Create `.env` File:**
   ```bash
   # In project root, create .env file with:
   VITE_NEWS_API_KEY=your_api_key_here
   ```

3. **Restart Server:**
   ```bash
   npm run dev
   ```

### Benefits of Using API Key

✅ **Real Indian News**: Live news from Times of India, The Hindu, NDTV, etc.  
✅ **50 Articles**: Up to 50 articles per category (vs 10 sample)  
✅ **Search Works**: Real-time search across Indian news sources  
✅ **Daily Updates**: Fresh news every day  

### Free Tier Limits

- **100 requests/day** (perfect for development)
- **All categories** available
- **Indian sources** included
- **Search enabled**

### Troubleshooting

**"Still seeing sample data"**
- ✅ Check `.env` file exists in root directory
- ✅ Verify format: `VITE_NEWS_API_KEY=your_key` (no quotes)
- ✅ Restart dev server after creating/changing `.env`
- ✅ Check browser console (F12) for errors

**"Rate limit exceeded"**
- Free tier: 100 requests/day
- Wait 24 hours or upgrade plan
- App automatically uses sample data as fallback

**"API key not working"**
- Verify key is correct in NewsAPI dashboard
- Make sure variable name is exactly `VITE_NEWS_API_KEY`
- Check for typos or extra spaces

### Security

- ✅ `.env` is in `.gitignore` - your key won't be committed
- ✅ Never share your API key publicly
- ✅ Key only used client-side in development

### Without API Key

The app works perfectly with sample Indian news:
- 10 articles per category
- All features work
- No setup needed!

## 🎯 VS Code Debugging

Your project includes VS Code launch configurations for easy debugging!

### How to Use

1. **Open VS Code** in your project folder
2. **Go to Run and Debug**: Press `F5` or click the debug icon in the sidebar
3. **Select a configuration**:
   - **🎯 Launch Server + Debug (Recommended)**: Starts dev server and opens Chrome with debugging
   - **🚀 Launch Chrome (Vite Dev)**: Opens Chrome if server is already running
   - **🔗 Attach to Chrome**: Attach to an existing Chrome instance
   - **🌐 Launch Chrome (Production Build)**: Debug production build
   - **⚙️ Debug Vite Server**: Debug the Vite dev server itself

### Debugging Features

- **Breakpoints**: Click line numbers to set breakpoints
- **Step Through Code**: Use F10 (step over), F11 (step into), Shift+F11 (step out)
- **Watch Variables**: Add variables to watch panel
- **Call Stack**: See function call hierarchy
- **Debug Console**: Execute code in current context

### Quick Start

1. Press `F5` in VS Code
2. Select "🎯 Launch Server + Debug (Recommended)"
3. Chrome will open with your app
4. Set breakpoints in your code
5. Interact with your app - execution will pause at breakpoints!

### Tips

- **Hot Reload**: Changes still hot-reload while debugging
- **Source Maps**: Source maps are enabled for accurate debugging
- **React Components**: Use React DevTools extension alongside VS Code debugger
- **Console**: Use both VS Code debug console and browser console

## 📄 License

This project is open source and available for personal and commercial use.
