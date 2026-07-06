# Configure a Model Provider

Now add the LLM that Obot will use. Obot supports several providers — this step uses **Anthropic** or **OpenAI** as examples, but the flow is the same for any supported provider.

## Step 1: Get an API Key

Create an API key with your chosen provider:

- **Anthropic** — [console.anthropic.com](https://console.anthropic.com/) → **API Keys**
- **OpenAI** — [platform.openai.com/api-keys](https://platform.openai.com/api-keys)

Copy the key — you'll paste it into Obot next.

## Step 2: Add the Provider in Obot

1. In the Obot admin UI, navigate to **Model Providers**
2. Click **Configure** next to your provider (e.g. **Anthropic** or **OpenAI**)
3. Paste your **API Key**
4. Click **Confirm**

Obot validates the key and loads the list of available models from that provider.

## Step 3: Select a Default Model

1. Still on the **Model Providers** page (or under **Models**), review the models that were loaded
2. Set a **default model** for chat (for example, a Claude or GPT model)
3. Save your selection

> You can configure more than one provider at a time and mix models across agents. The default model is what Obot's built-in chat uses unless you pick another.
