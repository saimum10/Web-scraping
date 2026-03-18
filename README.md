# 🕷️ Web Scraping Pro v3

**একটি পূর্ণাঙ্গ OSINT ও Security Audit টুল — Termux/Kali Linux-এ চলে**

---

## 📋 সূচিপত্র

1. [টুলটি কী?](#টুলটি-কী)
2. [সব ফিচার](#সব-ফিচার)
3. [প্রথমবার সেটআপ](#প্রথমবার-সেটআপ)
4. [ব্যবহারের নিয়ম](#ব্যবহারের-নিয়ম)
5. [ট্যাব গাইড](#ট্যাব-গাইড)
6. [Advanced Settings](#advanced-settings)
7. [Export ফরম্যাট](#export-ফরম্যাট)
8. [সমস্যা ও সমাধান](#সমস্যা-ও-সমাধান)
9. [APK বানানো](#apk-বানানো)

---

## টুলটি কী?

Web Scraping Pro v3 হলো একটি **web-based application** যা যেকোনো ওয়েবসাইটের গভীর তথ্য বের করে আনতে পারে। এটি ব্রাউজারে চলে, তাই আলাদা কোনো জটিল সফটওয়্যার লাগে না।

**কোথায় চলে:** Termux (Android) • Kali Linux • যেকোনো Linux

---

## সব ফিচার

| ট্যাব | কী দেখায় |
|-------|-----------|
| 🌐 **HTML** | সব লিংক, ইমেজ URL, ফর্ম, ইমেইল ঠিকানা, ফোন নম্বর |
| 📋 **Meta/SEO** | Title, Description, Open Graph, Twitter Card, Schema.org |
| ⚙️ **JS Audit** | API Keys (Google, Firebase, AWS, Stripe), JWT Tokens, Live Stream URLs (m3u8, RTMP) |
| 🔌 **API Finder** | Hidden API endpoints, GraphQL queries, WebSocket URLs, XHR calls |
| 🍪 **Cookies** | Session token, Auth token, JWT decode, localStorage hints, CORS |
| 🔧 **Technology** | Framework (React/Vue/Angular), CMS, Library, Server (Nginx/Apache) — ৮০+ technology |
| 🛡️ **Security** | Security header score, HTTPS check, server info |
| 🔍 **DNS/WHOIS** | IP address, Nameserver, MX record, CDN, WHOIS registrar |
| 📊 **Trackers** | Google Analytics, GTM, Facebook Pixel, Hotjar এবং আরো |
| 🌐 **Subdomains** | CT Log + DNS Brute Force দিয়ে subdomain খোঁজা |
| 📂 **Directories** | ৫০০+ hidden path scan (`.env`, `/admin`, `/.git`, `/backup` ইত্যাদি) |
| 🤖 **Robots** | `robots.txt` পড়া, Sitemap URLs |

**অতিরিক্ত সুবিধা:**
- 🌐 Free Proxy Rotation — IP block এড়াতে
- ⏱️ Smart Delay — Rate limit bypass
- 🔑 Custom Headers / Cookie — লগইন-এর পেছনের পেজ স্ক্যান করতে
- 📥 Export: PDF, JSON, CSV, HTML, Markdown, TXT

---

## প্রথমবার সেটআপ

### Termux (Android)-এ

**ধাপ ১ — ফাইল নামান ও Extract করুন**
```bash
# Downloads ফোল্ডারে যান
cd /sdcard/Download

# ZIP Extract করুন
unzip webscraping-pro-v3.zip

# ফোল্ডারে ঢুকুন
cd webscraping
```

**ধাপ ২ — Permission দিন**
```bash
chmod +x setup.sh start.sh build-apk.sh
```

**ধাপ ৩ — Setup চালান (শুধু একবার)**
```bash
bash setup.sh
```
> ⚠️ এটি Node.js install করবে এবং সব প্যাকেজ নামাবে। ইন্টারনেট সংযোগ থাকতে হবে। একবারই করতে হবে।

**ধাপ ৪ — চালু করুন**
```bash
bash start.sh
```

**ধাপ ৫ — ব্রাউজারে খুলুন**

Chrome বা Firefox-এ যান এবং লিখুন:
```
http://localhost:3001
```

---

### Kali Linux-এ

```bash
# ফাইল Extract
unzip webscraping-pro-v3.zip
cd webscraping

# Permission
chmod +x setup.sh start.sh

# Setup (একবার)
bash setup.sh

# চালু করুন
bash start.sh
```
তারপর browser-এ: `http://localhost:3001`

---

## ব্যবহারের নিয়ম

### ১. URL দিয়ে Full Scan

1. উপরের বক্সে **ওয়েবসাইটের URL** লিখুন
   - `example.com` লিখলেও হবে, `https://` দেওয়া লাগবে না
2. **🔍 Full Scan** বাটনে ক্লিক করুন
3. সব ট্যাব একসাথে স্ক্যান হবে

### ২. একটি নির্দিষ্ট ট্যাব স্ক্যান

Full Scan না করে শুধু একটি ট্যাবে ক্লিক করলে শুধু সেই অংশটুকু স্ক্যান হবে — দ্রুত ফলাফলের জন্য।

### ৩. ডেটা দেখা

- যেকোনো URL বা Key-এর পাশে **Copy** বাটন আছে
- বড় লিস্ট স্ক্রোল করে দেখুন
- JS Audit ট্যাবে কোনো ফাইলের নামে ক্লিক করলে বিস্তারিত বের হবে

---

## ট্যাব গাইড

### ⚙️ JS Audit — সবচেয়ে গুরুত্বপূর্ণ ট্যাব

এই ট্যাব সাইটের সব JavaScript ফাইল ও Inline Script বিশ্লেষণ করে নিচের জিনিসগুলো বের করে:

- **Google API Key** — `AIza...` দিয়ে শুরু
- **Firebase Config** — `firebaseio.com`, `appspot.com`
- **AWS Access Key** — `AKIA...` দিয়ে শুরু
- **Stripe Key** — `pk_live_...`, `sk_test_...`
- **JWT Token** — `eyJ...` দিয়ে শুরু
- **MongoDB / PostgreSQL URI** — database connection strings
- **HLS Stream (m3u8)** — Live TV চ্যানেলের URL
- **RTMP Stream** — Live broadcast URL
- **Hardcoded Password** — code-এ লেখা password

### 🔌 API Finder

- **XHR/Fetch Calls** — সাইট কোন কোন API call করে
- **Streaming APIs** — Live TV / Video stream endpoint
- **Path Probe** — সাধারণ API path গুলো check করে (যেমন `/api/v1`, `/swagger`, `/graphql`)
- **GraphQL Queries** — যদি থাকে

### 🌐 Subdomains

CT Log (crt.sh) থেকে real subdomain এবং ৩০০+ সাধারণ নাম দিয়ে DNS brute force করে।
- **CT Log** = Certificate Transparency-তে নিবন্ধিত subdomains
- **DNS Brute** = `api.`, `admin.`, `dev.` ইত্যাদি নামে চেষ্টা করে

> ⚠️ এটি একটু সময় নেয় (৩০-৬০ সেকেন্ড)

### 📂 Directories

৫০০+ path scan করে hidden বা সংবেদনশীল ফাইল খোঁজে:

| রঙ | অর্থ |
|----|------|
| 🟢 200 | সরাসরি অ্যাক্সেস করা যাচ্ছে |
| 🟡 401/403 | আছে কিন্তু লগইন লাগবে |
| ⚪ 301/302 | Redirect হচ্ছে |

**Critical** হিসেবে চিহ্নিত হয়: `.env`, `config`, `.git`, `sql`, `backup`, `phpinfo`, `swagger`

---

## Advanced Settings

উপরের **⚙️** বাটনে ক্লিক করলে সেটিংস খুলবে।

### 🔑 Custom Headers

লগইন-এর পেছনের পেজ স্ক্যান করতে authorization header দিন।

**Format (JSON অবজেক্ট):**
```json
{
  "Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI...",
  "X-API-Key": "your-api-key-here"
}
```

Browser-এর DevTools → Network ট্যাব থেকে এই header কপি করা যায়।

### 🍪 Session Cookie

লগইন করা অবস্থায় স্ক্যান করতে:

1. Browser-এ সাইটে লগইন করুন
2. DevTools → Application → Cookies
3. সব cookie কপি করুন এবং এখানে পেস্ট করুন

**Format:**
```
PHPSESSID=abc123def456; auth_token=eyJhbG...; user_id=12345
```

### 🌐 Free Proxy Rotation

চালু করলে public proxy server থেকে IP ঘুরিয়ে request পাঠাবে।

- **কখন চালু করবেন:** সাইট IP block করলে বা বারবার error আসলে
- **সীমাবদ্ধতা:** Free proxy ধীর হতে পারে

**Fetch Proxies** বাটনে ক্লিক করলে available proxy list দেখাবে।

### ⏱️ Smart Delay

প্রতি request-এর মাঝে random বিরতি দেয় (০.৫ — ২ সেকেন্ড)।

- **কখন চালু রাখবেন:** সাধারণত সবসময়ই চালু রাখুন
- **উদ্দেশ্য:** সাইট বুঝতে না পারে যে bot স্ক্যান করছে

---

## Export ফরম্যাট

স্ক্যান শেষে উপরে **📥 Export** বাটন আসবে।

| ফরম্যাট | কাজ | কখন ব্যবহার করবেন |
|---------|-----|-------------------|
| 📄 **PDF** | পেশাদার রিপোর্ট, রঙিন | Client বা টিমকে দিতে |
| `{}` **JSON** | সম্পূর্ণ raw data | Developer বা tool-এ import করতে |
| 📊 **CSV** | সারণি আকারে | Excel বা Google Sheets-এ বিশ্লেষণ করতে |
| 🌐 **HTML** | Interactive browser রিপোর্ট | offline দেখতে বা share করতে |
| 📝 **Markdown** | Formatted text | GitHub, Notion, Obsidian-এ |
| 📃 **TXT** | Plain text | সহজ কপি-পেস্টের জন্য |

> **টিপস:** PDF-এ সব ক্যাটাগরি আলাদা section-এ সাজানো থাকে (API কোনটা, Endpoint কোনটা, সব লেবেল করা)।

---

## সমস্যা ও সমাধান

### ❌ `bash: node: command not found`
```bash
pkg install nodejs
```

### ❌ `EADDRINUSE: address already in use 3001`
Port ইতিমধ্যে ব্যবহার হচ্ছে। আগের সার্ভার বন্ধ করুন:
```bash
pkill -f "node server.js"
bash start.sh
```

### ❌ `npm ERR! network`
ইন্টারনেট সংযোগ চেক করুন। তারপর:
```bash
cd backend && npm install
cd ../frontend && npm install && npm run build
```

### ❌ স্ক্যান করতে অনেক সময় লাগছে
- **Subdomains** ট্যাব স্বাভাবিকভাবেই ৩০-৬০ সেকেন্ড নেয়
- **Directories** ট্যাব ৫০০ path check করে, একটু অপেক্ষা করুন
- Proxy চালু থাকলে বন্ধ করে দেখুন — দ্রুত হবে

### ❌ কিছু ট্যাবে error দেখাচ্ছে
- **Retry ⟳** বাটনে ক্লিক করুন
- সাইটটি হয়তো ঐ নির্দিষ্ট তথ্য দেয় না (যেমন কোনো cookie নেই)
- Custom Header বা Cookie দিয়ে চেষ্টা করুন

### ❌ Browser-এ `localhost:3001` খুলছে না
```bash
# Server চলছে কিনা দেখুন
ps aux | grep node

# না চললে চালু করুন
bash start.sh
```

---

## APK বানানো

Android APK বানাতে **Java JDK** এবং **Android SDK** লাগবে। Kali Linux-এ:

```bash
# Java install করুন
sudo apt install default-jdk -y

# APK build করুন
bash build-apk.sh
```

APK তৈরি হলে এই পথে পাবেন:
```
android/app/build/outputs/apk/debug/app-debug.apk
```

ফোনে কপি করুন:
```bash
cp android/app/build/outputs/apk/debug/app-debug.apk /sdcard/WebScraping.apk
```

তারপর ফোনের File Manager থেকে `WebScraping.apk` ইনস্টল করুন।

> ⚠️ APK install করতে Settings → Security → Unknown Sources চালু করতে হবে।

---

## ⚠️ দায়িত্বশীল ব্যবহার

এই টুলটি শুধুমাত্র **নিজের সাইট** বা **অনুমতি আছে এমন সাইট** পরীক্ষা করার জন্য।
অন্যের সাইটে অনুমতি ছাড়া ব্যবহার করা বেআইনি।

---

*Web Scraping Pro v3 — Built for security researchers & developers*
