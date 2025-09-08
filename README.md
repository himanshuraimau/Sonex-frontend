# 🎵 Sonex - AI-Powered Audio Generation Platform

Sonex is a modern web application that provides AI-powered audio generation services including text-to-speech synthesis, voice cloning, and sound effect generation. Built with cutting-edge technologies, Sonex offers multiple AI models for high-quality audio production.

## ✨ Features

- **🎤 Text-to-Speech**: Convert text to natural-sounding speech using StyleTTS2
- **🔄 Voice Cloning**: Clone voices using SeedVC technology
- **🎵 Audio Generation**: Create audio content with Make-an-Audio AI
- **👤 User Authentication**: Secure login/signup with NextAuth.js
- **💳 Credit System**: Manage user credits for audio generation
- **📱 Responsive Design**: Modern UI with Tailwind CSS
- **☁️ Cloud Storage**: AWS S3 integration for audio file storage
- **⚡ Background Processing**: Async audio generation with Inngest
- **📊 History Tracking**: Keep track of generated audio clips

## 🛠️ Tech Stack

- **Framework**: [Next.js 15](https://nextjs.org/) with App Router
- **Language**: TypeScript
- **Styling**: [Tailwind CSS](https://tailwindcss.com/)
- **Database**: SQLite with [Prisma ORM](https://prisma.io/)
- **Authentication**: [NextAuth.js](https://next-auth.js.org/)
- **State Management**: [Zustand](https://github.com/pmndrs/zustand)
- **Form Handling**: [React Hook Form](https://react-hook-form.com/) with Zod validation
- **Background Jobs**: [Inngest](https://www.inngest.com/)
- **Cloud Storage**: AWS S3
- **Package Manager**: Bun
- **Code Quality**: Biome (ESLint + Prettier alternative)

## 🚀 Getting Started

### Prerequisites

- [Bun](https://bun.sh/) (latest version)
- [Node.js](https://nodejs.org/) (18+ recommended)
- AWS Account (for S3 storage)
- API access to audio generation services

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/himanshuraimau/Sonext-frontend.git
   cd Sonext-frontend
   ```

2. **Install dependencies**
   ```bash
   bun install
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env
   ```
   
   Fill in the required environment variables in `.env`:
   ```bash
   # Authentication
   AUTH_SECRET="your-auth-secret"
   AUTH_DISCORD_ID="your-discord-id"
   AUTH_DISCORD_SECRET="your-discord-secret"
   
   # Database
   DATABASE_URL="file:./db.sqlite"
   
   # AWS Configuration
   AWS_ACCESS_KEY_ID="your-aws-access-key"
   AWS_SECRET_ACCESS_KEY="your-aws-secret-key"
   AWS_REGION="your-aws-region"
   S3_BUCKET="your-s3-bucket"
   
   # API Configuration
   API_KEY="your-api-key"
   BACKEND_API_KEY="your-backend-api-key"
   
   # External AI Services
   STYLETTS2_API_ROUTE="your-styletts2-api-url"
   SEED_VC_API_ROUTE="your-seedvc-api-url"
   MAKE_AN_AUDIO_API_ROUTE="your-make-audio-api-url"
   ```

4. **Set up the database**
   ```bash
   bun run db:push
   ```

5. **Start the development server**
   ```bash
   bun run dev
   ```

The application will be available at `http://localhost:3000`.

## 📜 Available Scripts

- `bun run dev` - Start development server with Turbo
- `bun run build` - Build the application for production
- `bun run start` - Start production server
- `bun run preview` - Build and start production server
- `bun run db:push` - Push database schema changes
- `bun run db:studio` - Open Prisma Studio
- `bun run db:generate` - Generate Prisma client and run migrations
- `bun run db:migrate` - Deploy database migrations
- `bun run check` - Run Biome linting and formatting checks
- `bun run check:write` - Fix linting and formatting issues
- `bun run typecheck` - Run TypeScript type checking

## 🏗️ Project Structure

```
src/
├── app/                    # Next.js App Router pages
│   ├── api/               # API routes
│   │   ├── auth/          # Authentication endpoints
│   │   └── inngest/       # Background job webhooks
│   ├── layout.tsx         # Root layout
│   └── page.tsx           # Home page
├── components/            # React components
│   └── client/           # Client-side components
│       ├── sound-effects/ # Sound effects components
│       └── speech-synthesis/ # Text-to-speech components
├── inngest/              # Background job definitions
├── lib/                  # Utility libraries
├── schemas/              # Zod validation schemas
├── server/               # Server-side code
│   ├── auth/             # Authentication configuration
│   └── db.ts             # Database client
├── stores/               # Zustand state stores
├── styles/               # Global styles
├── types/                # TypeScript type definitions
└── utils/                # Utility functions
```

## 🔧 Configuration

### Environment Variables

The application uses environment variables for configuration. All variables are validated using Zod schemas in `src/env.js`.

### Database Schema

The app uses Prisma with SQLite for data storage. Key models include:
- **User**: User accounts with credit system
- **GeneratedAudioClip**: Audio generation history
- **Account/Session**: NextAuth.js authentication models

### Audio Generation Services

Sonex integrates with multiple AI audio generation services:
- **StyleTTS2**: High-quality text-to-speech synthesis
- **SeedVC**: Voice conversion and cloning
- **Make-an-Audio**: General audio content generation

## 🚀 Deployment

### Vercel (Recommended)

1. Connect your GitHub repository to Vercel
2. Set up environment variables in Vercel dashboard
3. Deploy with automatic builds on push

### Manual Deployment

1. Build the application: `bun run build`
2. Start the production server: `bun run start`

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

---

Built with ❤️ by [Himanshu Raimau](https://github.com/himanshuraimau)
