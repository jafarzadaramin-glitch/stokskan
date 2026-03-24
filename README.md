# StokSkan — Railway + Firebase Deploy Təlimatı

## Addım 1: Firebase Layihəsi Yarat

1. **console.firebase.google.com** → "Add project"
2. Layihə adı: `stokskan` (istədiyiniz ad)
3. Google Analytics: əlavə etməyə bilərsiniz → "Create project"

### Firestore aktiv et:
- Sol menyu → **Firestore Database** → "Create database"
- **Start in test mode** seçin → Next → Region: `europe-west` → Done

### Firebase konfiqurasiyasını al:
- Sol menyu → ⚙️ **Project Settings** → "Your apps" → `</>` (Web) ikonuna bas
- App nickname: `stokskan-web` → "Register app"
- **firebaseConfig** obyektini kopyala

---

## Addım 2: index.html-i yenilə

`templates/index.html` faylında bu hissəni tapın:

```javascript
const firebaseConfig = {
  apiKey: "BURAYA_API_KEY",
  authDomain: "BURAYA_AUTH_DOMAIN",
  projectId: "BURAYA_PROJECT_ID",
  ...
};
```

Öz konfiqurasiyanız ilə əvəz edin.

---

## Addım 3: GitHub-a yüklə

```bash
git init
git add .
git commit -m "stokskan init"
```

GitHub.com → New repository → `stokskan` → Create

```bash
git remote add origin https://github.com/SIZIN_AD/stokskan.git
git push -u origin main
```

---

## Addım 4: Railway Deploy

1. **railway.app** → "Start a New Project" → "Deploy from GitHub repo"
2. `stokskan` repo-sunu seçin
3. Deploy avtomatik başlayır ✅

### Domain al:
- Railway dashboard → layihəniz → **Settings** → **Networking**
- "Generate Domain" → `stokskan-xxx.railway.app`

---

## Nəticə

`https://stokskan-xxx.railway.app` — istənilən cihazdan, istənilən yerden işləyir!

Məlumatlar Firebase Firestore-da saxlanır — telefon, kompüter, hər yerdən eyni data görünür.
