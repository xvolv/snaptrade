# Trade Forge

A comprehensive trading journal for crypto, forex, binary options, and more. Track your trades, analyze your performance, and improve your discipline with AI-powered insights.

## Features

- **Trade Tracking** - Log trades with entry/exit prices, position sizes, direction, and notes
- **Performance Analytics** - View equity curves, P&L breakdowns, win/loss ratios
- **Discipline Rules** - Set daily loss limits, max trade counts, and get alerts when rules are breached
- **Broker Connections** - Connect your brokerage accounts to import trades automatically
- **Calendar Heatmap** - Visualize your trading activity over time
- **Mistake Tracking** - Identify and learn from common trading mistakes

## Tech Stack

- **Frontend**: Next.js 16, React 19, Tailwind CSS 4
- **Database**: PostgreSQL (Neon) with Prisma ORM
- **Mobile**: Capacitor (Android WebView)
- **Charts**: Recharts

## Getting Started

### Prerequisites

- Node.js 18+
- PostgreSQL database (or use Neon serverless)
- npm or pnpm

### Installation

1. Clone the repository
2. Install dependencies:

```bash
npm install
```

3. Set up environment variables:

```bash
# Create .env file
cp .env.example .env
```

Configure your database URL in `.env`:

```env
DATABASE_URL="postgresql://user:password@host:5432/database"
```

4. Generate Prisma client:

```bash
npx prisma generate
```

5. Run database migrations:

```bash
npx prisma migrate dev
```

6. Start the development server:

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### Seeding Demo Data

To add sample trades for testing:

```bash
npm run db:seed
```

## Building for Android

This project uses Capacitor to build a native Android app.

### Prerequisites

- Android Studio
- Java JDK 17+
- Android SDK

### Build Steps

1. Sync Capacitor:

```bash
npx cap sync
```

2. Open in Android Studio:

```bash
npx cap open android
```

3. Build the APK in Android Studio (Build → Build Bundle(s) / APK(s) → Build APK)

Or build from command line:

```bash
cd android && ./gradlew assembleDebug
```

The APK will be at `android/app/build/outputs/apk/debug/app-debug.apk`

## Project Structure

```
trade-forge/
├── app/                    # Next.js App Router pages
│   ├── (dashboard)/         # Dashboard routes (with layout)
│   ├── api/                # API routes
│   └── globals.css         # Global styles
├── components/             # React components
│   ├── analytics/          # Chart components
│   ├── dashboard/          # Dashboard widgets
│   ├── layout/             # Header, sidebar, nav
│   ├── trade/              # Trade form components
│   └── trades/             # Trade list components
├── context/                # React Context providers
├── hooks/                  # Custom React hooks
├── lib/                    # Utility functions
└── prisma/                 # Database schema & migrations
```

## License

MIT
