# Quick Deployment Guide

## 🚀 Choose Your Deployment Method

### 1. Docker (Recommended for Production)

**One-line deployment:**
```bash
docker-compose up -d
```

Or manually:
```bash
docker build -t edge-ai-docs .
docker run -p 3000:3000 edge-ai-docs
```

### 2. Render (Free tier available)

1. Fork this repository
2. Go to [Render Dashboard](https://dashboard.render.com/)
3. Click "New +" → "Web Service"
4. Connect your repository
5. Render auto-detects `render.yaml` → Click "Apply"
6. Your app will be live in minutes!

### 3. Railway (Free tier available)

1. Fork this repository
2. Go to [Railway](https://railway.app/)
3. Click "New Project" → "Deploy from GitHub repo"
4. Select your forked repository
5. Railway auto-detects `railway.json` → Click "Deploy"
6. Your app will be live!

### 4. Vercel (Static deployment)

**Via CLI:**
```bash
npm i -g vercel
vercel
```

**Via Dashboard:**
1. Go to [Vercel Dashboard](https://vercel.com/dashboard)
2. Import your repository
3. Configure: Build Command = `pnpm run build`
4. Deploy!

**Note:** Vercel deployment is static-only (frontend). The `/health` endpoint will not be available.

### 5. Manual Deployment (Any Node.js host)

```bash
# Install dependencies
pnpm install --frozen-lockfile

# Build
pnpm run build

# Set environment variables
export NODE_ENV=production
export PORT=3000

# Start
pnpm start
```

## 🔧 Environment Variables

Only needed if you want to enable analytics:

```env
VITE_ANALYTICS_ENDPOINT=your-analytics-endpoint
VITE_ANALYTICS_WEBSITE_ID=your-website-id
```

## ✅ Deployment Checklist

- [ ] Choose deployment platform
- [ ] Fork/clone repository
- [ ] Configure environment variables (optional)
- [ ] Deploy using one of the methods above
- [ ] Verify deployment is working
- [ ] Set up custom domain (optional)

## 🔍 Verify Deployment

After deployment, visit your app URL and check:
- Home page loads correctly
- Navigation works (/, /docs)
- No console errors
- Responsive design works on mobile

## 🆘 Troubleshooting

**Build fails:**
- Ensure Node.js 22+ is available
- Check if pnpm is installed
- Verify all dependencies are resolved

**App doesn't start:**
- Check if port 3000 is available
- Verify NODE_ENV is set to "production"
- Check server logs for errors

**404 errors:**
- Ensure static files are served correctly
- Check if dist/public directory exists
- Verify routing configuration

## 📚 Need Help?

See the full [README.md](./README.md) for detailed documentation.
