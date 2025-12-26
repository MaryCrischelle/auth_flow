# AuthFlow - Secure Authentication

A modern, beautiful web application for Facebook authentication with a sleek UI featuring light/dark mode support.

## 🎨 Features

- **Modern UI Design**: Glassmorphism effects, smooth animations, and responsive layout
- **Light/Dark Mode**: Toggle between light and dark themes with persistent preference
- **Facebook Authentication**: Secure login using Facebook SDK
- **User Profile Display**: Shows user name, email, and profile picture after login
- **Mobile Responsive**: Optimized for all device sizes
- **Smooth Animations**: Fade-in, scale, and slide transitions throughout the app

## 🚀 Getting Started

### Prerequisites

- A web server (Python, Node.js, or any HTTP server)
- ngrok (for HTTPS tunneling - required for Facebook login)
- A Facebook App ID (configured in Facebook Developer Console)

### Installation

1. Clone or download this repository
2. Ensure all files are in the same directory:
   - `index.html`
   - `style.css`
   - `script.js`
   - `ngrok.exe` (for Windows)

### Configuration

1. **Update Facebook App ID**:
   - Open `script.js`
   - Update the `APP_ID` constant with your Facebook App ID:
   ```javascript
   const APP_ID = 'YOUR_APP_ID_HERE';
   ```

2. **Configure Facebook App**:
   - Go to [Facebook Developers](https://developers.facebook.com/)
   - Create a new app or use an existing one
   - Add your ngrok HTTPS URL to "Valid OAuth Redirect URIs"
   - Ensure the app is in development mode or add test users

## 🏃 Running the Application

### Step 1: Start Local Server

**Using Python:**
```bash
python -m http.server 8000
```

**Using Node.js:**
```bash
npx http-server -p 8000
```

### Step 2: Create HTTPS Tunnel with ngrok

Since Facebook login requires HTTPS, you need to create a secure tunnel:

```bash
ngrok.exe http 8000
```

Or if using ngrok from command line:
```bash
ngrok http 8000
```

### Step 3: Access the Application

1. Copy the HTTPS URL from ngrok (e.g., `https://abc123.ngrok.io`)
2. Open that URL in your browser
3. The application will load and you can test Facebook login

## 📁 Project Structure

```
FB Demo/
├── index.html          # Main HTML structure
├── style.css           # Complete styling with theme support
├── script.js           # Facebook authentication logic
├── ngrok.exe           # HTTPS tunneling tool
└── README.md           # This file
```

## 🎯 Usage

1. **Login**: Click the "Login with Facebook" button
2. **Authorize**: You'll be redirected to Facebook to authorize the app
3. **View Profile**: After successful login, your profile information will be displayed
4. **Logout**: Click the "Log out" button to sign out
5. **Theme Toggle**: Use the moon/sun icon in the header to switch between light and dark themes

## 🔧 Technical Details

### Technologies Used

- **HTML5**: Semantic markup
- **CSS3**: Modern styling with CSS variables, animations, and glassmorphism
- **JavaScript**: Facebook SDK integration
- **Facebook SDK v19.0**: For authentication

### Key Features Implementation

- **Theme System**: CSS variables for easy theme switching
- **LocalStorage**: Saves theme preference
- **Facebook SDK**: Handles authentication and user data fetching
- **Responsive Design**: Mobile-first approach with media queries

### Facebook SDK Configuration

The app uses:
- **App ID**: Configured in `script.js`
- **Permissions**: `public_profile,email`
- **Auth Type**: `reauthenticate` (forces account selection dialog)
- **SDK Version**: v19.0

## ⚠️ Important Notes

1. **HTTPS Required**: Facebook SDK requires HTTPS. Always use ngrok or another HTTPS tunnel for testing.
2. **App Configuration**: Make sure your Facebook App settings match your ngrok URL.
3. **Development Mode**: The app must be in development mode or have test users added in Facebook Developer Console.
4. **Browser Console**: Check the browser console for any errors if login fails.

## 🐛 Troubleshooting

### "This app must be opened using the HTTPS ngrok URL"
- Make sure you're accessing the app through the ngrok HTTPS URL, not `localhost:8000`

### Login button doesn't work
- Verify your APP_ID is correct in `script.js`
- Check that your ngrok URL is added to Facebook App settings
- Ensure the app is not blocked by ad blockers

### Theme not persisting
- Check browser localStorage support
- Clear browser cache and try again

## 📝 License

This project is for educational purposes.

## 👨‍💻 Development

### Customization

- **Colors**: Modify CSS variables in `style.css` to change the color scheme
- **Animations**: Adjust animation timings in the `@keyframes` rules
- **Layout**: Modify the HTML structure in `index.html` and corresponding CSS

### Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## 🔐 Security

- Never commit your Facebook App ID to public repositories
- Always use HTTPS in production
- Validate user data on the server side in production applications
- This is a demo application - add proper security measures for production use

---

**Note**: This is a demo application. For production use, implement proper server-side validation and security measures.

