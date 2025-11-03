# 🔥 MemeForge - AI-Generated Meme Studio

**An intelligent meme generator powered by OpenAI's GPT-4 and DALL-E 3.**

Create viral-worthy memes in seconds! Simply enter a topic, and MemeForge generates three unique memes with AI-generated images and witty captions in classic meme format.

![MemeForge Banner](https://img.shields.io/badge/Status-Production%20Ready-brightgreen) ![Next.js](https://img.shields.io/badge/Next.js-14-black) ![TypeScript](https://img.shields.io/badge/TypeScript-5.3-blue) ![Tailwind](https://img.shields.io/badge/Tailwind-3.4-38bdf8)

## ✨ Features

### Core Features
- 🤖 **AI-Powered Generation**: Uses GPT-4 for caption writing and DALL-E 3 for image generation
- 🎨 **Classic Meme Format**: Impact font with black outline, white text - just like the classics
- 🎭 **Multiple Variations**: Generates 3 unique memes per request with different angles
- 📱 **Responsive Design**: Beautiful UI that works on desktop, tablet, and mobile
- ⚡ **Real-time Preview**: Canvas-based rendering with instant preview
- 💾 **Download & Share**: Easy download and copy-to-clipboard functionality

### Personalization Features
- 🎯 **Humor Tone Control**: Choose from sarcastic, wholesome, edgy, absurd, or professional
- 📝 **Caption Style**: Classic, modern, or minimalist text layouts
- 🖼️ **Image Style**: Realistic, cartoon, abstract, or photographic visuals
- 💾 **Preference Memory**: Your settings are saved locally for future sessions

### Developer Features
- 🔐 **Type-Safe**: Full TypeScript implementation
- 🎨 **Modern Stack**: Next.js 14 (App Router), React 18, Tailwind CSS
- 🔄 **API Routes**: Clean separation between frontend and backend
- 📦 **Modular Components**: Reusable, well-organized component structure

---

## 🚀 Quick Start

### Prerequisites

- **Node.js 18+** and npm/yarn/pnpm
- **OpenAI API Key** ([Get one here](https://platform.openai.com/api-keys))

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/jgold-code/MemeGenerator.git
cd MemeGenerator
```

2. **Install dependencies**
```bash
npm install
# or
yarn install
# or
pnpm install
```

3. **Set up environment variables**
```bash
cp .env.example .env
```

Edit `.env` and add your OpenAI API key:
```env
OPENAI_API_KEY=sk-your-actual-api-key-here
```

4. **Run the development server**
```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```

5. **Open your browser**

Navigate to [http://localhost:3000](http://localhost:3000)

---

## 📖 Usage

### Basic Usage

1. **Enter a Topic**: Type any topic in the input box (e.g., "founder life", "debugging at 3am")
2. **Customize (Optional)**: Expand the preferences panel to adjust humor tone and style
3. **Generate**: Click "Generate Memes" and wait for the AI magic
4. **Download/Share**: Use the buttons on each meme card to download or copy to clipboard

### Example Topics

- `founder life` - Startup and entrepreneurship humor
- `late-night debugging` - Developer struggles
- `coffee addiction` - Caffeine-dependent life
- `monday morning` - Work week blues
- `procrastination` - The art of avoiding work
- `gym motivation` - Fitness humor
- `cat behavior` - Feline chaos

---

## 🏗️ Project Structure

```
MemeGenerator/
├── app/
│   ├── api/
│   │   └── generate-memes/
│   │       └── route.ts          # API endpoint for meme generation
│   ├── globals.css               # Global styles and meme text styling
│   ├── layout.tsx                # Root layout with providers
│   └── page.tsx                  # Main page component
├── components/
│   ├── LoadingAnimation.tsx      # Loading state UI
│   ├── MemeCard.tsx              # Individual meme card with canvas rendering
│   ├── MemeGallery.tsx           # Grid layout for meme display
│   └── PreferencesPanel.tsx      # User preferences UI
├── lib/
│   ├── contexts/
│   │   └── UserPreferencesContext.tsx  # React Context for preferences
│   ├── utils/
│   │   └── memeRenderer.ts       # Canvas rendering utilities
│   └── types.ts                  # TypeScript type definitions
├── public/                        # Static assets
├── .env.example                   # Environment variables template
├── next.config.js                # Next.js configuration
├── tailwind.config.ts            # Tailwind CSS configuration
├── tsconfig.json                 # TypeScript configuration
└── package.json                  # Dependencies and scripts
```

### Key Files Explained

#### `app/api/generate-memes/route.ts`
- Handles POST requests for meme generation
- Calls OpenAI GPT-4 for caption generation
- Calls DALL-E 3 for image generation
- Returns structured meme data

#### `components/MemeCard.tsx`
- Renders individual memes using HTML5 Canvas
- Overlays text with Impact font styling
- Handles download and clipboard copy

#### `lib/contexts/UserPreferencesContext.tsx`
- Manages user preferences (humor tone, style, etc.)
- Persists to localStorage
- Provides React hooks for easy access

#### `lib/utils/memeRenderer.ts`
- Utility functions for canvas text rendering
- Text wrapping and positioning logic
- Image loading helpers

---

## 🔧 Configuration

### Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `OPENAI_API_KEY` | Yes | Your OpenAI API key for GPT-4 and DALL-E 3 |

### Customization

#### Changing Image Dimensions

Edit `app/api/generate-memes/route.ts`:
```typescript
size: '1024x1024',  // Change to '1792x1024' for wide format
```

#### Adding New Humor Tones

1. Update `lib/types.ts`:
```typescript
humorTone: 'sarcastic' | 'wholesome' | 'edgy' | 'absurd' | 'professional' | 'yourNewTone'
```

2. Update `app/api/generate-memes/route.ts`:
```typescript
const toneDescriptions = {
  // ... existing tones
  yourNewTone: 'description of your tone',
}
```

3. Update `components/PreferencesPanel.tsx` to add the button

---

## 🎨 Styling

MemeForge uses Tailwind CSS for styling with a custom dark theme:

- **Primary Colors**: Purple, Pink, Cyan gradients
- **Background**: Dark slate with gradient overlays
- **Font**: Impact for meme text, system fonts for UI
- **Animations**: Custom pulse and bounce animations

### Meme Text Styling

The classic meme text effect is achieved with:
- White fill color
- Black text stroke (outline)
- Impact font family
- ALL CAPS transformation
- Multi-layer shadows for depth

---

## 🚢 Deployment

### Vercel (Recommended)

1. Push your code to GitHub
2. Import the project in [Vercel](https://vercel.com)
3. Add `OPENAI_API_KEY` to environment variables
4. Deploy!

### Other Platforms

MemeForge is a standard Next.js app and can be deployed to:
- **Netlify**
- **AWS Amplify**
- **Railway**
- **DigitalOcean App Platform**
- **Self-hosted** with Node.js

Build command: `npm run build`  
Start command: `npm run start`

---

## 💡 Future Extensions

### Feature Ideas

1. **Multi-User Support**
   - User authentication (NextAuth.js)
   - Save meme history to database (Supabase/PostgreSQL)
   - Public meme gallery

2. **Trending Meme Leaderboard**
   - Upvote/downvote system
   - Most popular topics tracking
   - Viral meme analytics

3. **Style Fine-Tuning**
   - Custom meme templates
   - Font customization (size, family, color)
   - Advanced text positioning
   - Multiple text overlays

4. **Social Features**
   - Direct share to Twitter, Instagram, Reddit
   - Meme collections/folders
   - Collaborative meme creation

5. **Advanced AI**
   - GPT-4 Vision for analyzing uploaded images
   - Style transfer between memes
   - Automatic template detection
   - Trending topic suggestions

6. **Business Features**
   - Watermark options
   - Bulk generation
   - API access for developers
   - Premium templates

### Technical Improvements

- **Caching**: Redis cache for repeated topics
- **Queue System**: Bull/BullMQ for high-load scenarios
- **Image Optimization**: CDN integration (Cloudinary/imgix)
- **Analytics**: PostHog/Mixpanel for usage tracking
- **A/B Testing**: Test different caption styles
- **Progressive Web App**: Offline support

---

## 📚 API Reference

### POST `/api/generate-memes`

Generate three memes based on a topic and user preferences.

**Request Body:**
```typescript
{
  topic: string
  preferences: {
    humorTone: 'sarcastic' | 'wholesome' | 'edgy' | 'absurd' | 'professional'
    captionStyle: 'classic' | 'modern' | 'minimalist'
    imageStyle: 'realistic' | 'cartoon' | 'abstract' | 'photographic'
    favoriteTopics: string[]
  }
}
```

**Response:**
```typescript
{
  memes: [
    {
      id: string
      imageUrl: string
      caption: string
      topText: string
      bottomText: string
      topic: string
      timestamp: number
    }
  ]
}
```

**Error Response:**
```typescript
{
  error: string
}
```

---

## 🛠️ Tech Stack

- **Framework**: [Next.js 14](https://nextjs.org/) (App Router)
- **Language**: [TypeScript](https://www.typescriptlang.org/)
- **Styling**: [Tailwind CSS](https://tailwindcss.com/)
- **AI**: [OpenAI GPT-4](https://openai.com/) & [DALL-E 3](https://openai.com/dall-e-3)
- **Canvas**: HTML5 Canvas API
- **State Management**: React Context API
- **Storage**: localStorage (client-side)

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

Copyright © 2025 Anysphere Inc.

---

## 🙏 Acknowledgments

- OpenAI for GPT-4 and DALL-E 3
- The meme community for endless inspiration
- Impact font creators (still the GOAT)
- Vercel for Next.js and hosting platform

---

## 📧 Support

Having issues? Want to share your memes?

- **Issues**: [GitHub Issues](https://github.com/jgold-code/MemeGenerator/issues)
- **Discussions**: [GitHub Discussions](https://github.com/jgold-code/MemeGenerator/discussions)

---

## 🎉 Demo

Try it live: [MemeForge Demo](https://your-deployment-url.vercel.app)

---

Made with 🔥 by creative developers who appreciate good memes.

**Now go forth and generate some legendary memes!** 🚀

