# Open Studio AI — Setup Guide
### Developed by Hasnain Sheikh

## Sabse bari khushkhabri
Ab koi OpenAI API key nahi chahiye, koi billing nahi, koi credit card nahi. App free AI engine (Puter.js) use karti hai jo bina key ke chalta hai.

## Pehli baar use karte waqt
Jab pehli dafa koi message bhejoge, ho sakta hai ek chhota sign-in popup aaye jahan free account bane (email/Google se, seconds ka kaam) — bas ek dafa hota hai, uske baad sab automatic chalta hai. Ye Puter ka apna free account hai, koi payment nahi mangega.

## Step 1: GitHub Pages pe deploy karna
1. GitHub.com pe naya repo banayein (e.g. `open-studio-ai`)
2. `index.html`, `manifest.json`, `sw.js` upload karein
3. Settings > Pages > Source = main branch, root
4. Link milega: `https://yourusername.github.io/open-studio-ai/`

## Step 2: Use karna
1. Link kholein
2. New chat se shuru karein — normal message likhein, ya image icon dabakar image describe karein
3. Voice input mic icon se

## Features
- Ek hi clean chat interface (ChatGPT jaisa), zyada dashboards nahi
- Sidebar mein chat history save hoti hai (device pe)
- Image generation isi chat ke andar
- Voice input
- Har AI reply pe Copy aur Read Aloud
- Jo language likhoge usi mein jawab milega, numbers hamesha English format mein
- Koi emoji nahi — sab professional SVG icons

## Icons (optional)
`manifest.json` mein `icon-192.png` aur `icon-512.png` chahiye — apna logo bana kar isi folder mein daal dein. Bina icon ke bhi app kaam karti hai.

## Agla level (jab chahein)
- Custom app icon aur splash screen
- Streaming responses (word-by-word typing)
- Export chat as PDF/text
- Different AI models select karne ka option (settings mein)
