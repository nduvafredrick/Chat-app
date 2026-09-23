# Ephemeral chat

This repository contains a Vercel serverless chat app in `vercel-chat-app/`.

## Deploy to Vercel

The root `vercel.json` maps the nested API and static files into the URL paths expected by the browser, so importing this repository directly into Vercel works.

Add the variables from [`vercel-chat-app/.env.example`](vercel-chat-app/.env.example) to the Vercel project before creating a room. `UPSTASH_REDIS_REST_URL`, `UPSTASH_REDIS_REST_TOKEN`, `ROOM_LINK_SECRET`, and `ABLY_API_KEY` are required. The S3/R2 variables are required only for file uploads.

## Run locally

```bash
cd vercel-chat-app
npm install
cp .env.example .env
npx vercel dev
```

Rooms are stored in Upstash Redis, realtime delivery uses Ably, and files are uploaded directly to S3/R2 using presigned URLs.
