# Basic English — APK Build (via GitHub)

Is folder mein wo sab files hain jo aap ko GitHub par upload karni hain taake
GitHub khud aap ki APK bana de — bina kisi computer par Android Studio install
kiye.

## Steps

1. **GitHub par naya repository banayein** (jaise `basic-english-apk`), public ya
   private, dono chalega.

2. **Is poore folder ki files us repository mein upload kar dein**, isi structure
   ke sath:
   ```
   basic-english-apk/
     package.json
     capacitor.config.json
     www/
       index.html
     .github/
       workflows/
         build-apk.yml
   ```

3. Repository ke andar, GitHub ki website par upar **"Actions"** tab par click
   karein. Wahan "Build APK" workflow dikhega — usay ek dafa manually run karein
   (Actions tab > Build APK > "Run workflow" button).

4. Build complete hone ke baad (2-4 minute lagte hain), usi workflow run ke
   neeche **"Artifacts"** section mein `basic-english-apk` naam ki file milegi —
   usay download kar lein, andar `app-debug.apk` hogi. Yehi aap ki APK hai.

5. Us APK ko apne Android phone mein bhej kar install kar lein (Unknown Sources
   allow karna par sakta hai).

## Unlock Code

App mein ek lock screen lagi hui hai. Default unlock code hai:

```
BASIC2026
```

Ye code sirf unhi logon ko dein jinhein aap access dena chahti hain. Ek dafa
sahi code dalne ke baad, us phone par app hamesha ke liye unlock rehti hai.

Agar aap code badalna chahen, `www/index.html` file kholein, is line ko dhoondein:

```js
const UNLOCK_CODE = "BASIC2026";
```

aur `"BASIC2026"` ki jagah apna naya code likh dein, phir dobara GitHub par
upload karke Actions se naya build chala dein.

## Note

- App poori tarah offline chalti hai (koi internet zaroori nahi, sirf pehli
  dafa APK install karne ke liye internet chahiye hoga jaisa kisi bhi app ke
  liye hota hai).
- Mic (bol kar jawab dena) APK ke andar kaam kare ya nahi ye WebView ki
  microphone permission par depend karta hai — agar zaroori ho to
  `capacitor.config.json` mein permissions add ki ja sakti hain.
