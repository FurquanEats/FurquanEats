# Mohammed Furquan

Full-stack engineer in Bengaluru, India. I design, build and ship software on my
own, end to end: the interface, the API, the database, the deployment, and
whatever breaks afterwards.

Five of the things I have built are being used by other people right now.

## Running

**[KOKOMATA](https://kokomata.com)** — a message left at a place can only be read
by walking there. The map never shows a pin, because the exact coordinates never
leave the server. React Native and Expo over Supabase Postgres with PostGIS,
built for Genki to Asia in Japan, shipping in Japanese and English.

**[Wheelness](https://wheelness.in)** — car washing by subscription for apartment
communities. Four role-based apps in one Next.js codebase, Razorpay billing, and
a task board that works in a basement with no signal. 200+ subscribers, 5,000+
cleans logged with a photo each.

**[Veynity](https://veynity.com)** — visitor parking tags for gated communities.
Scan the sticker on a guest car and the guard sees a report. One Cloudflare
Worker, no client framework, no bundler, 391 tests, and a written plan for how it
is allowed to fail.

**[Sleek Interio](https://sleekinterio.com)** — a cost calculator that keeps your
answers if you wander off mid-form, and hands a sales team a ranked list instead
of a pile of identical enquiries. Next.js and Express over Neon Postgres and
Redis.

**[Spotlight Furnishings](https://spotlight-furnishings.vercel.app)** — a carpet
shop in Srinagar, cash on delivery, run entirely from the owner's phone. Money in
whole paise, stock only through a ledger, and it cannot oversell.

## How I tend to build

The rules I care about end up in the database rather than in application code. A
check written in a function is a promise that everyone who touches that code
later remembers to make it, and for anything that cannot fail even once, that is
not good enough.

What that means in practice:

- KOKOMATA's true coordinates sit in a schema the client has no grants on at all.
  Eleven assertions prove a non-owner cannot read one, and they run as a gate
  after every change to the schema.
- Wheelness has four kinds of user sharing one set of tables. A query that
  forgets to say whose data it wants returns nothing, because Postgres refuses
  rather than guesses.
- Spotlight reduces stock only where there is enough left. Two people buying the
  last carpet in the same second cannot both succeed.

I also write down how a system is allowed to degrade before I write the system.
Veynity has eight rungs, from the server being gone to a missing phone number,
and nothing lower is permitted to take out anything above it.

## Tools

- **Web** — Next.js, React, TypeScript, Tailwind
- **Mobile** — React Native, Expo, MapLibre
- **Backend** — Node.js, Express, FastAPI, Python
- **Data** — PostgreSQL, PostGIS, Supabase, Neon, Prisma, Drizzle, Redis, Cloudflare D1
- **Rest** — Razorpay, Cloudflare Workers and R2, Sentry, GSAP and WebGL

## Open source

- **[Insight-Presenter](https://github.com/FurquanEats/Insight_Presenter)** —
  students submit a presentation video through a share link with no account.
  Three streams run in parallel behind FastAPI: Whisper for the transcript,
  MediaPipe for eye contact and gestures, Gemini for the rubric. An agent
  reconciles them into timestamped notes and a draft grade.
- **[emotion-detector-ai](https://github.com/FurquanEats/emotion-detector-ai)** —
  a CNN in TensorFlow and Keras for facial emotion recognition, holding above 85%
  accuracy at 20+ FPS on a live webcam, through to a Streamlit app.

## Elsewhere

Case studies, with the architecture written out: **[frqn.in](https://www.frqn.in)**

Available for work in Bengaluru, Hyderabad, across India and remotely worldwide:
**[frqn.in/hire](https://www.frqn.in/hire)**

<mohammedfurquan10010@gmail.com> · [LinkedIn](https://www.linkedin.com/in/furquaneats)

Studying for a BCA in Data Science at Chanakya University, Bengaluru, graduating
2027.
