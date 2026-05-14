# 🥒 Doon Didi – Ghar Ka Aachar

**Authentic homemade Indian pickles & traditional delights by Kavita Uniyal, Uttarakhand.**

---

## 🌟 Project Overview

A fully static, mobile-responsive Indian pickle business website with bilingual (Hindi/English) support, AI-powered chatbot, customer reviews, and a full product catalogue.

---

## ✅ Completed Features

### 🏠 Pages
- **Home** – Hero banner, intro strip, featured products, testimonials slider, CTA banner
- **Products** – Full catalogue with category filters (All / Achar / Sweets / Mukhwas), product cards with order & price inquiry buttons
- **Reviews** – Customer reviews loaded from API, star rating picker, submit review form, rating breakdown bars
- **About** – Founder story, timeline, quality commitments section
- **Contact** – Contact info cards, social links, message form

### 🛍️ Products (9 items)
| # | Product | Category | Local Image |
|---|---------|----------|-------------|
| 1 | Lahsun Pickle (लहसुन का अचार) | Pickle | ✅ images/lahsun-pickle.jpg |
| 2 | Amla Pickle (आंवला का अचार) | Pickle | ✅ images/amla-pickle.jpg |
| 3 | Green Mirch Achar (हरी मिर्च का अचार) | Pickle | ✅ images/green-mirch-pickle.jpg |
| 4 | Red Mirch Achar (लाल मिर्च का अचार) | Pickle | ✅ images/red-mirch-pickle.jpg |
| 5 | Mixed Pickle (मिक्स्ड अचार) | Pickle | ✅ images/mixed-pickle.jpg |
| 6 | Gajar Pickle (गाजर का अचार) | Pickle | ✅ images/gajar-pickle.jpg |
| 7 | Mukhwas (मुखवास) | Fresh | CDN URL |
| 8 | Amla Candy (आंवला कैंडी) | Sweet | CDN URL |
| 9 | Murabba (मुरब्बा) | Sweet | CDN URL |

### 🌐 Bilingual i18n System
- Full Hindi / English translation dictionary in `js/main.js` (`I18N` object)
- `data-i18n` attributes on every translatable element in `index.html`
- `updateLanguage(lang)` loops all `[data-i18n]` and `[data-i18n-placeholder]` elements
- Instant toggle via top-bar `🌐 English` / `🌐 हिंदी` button — no page reload
- Language synced to chatbot via `syncChatbotLang(lang)`

### 🤖 AI Chatbot
- Floating bottom-right widget (above WhatsApp button — no overlap)
- Bilingual auto-detection (Devanagari → Hindi, Latin → English)
- 19 offline intent handlers: products, prices, ordering, ingredients, hours, location, greetings, etc.
- OpenRouter DeepSeek-R1 fallback (add `OPENROUTER_API_KEY` in `js/chatbot.js` line 24)
- Voice input via `SpeechRecognition` API
- Optional voice output via `SpeechSynthesis` API
- Syncs with site language toggle in real time
- Full product knowledge including all 9 items

### 💬 Button Positioning (Fixed)
| Button | Position | z-index |
|--------|----------|---------|
| WhatsApp float | `bottom: 20px, right: 24px` | 9998 |
| Chatbot toggle | `bottom: 96px, right: 24px` | 10000 |
| Back to top | `bottom: 10.5rem, right: 2rem` | 998 |
- Mobile (≤480px): Chatbot at `bottom: 96px`, chat window above at `bottom: 160px`

### ⭐ Reviews API
- Table: `reviews` (via RESTful Table API)
- Fields: `customer_name`, `product`, `rating`, `review_text`, `created_at`
- Loads, displays with star ratings, allows new submissions

---

## 📁 File Structure

```
index.html              ← Single-page app (5 pages via JS showPage())
css/
  style.css             ← Main stylesheet (Doon Didi branding)
  extras.css            ← Decorative extras (badges, dividers, animations)
  chatbot.css           ← Chatbot widget styles
js/
  main.js               ← Products data, navigation, reviews, i18n system
  chatbot.js            ← AI chatbot logic (offline + OpenAI GPT)
images/
  lahsun-pickle.jpg
  amla-pickle.jpg
  green-mirch-pickle.jpg
  red-mirch-pickle.jpg
  mixed-pickle.jpg
  gajar-pickle.jpg
```

---

## 🔗 Entry Points

| URL | Description |
|-----|-------------|
| `/` or `index.html` | Home page |
| `index.html#products` (click nav) | Products page |
| `index.html#reviews` (click nav) | Reviews page |
| `index.html#about` (click nav) | About page |
| `index.html#contact` (click nav) | Contact page |
| `tables/reviews` | Reviews REST API endpoint |

---

## 🗄️ Data Models

### `reviews` table
| Field | Type | Description |
|-------|------|-------------|
| id | text | Auto UUID |
| customer_name | text | Reviewer's name |
| product | text | Product reviewed |
| rating | number | 1–5 star rating |
| review_text | rich_text | Full review content |
| created_at | datetime | Auto timestamp |

---

## 🚀 Deployment

To make the website live, go to the **Publish tab** and click publish. No build step required — purely static.

---

## 🔧 To-Do / Recommended Next Steps

1. **Add API key** – Set `OPENROUTER_API_KEY` in `js/chatbot.js` line 24 (get one free at https://openrouter.ai/keys). Uses model `deepseek/deepseek-r1`
2. **Download remaining images** – Mukhwas, Amla Candy, Murabba still use CDN URLs; download locally for reliability
3. **Social media links** – Update Facebook, Instagram, YouTube URLs in footer and contact page
4. **SEO** – Add Open Graph meta tags (`og:title`, `og:image`, `og:description`)
5. **WhatsApp pre-fill** – Update `wa.me` links to include pre-filled order message
6. **Analytics** – Add Google Analytics or similar

---

## 📞 Contact / Brand Info

- **Brand**: Doon Didi – Ghar Ka Aachar
- **Founder**: Kavita Uniyal
- **Location**: Uttarakhand, India
- **Phone / WhatsApp**: 8445349802
- **Hours**: Mon–Sat 9AM–7PM, Sunday 10AM–3PM
