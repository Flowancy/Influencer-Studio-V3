# AI Influencer Studio

Generate consistent AI influencer photos at scale — GPT-4o writes the prompt, Apixo Nano Banana 2 generates the image.

## Setup

1. Install the **Live Server** extension in VS Code (by Ritwick Dey)
2. Open this folder in VS Code
3. Right-click `index.html` → **Open with Live Server**

Or: `npx serve . -p 3000` → open http://localhost:3000

## How to use

1. Enter your **OpenAI API key** and **Apixo.ai API key**
2. Type the girl's **name** and upload her **avatar photo**
3. Upload all your **inspiration photos**
4. Hit **Generate Photos**

## What happens per photo

1. Avatar + inspiration photo sent to **GPT-4o** with this exact prompt:
   > "Can you write a json prompt for nano banana 2 to add [name] (first photo) to the second photo, instead of the girl on the second photo. But make sure [name] is wearing the same clothes as the girl on the second photo. Also make sure that the generation has the same face and the same hair as [name]. The photo must look like it was taken with an iphone 17 pro with lens 1x"

2. GPT-4o returns a JSON prompt → extracted and sent to Apixo

3. Apixo task submitted:
   - Model: `nano-banana-2`
   - Mode: `image-to-image`
   - Resolution: `1K`
   - Aspect ratio: `auto`
   - Output format: `png`

4. App polls every 3s until done → image appears in output panel

## API keys

- OpenAI: https://platform.openai.com/api-keys
- Apixo:  https://apixo.ai/dashboard/api-keys
