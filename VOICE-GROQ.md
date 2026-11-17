# Voice with Groq (optional)

OASIS turns your speech into text **on your computer** by default. That is private and works offline.

**Groq** is an online service that does the same job, often faster and more accurately. It is free
for normal use, but you need **your own key**. OASIS does not come with one.

> With Groq on, every recording is sent to `api.groq.com`. Use it only if you are fine with that.

## 1. Get a free key (about 3 minutes)

1. Go to **https://console.groq.com** and sign up (Google sign-in works).
2. In the menu, open **API Keys**.
3. Click **Create API Key**, give it any name (for example `OASIS`), and click **Submit**.
4. **Copy the key now.** It starts with `gsk_`. Groq shows it only once.

## 2. Put the key into OASIS

1. Open OASIS and go to **Voice**.
2. In **03 Speech to text**, click **Groq online**.
3. OASIS asks whether to send recordings to Groq. Click **Use Groq**.
4. Paste your key in the box and click **Save**.
5. Click **Test**. You should see that the key works.

Leave **"If Groq fails, use this computer"** on. Then voice still works when you are offline
or Groq is busy.

## 3. Try it

Click into a text box, hold your talk button, speak, let go.

## Good to know

- The key is stored protected by Windows, on your computer only. It is never written to the settings file.
- To stop using Groq, click **This computer** in **03 Speech to text**.
- To remove the key, clear the box and click **Remove**.
- Do not share your key. If you think someone has it, delete it on console.groq.com and create a new one.
