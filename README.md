# Sishya School Assistant

Full-screen page hosting the LiveKit voice agent (embed widget) for the Sishya OMR School expo.

Live: https://sishya-school-assistant.vercel.app

The widget only loads on origins listed under the agent's Embed widget > Allowed origins in LiveKit Cloud.

## Agent setup (LiveKit Agent Builder)

- Type: Open ended
- Instructions: [agent/instructions.txt](agent/instructions.txt)
- Welcome message: [agent/welcome.txt](agent/welcome.txt), "Allow users to interrupt the greeting" on
- Pipeline mode: Realtime model
- Model: OpenAI GPT Realtime 2.1 (Google Gemini 3.8 Live returned 503 errors in October 2026)
- Voice: Marin
- Noise cancellation: Quail VF S

## Moving to another LiveKit account

1. In the new account, create a project, then Agents > new agent in the Agent Builder.
2. Copy in the settings above and click Deploy agent.
3. On the agent's Overview page, open the ⋮ menu > Embed web widget:
   add `https://sishya-school-assistant.vercel.app` to Allowed origins, switch the widget on, and save.
4. Copy the new agent ID (starts with `CA_`) from the embed code and replace `data-lk-agent` in `index.html`.
5. Push to `main`; Vercel redeploys automatically.
6. Switch the old account's widget off.
