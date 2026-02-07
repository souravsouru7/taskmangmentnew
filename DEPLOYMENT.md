# Task Management App - Deployment Guide

## Vercel Deployment Instructions

### 1. Prerequisites
- Make sure you have a Vercel account
- Install Vercel CLI: `npm install -g vercel`

### 2. Deploy using Vercel CLI
```bash
# Navigate to your project folder
cd taskfront

# Deploy to Vercel
vercel

# Follow the prompts:
# - Set up and deploy? Y
# - Which scope? (your account)
# - Link to existing project? N
# - What's your project's name? taskman-client
# - In which directory is your code located? ./
# - Want to override the settings? N
```

### 3. Environment Variables
Add these environment variables in your Vercel project settings:
- `REACT_APP_API_URL` = `https://api.jktaskmangement.online/api`

### 4. Automatic Deployment
- Push to your GitHub repository
- Connect GitHub to Vercel
- Vercel will automatically deploy on every push to main branch

### 5. Manual Deployment
```bash
# After initial setup
vercel --prod
```

## Files Added/Modified

### New Files:
- `vercel.json` - Vercel configuration
- `.env.production` - Production environment variables

### Modified:
- `package.json` - Added resolutions for dependency conflicts

## Troubleshooting

### Common Issues:
1. **Build fails**: Check the build logs in Vercel dashboard
2. **API calls fail**: Verify `REACT_APP_API_URL` is set correctly
3. **404 errors**: Make sure vercel.json routes are configured properly

### Security Notes:
- The remaining npm audit warnings are related to development dependencies and won't affect production
- The app uses HTTPS for API calls
- Environment variables are properly configured for production