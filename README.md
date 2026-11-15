# Waddle

Learn web development five minutes a day, with a duck.

Waddle is a mobile app that teaches HTML and CSS through short lessons you build by hand. It works in English and Arabic.

## What's inside

- **Lessons**: step-by-step tasks (fill the blank, pick the tag, write the code) with a live preview of your page.
- **Waddle AI**: a duck tutor you can chat with, or ask about the lesson step you are on.
- **The pond**: lessons earn coins and eggs; hatch ducks, merge twins into stronger ducks, feed them bread. The pond follows the time of day.
- **Badges, streaks and a profile**, saved to your account.
- **Plans**: Free, Pro and Max, each with a daily AI message limit.

## Stack

React 18, TypeScript, Vite, Tailwind, Motion, Rive (the duck), the AI SDK, and Supabase (auth, Postgres, an Edge Function for the tutor). The Android app is a WebView wrapper with native Google sign-in in `android/`.

## Run it

```bash
bun install
cp .env.example .env   # fill in your Supabase project
bun run dev            # http://localhost:5174
bun test
```

Build the Android APK (needs the Android SDK and JDK 17):

```bash
npm run android:apk    # writes WaddleMobile.apk
```

## Backend

- `supabase/migrations`: the tables (progress, plans, daily AI usage, chats, avatars), all with row-level security.
- `supabase/functions/tutor`: the AI tutor. Set its model key as a Supabase secret: `supabase secrets set MODELFLARE_API_KEY=...`

The Android package id is still `com.bataa.app`, the app's original name; changing it means a new Google sign-in client.

## License

MIT
