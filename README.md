# Aarush Jagannathan - Portfolio Website

A modern, animated portfolio website built with React, TypeScript, Tailwind CSS, and GSAP.

![Portfolio Preview](./public/profile-hero.jpg)

## 🚀 Live Demo

[View Live Site](https://your-github-username.github.io/your-repo-name)

## ✨ Features

- **Modern Design** - Dark theme with glassmorphism effects and gradient accents
- **Smooth Animations** - GSAP-powered scroll animations and transitions
- **Responsive Layout** - Works perfectly on desktop, tablet, and mobile devices
- **Interactive Components** - Flip cards, animated skill bars, timeline, and more
- **Fast Performance** - Optimized build with Vite

## 🛠️ Tech Stack

- **Framework:** React 18 + TypeScript
- **Build Tool:** Vite
- **Styling:** Tailwind CSS
- **Animations:** GSAP (GreenSock Animation Platform)
- **Icons:** Lucide React
- **UI Components:** shadcn/ui

## 📁 Project Structure

```
├── public/              # Static assets (images, fonts)
├── src/
│   ├── sections/        # Page sections (Hero, About, Skills, etc.)
│   ├── components/ui/   # Reusable UI components
│   ├── hooks/           # Custom React hooks
│   ├── App.tsx          # Main application component
│   └── index.css        # Global styles
├── dist/                # Production build output
├── index.html           # HTML entry point
├── vite.config.ts       # Vite configuration
├── tailwind.config.js   # Tailwind CSS configuration
└── package.json         # Dependencies and scripts
```

## 🚀 Getting Started

### Prerequisites

- Node.js 18+ 
- npm or yarn

### Installation

1. Clone the repository:
```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

4. Open [http://localhost:5173](http://localhost:5173) in your browser.

## 📦 Building for Production

```bash
npm run build
```

The production files will be in the `dist/` folder.

## 🌐 Deploying to GitHub Pages

### Method 1: Using GitHub Actions (Recommended)

1. Push your code to GitHub
2. Go to **Settings** → **Pages** in your repository
3. Under "Build and deployment", select **GitHub Actions**
4. Create a new workflow file `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [main]

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: 'pages'
  cancel-in-progress: true

jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Setup Node
        uses: actions/setup-node@v4
        with:
          node-version: 20
      - name: Install dependencies
        run: npm ci
      - name: Build
        run: npm run build
      - name: Setup Pages
        uses: actions/configure-pages@v4
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: './dist'
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

5. Commit and push the workflow file
6. GitHub Actions will automatically build and deploy your site

### Method 2: Manual Deployment

1. Build the project:
```bash
npm run build
```

2. Push the `dist` folder to the `gh-pages` branch:
```bash
npm run deploy
```

Or manually:
```bash
git subtree push --prefix dist origin gh-pages
```

3. Go to **Settings** → **Pages** and select the `gh-pages` branch as the source

## 📝 Customization

### Updating Personal Information

Edit the following files to update your information:

| Section | File | What to Edit |
|---------|------|--------------|
| Hero | `src/sections/Hero.tsx` | Name, role, social links |
| About | `src/sections/About.tsx` | Bio, personal info (birthday, phone, email, etc.) |
| Skills | `src/sections/Skills.tsx` | Skill names, percentages, descriptions |
| Experience | `src/sections/Experience.tsx` | Job titles, companies, dates, bullet points |
| Education | `src/sections/Education.tsx` | Degrees, schools, CGPA, achievements |
| Contact | `src/sections/Contact.tsx` | Contact info, social links |

### Updating Images

Replace the images in the `public/` folder:
- `profile-hero.jpg` - Hero section profile picture
- `profile-about.jpg` - About section picture

### Changing Colors

Edit `tailwind.config.js` to customize the color scheme:
```javascript
colors: {
  purple: { DEFAULT: "#6B46C1", ... },
  blue: { DEFAULT: "#3B82F6", ... },
  pink: { DEFAULT: "#EC4899", ... },
}
```

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

Feel free to fork this project and customize it for your own portfolio!

## 📧 Contact

For any questions or suggestions, feel free to reach out:
- Email: aarushjagannathan@gmail.com
- LinkedIn: [aarush-jagannathan](https://linkedin.com/in/aarush-jagannathan)
- GitHub: [ItzGOLLY](https://github.com/ItzGOLLY)
