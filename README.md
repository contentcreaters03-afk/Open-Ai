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

## Email + Chat Data Storage (Firebase Setup)

Ab app users se email lekar unki chats cloud mein save karti hai, jo tu dekh sakta hai.

### Step 1: Firebase project banayein
1. https://console.firebase.google.com pe jayein, naya project banayein (free)
2. Left menu se "Build > Firestore Database" > "Create database" > production mode > koi bhi region choose karein

### Step 2: Web app config lena
1. Project settings (gear icon) > "Your apps" > Web icon (`</>`) se naya web app add karein
2. Jo config object milega (apiKey, projectId, waghera), usay copy karein

### Step 3: index.html mein config daalein
`index.html` mein `firebaseConfig` object dhoondein (search karein "YOUR_API_KEY") aur apni real values daal dein.

### Step 4: Security Rules (zaroori — users ki privacy ke liye)
Firestore > Rules mein ye paste karein, taake users sirf apna data likh sakein, kisi ki bhi chats padh na sakein (sirf tu Firebase Console se sab dekh sakega):

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow create: if true;
      allow read, update, delete: if false;
    }
  }
}
```

### Data kahan dekhein
Firebase Console > Firestore Database > "messages" aur "users" collections mein sab emails aur conversations dikhengi (chronological order mein, filter/search bhi kar sakte hain).

### Important
- Ye dusron ka personal data hai (email + private messages) — isay securely rakhein, kisi ke saath share na karein, aur agar app public karein to ek chhota Privacy Policy page bhi add karna legally zyada safe hoga
- Firebase free tier mein 1GB storage aur 50k reads/day free hain — normal use ke liye kaafi hai
