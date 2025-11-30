# cf_ai_agents

An AI chat agent built on Cloudflare Workers. Chat with an AI that can check weather, tell time, and schedule tasks.

## What it does

This is a chat interface powered by OpenAI's GPT-4 that runs on Cloudflare's network. The agent can:

- Answer questions and have conversations
- Check weather in any city (asks for your approval first)
- Tell you the local time anywhere
- Schedule tasks for later (one-time, delayed, or recurring with cron)
- List and cancel scheduled tasks
- Remember your conversation history

## Tech stack

- Cloudflare Workers - runs the backend
- Durable Objects - keeps state and chat history
- OpenAI GPT-4 - powers the AI responses
- React - builds the UI
- Vite - bundles everything
- TypeScript - types the code

## Running it locally

1. Get your OpenAI API key from https://platform.openai.com

2. Clone this repo and install:
```bash
cd agents-starter
npm install
```

3. Add your API key:
Create `.dev.vars` file:
```
OPENAI_API_KEY=your-api-key-here
```

4. Start it up:
```bash
npm start
```

5. Open http://localhost:5173

That's it. The chat interface should load and you can start talking to the agent.

## Try these commands

Once it's running, try asking:

- "What's the weather in Tokyo?"
- "What time is it in London?"
- "Schedule a reminder in 30 seconds"
- "Schedule a daily task at 9am"
- "Show me my scheduled tasks"

## How it works

The agent runs on Cloudflare Workers with a few key parts:

**src/server.ts** - Main agent class that handles chat messages and executes scheduled tasks

**src/tools.ts** - Tools the AI can use (weather, time, scheduling)

**src/app.tsx** - React chat UI

**wrangler.jsonc** - Cloudflare config

When you send a message, it goes to the Worker which calls OpenAI's API. The AI decides which tools to use and streams back the response in real time.

Some tools run automatically (like getting the time). Others ask for your approval first (like checking weather). You can add your own tools by editing tools.ts.

## Deploying to Cloudflare

1. Install Wrangler and login:
```bash
npm install -g wrangler
wrangler login
```

2. Add your API key to production:
```bash
wrangler secret put OPENAI_API_KEY
```

3. Deploy:
```bash
npm run deploy
```

Your agent will be live on Cloudflare's network.

## Adding new tools

Open `src/tools.ts` and add a new tool:

```typescript
const yourTool = tool({
  description: "what your tool does",
  inputSchema: z.object({
    param: z.string()
  }),
  execute: async ({ param }) => {
    // your code here
    return "result";
  }
});
```

Add it to the exports:
```typescript
export const tools = {
  getWeatherInformation,
  getLocalTime,
  scheduleTask,
  getScheduledTasks,
  cancelScheduledTask,
  yourTool  // add here
} satisfies ToolSet;
```

If you want the tool to ask for approval before running, leave out the `execute` function and add it to `executions` instead:

```typescript
export const executions = {
  getWeatherInformation: async ({ city }: { city: string }) => {
    return `The weather in ${city} is sunny`;
  },
  yourTool: async ({ param }) => {
    // runs after user approves
    return "result";
  }
};
```

## Project structure

```
src/
  server.ts       - Agent logic
  tools.ts        - Tool definitions
  app.tsx         - Chat UI
  client.tsx      - App entry point
  utils.ts        - Helper functions
  components/     - UI components
wrangler.jsonc    - Cloudflare config
vite.config.ts    - Build config
```

## License

MIT
