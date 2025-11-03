# 🚀 Quick Setup Guide

## Prerequisites Check

Before starting, ensure you have:

- ✅ **Node.js 18 or higher** - Run `node --version`
- ✅ **npm, yarn, or pnpm** - Run `npm --version`
- ✅ **OpenAI API Key** - Get one at https://platform.openai.com/api-keys

---

## 5-Minute Setup

### Step 1: Install Dependencies

```bash
npm install
```

This installs all required packages including:
- Next.js 14
- React 18
- TypeScript
- Tailwind CSS
- OpenAI SDK

### Step 2: Configure Environment

Create a `.env` file in the root directory:

```bash
# On macOS/Linux
echo "OPENAI_API_KEY=your_actual_api_key_here" > .env

# On Windows
echo OPENAI_API_KEY=your_actual_api_key_here > .env
```

**Important**: Replace `your_actual_api_key_here` with your real OpenAI API key!

### Step 3: Run Development Server

```bash
npm run dev
```

### Step 4: Open in Browser

Navigate to: **http://localhost:3000**

---

## Troubleshooting

### "OpenAI API key not configured"

**Problem**: The API key is not set or incorrect.

**Solution**:
1. Check that `.env` file exists in the project root
2. Verify the format: `OPENAI_API_KEY=sk-...`
3. No quotes needed around the key
4. Restart the dev server after changing `.env`

### "Module not found" errors

**Problem**: Dependencies not installed properly.

**Solution**:
```bash
rm -rf node_modules package-lock.json
npm install
```

### Port 3000 already in use

**Problem**: Another application is using port 3000.

**Solution**:
```bash
# Kill the process on port 3000
lsof -ti:3000 | xargs kill

# Or run on a different port
npm run dev -- -p 3001
```

### TypeScript errors

**Problem**: Type checking issues.

**Solution**:
```bash
# Restart TypeScript server in your IDE
# Or run type check manually
npx tsc --noEmit
```

### Canvas-related errors

**Problem**: Canvas package installation failed.

**Solution**:
```bash
# On macOS, you might need:
brew install pkg-config cairo pango libpng jpeg giflib librsvg

# Then reinstall
npm install canvas
```

---

## Verification Checklist

After setup, verify everything works:

- [ ] Development server starts without errors
- [ ] Homepage loads at http://localhost:3000
- [ ] Input field accepts text
- [ ] Preferences panel opens and closes
- [ ] No console errors in browser DevTools
- [ ] `.env` file exists with valid API key

---

## Cost Estimation

Each meme generation costs approximately:
- **GPT-4 API call**: ~$0.001 (for captions)
- **DALL-E 3 API calls**: ~$0.04 × 3 = ~$0.12 (for images)
- **Total per generation**: ~$0.12

With $5 credit, you can generate approximately **40 sets** (120 memes).

---

## Next Steps

Once setup is complete:

1. **Generate your first meme**: Try "founder life" or "debugging at 3am"
2. **Customize preferences**: Set your humor tone and image style
3. **Share your creations**: Download and share your favorite memes
4. **Read the docs**: Check out README.md for advanced features

---

## Getting Help

- **Documentation**: See [README.md](README.md)
- **Architecture**: See [ARCHITECTURE.md](ARCHITECTURE.md)
- **Issues**: [GitHub Issues](https://github.com/jgold-code/MemeGenerator/issues)

---

Happy meme making! 🔥

