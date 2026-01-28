# 🚀 Complete GitHub Setup Guide - Step by Step

Follow these exact steps to fork, clone, and set up the CA Monk Blog Application.

---

## 📋 Prerequisites

Make sure you have:
- ✅ GitHub account (https://github.com/signup)
- ✅ Git installed on your computer (https://git-scm.com/)
- ✅ Node.js v18+ (https://nodejs.org/)
- ✅ npm (comes with Node.js)

### Verify Installation

```bash
# Check Git
git --version
# Should show: git version X.X.X

# Check Node.js
node --version
# Should show: v18.X.X or higher

# Check npm
npm --version
# Should show: X.X.X
```

---

## Step 1️⃣: Fork the Repository on GitHub

### What is Forking?
Forking creates a copy of the project in YOUR GitHub account so you can modify it.

### How to Fork:

1. **Go to the Original Repository**
   - Open: https://github.com/CA-Monk/blog-app-react
   - (Or the URL where the project is hosted)

2. **Click the "Fork" Button**
   - Look at the top-right of the page
   - Click the **"Fork"** button
   - You'll see a small dropdown menu

3. **Configure Fork (if prompted)**
   - Owner: Select your GitHub username
   - Repository name: `blog-app-react` (keep default)
   - Description: (optional) "My blog application"
   - Click **"Create fork"**

4. **Wait for Forking to Complete**
   - GitHub will copy the repository
   - You'll be redirected to your forked copy
   - The URL will now show: `https://github.com/YOUR-USERNAME/blog-app-react`

✅ **Fork Complete!** You now have your own copy.

---

## Step 2️⃣: Clone Your Forked Repository

### What is Cloning?
Cloning downloads your forked repository to your local computer.

### How to Clone:

1. **Get Your Repository URL**
   - Go to your forked repository
   - Click the green **"Code"** button
   - Select **"HTTPS"** (default)
   - Click the copy icon next to the URL
   - URL looks like: `https://github.com/YOUR-USERNAME/blog-app-react.git`

2. **Open Terminal/Command Prompt**
   - **Windows:** Press `Win + R`, type `cmd`, press Enter
   - **Mac:** Press `Cmd + Space`, type `terminal`, press Enter
   - **Linux:** Open your terminal

3. **Navigate to Where You Want to Save**
   ```bash
   # Go to Documents folder
   cd Documents
   
   # Or create a projects folder
   mkdir projects
   cd projects
   ```

4. **Clone the Repository**
   ```bash
   git clone https://github.com/YOUR-USERNAME/blog-app-react.git
   ```
   Replace `YOUR-USERNAME` with your actual GitHub username.

5. **Wait for Cloning**
   - You'll see output like:
   ```
   Cloning into 'blog-app-react'...
   remote: Enumerating objects: 150, done.
   Receiving objects: 100% (150/150), done.
   ```

6. **Navigate into the Project**
   ```bash
   cd blog-app-react
   ```

✅ **Clone Complete!** The project is now on your computer.

---

## Step 3️⃣: Install Dependencies

### What is Installing?
Installing downloads all the required libraries the project needs.

```bash
# Make sure you're in the project folder
cd blog-app-react

# Install all dependencies
npm install
```

**What you'll see:**
```
added 350 packages in 45s
```

⏳ This may take 1-2 minutes the first time.

✅ **Installation Complete!** All packages are ready.

---

## Step 4️⃣: Set Up Environment Variables

### Create `.env.local` File

1. **Copy the Example File**
   ```bash
   # The file .env.example is included in the project
   # Copy it to create your own .env.local
   ```

2. **Create `.env.local` in Project Root**
   - Look for `.env.example` in the project folder
   - Copy its contents
   - Create a new file called `.env.local` in the same location
   - Paste the contents

3. **The `.env.local` File Should Contain:**
   ```
   VITE_API_URL=http://localhost:3001
   ```

✅ **Environment Setup Complete!**

---

## Step 5️⃣: Start the Development Server

### Run the Project

```bash
# Make sure you're in the project folder
cd blog-app-react

# Start both React and JSON Server
npm run dev:full
```

**What you'll see:**
```
  VITE v7.3.1  ready in 682 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
```

✅ **Servers Running!**

---

## Step 6️⃣: Open in Browser

### View Your App

1. **Copy the URL**
   - From the terminal output, copy: `http://localhost:5173/`

2. **Open Browser**
   - Open any web browser (Chrome, Firefox, Safari, Edge)
   - Paste the URL in the address bar
   - Press Enter

3. **See the App**
   - The blog application will load
   - Click on blog posts
   - Create new blog posts
   - See the animations work!

✅ **App is Running!**

---

## 🎉 You're All Set Up!

### What to Do Next:

#### Option A: Make Changes
```bash
# 1. Stop the server (in terminal, press Ctrl + C)
# 2. Make changes to the code
# 3. Run npm run dev:full again
# 4. Changes will auto-reload in browser
```

#### Option B: Push Changes to GitHub
```bash
# 1. Make your changes in the code
# 2. Check what changed
git status

# 3. Add all changes
git add .

# 4. Create a commit with message
git commit -m "Added my awesome feature"

# 5. Push to GitHub
git push
```

---

## 📝 Common Commands Reference

| Command | What It Does |
|---------|---|
| `npm install` | Install all dependencies |
| `npm run dev:full` | Start React + JSON Server |
| `npm run dev` | Start only React (dev mode) |
| `npm run server` | Start only JSON Server |
| `npm run build` | Create production build |
| `npm run lint` | Check code quality |
| `git status` | See what files changed |
| `git add .` | Stage all changes |
| `git commit -m "message"` | Save changes with message |
| `git push` | Upload changes to GitHub |
| `git pull` | Download latest changes |

---

## ❌ Troubleshooting

### Problem: "npm: command not found"
**Solution:** Install Node.js from https://nodejs.org/

### Problem: "Port 3001 already in use"
**Solution:** Kill the process or use different port
```bash
# Windows
netstat -ano | findstr :3001
taskkill /PID <number> /F

# Mac/Linux
lsof -i :3001
kill -9 <number>
```

### Problem: "git: command not found"
**Solution:** Install Git from https://git-scm.com/

### Problem: Dependencies not installing
**Solution:** Clear cache and try again
```bash
rm -rf node_modules
npm cache clean --force
npm install
```

### Problem: App doesn't load at localhost:5173
**Solution:** 
1. Check terminal for errors
2. Make sure npm run dev:full is still running
3. Try a different port: `npm run dev -- --port 5174`

### Problem: JSON Server not starting
**Solution:** Check if port 3001 is free
```bash
# Try manually starting
npm run server
```

---

## 📚 Project Structure

```
blog-app-react/
├── src/                    # Your code goes here
│   ├── components/        # React components
│   ├── hooks/            # Custom hooks
│   ├── lib/              # Utilities & API
│   ├── App.tsx           # Main app
│   └── index.css         # Styles
├── public/               # Static files
├── db.json               # Sample data
├── package.json          # Dependencies
├── README.md             # Project info
└── vite.config.ts        # Build config
```

---

## 🎯 Making Your First Change

### Add Your Own Blog Post:

1. **Open `db.json`** in text editor
2. **Add a new blog object:**
   ```json
   {
     "id": 4,
     "title": "My First Blog",
     "description": "This is my blog post",
     "category": ["JAVASCRIPT", "TUTORIAL"],
     "date": "2026-01-27",
     "coverImage": "https://images.pexels.com/photos/1181690/pexels-photo-1181690.jpeg",
     "content": "This is the content of my blog post..."
   }
   ```
3. **Save the file**
4. **Refresh the browser**
5. **Your new blog will appear!**

---

## ✅ Final Checklist

- [x] Fork repository on GitHub
- [x] Clone to local computer
- [x] Install dependencies with `npm install`
- [x] Create `.env.local` file
- [x] Run `npm run dev:full`
- [x] Open http://localhost:5173 in browser
- [x] See the blog app working
- [x] Test clicking on blogs
- [x] Try creating a new blog
- [x] Make a commit with `git commit -m "message"`
- [x] Push with `git push`

---

## 🚀 You're Ready!

You now have:
✅ Your own fork on GitHub  
✅ A local copy on your computer  
✅ All dependencies installed  
✅ App running locally  
✅ Ready to make changes  

**Start coding and have fun! 🎉**

---

## 📞 Need More Help?

Check these files in the project:
- `README.md` - Project overview
- `.env.example` - Environment setup
- `package.json` - Available scripts
- Source code comments - Code explanations

---

**Happy coding! 🚀**
