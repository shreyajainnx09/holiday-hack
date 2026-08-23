<div align="center">

# 🗓️ Holiday Hack
### Find public holidays by country and hack together the longest possible break

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
[![Nager.Date API](https://img.shields.io/badge/Nager.Date%20API-2d7a4f?style=for-the-badge)](https://img.shields.io/badge/Nager.Date%20API-2d7a4f?style=for-the-badge)
[![Play Now](https://img.shields.io/badge/🎮%20TRY%20IT%20LIVE-6C3EB8?style=for-the-badge)](https://shreyajainnx09.github.io/holiday-hack/)

</div>

---

## 📌 Description

A vacation-planning tool that looks up any country's public holidays for a given year and highlights **long-weekend opportunities** — helping you stretch a handful of leave days into the longest possible breaks.

Discover public holidays, find long weekend opportunities, and stretch your leave days further than ever.

## 🎯 Features

- **190+ countries** and years from 2024 through 2100, powered by the [Nager.Date public holidays API](https://date.nager.at/)
- Summary stats bar: total holidays, holidays remaining this year, long-break opportunities, and items saved to your plan
- **Insights cards** — next holiday, best upcoming break, and the months with the most holidays concentrated
- **Holidays view** with search, filters (all / long breaks only / upcoming only), and per-holiday long-weekend strategy tips (e.g. "Thu–Sun · 4-day break")
- **Calendar view** — full-year grid across all 12 months with holiday/weekend/long-break color coding, plus click-and-drag-style date-range selection to plan custom breaks
- **Plans** — save individual holidays or custom date ranges, grouped by year, with export to `.txt`
- **Inspiration** — a curated grid of destination ideas with best-time-to-visit notes
- **Share** — a styled shareable card of your upcoming holidays, copy-to-clipboard, and native OS share sheet support
- Graceful offline/API-failure fallback with a small built-in holiday dataset for 8 major countries

## 🎮 Usage

1. Select your country and year from the hero controls.
2. Review total/remaining holidays and detected long-break opportunities in the insights cards.
3. Browse the **Holidays** list or the **Calendar** view — click a start date then an end date on the calendar to select a custom range, then press `Enter` or click **Save range**.
4. Save promising long weekends to **Plans**, export them as a `.txt` file, or share your plan via the **Share** tab.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| 🌐 HTML5 / CSS3 | Structure and styling (custom CSS variables for theming, Google Fonts: Fraunces + DM Sans) |
| 🟨 JavaScript | App state, holiday analysis, calendar rendering, plan management |
| 🌍 [Nager.Date API](https://date.nager.at/) | Public holiday data by country and year |
| 💾 `localStorage` | Persists selected country/year and saved plans across visits |

## ⚙️ Setup

No build step or dependencies — it's a single static HTML file.

```bash
git clone https://github.com/shreyajainnx09/holiday-hack.git
cd holiday-hack
python3 -m http.server 8000
```

Then visit `http://localhost:8000` — or just use the **[live demo](https://shreyajainnx09.github.io/holiday-hack/)**.

## 🧠 How It Works

- `fetchHolidays()` calls `https://date.nager.at/api/v3/PublicHolidays/{year}/{countryCode}`; if the request fails or returns no data, it falls back to a small hardcoded dataset (`FALLBACK`) covering India, US, UK, Germany, Japan, Australia, France, and Canada, or a minimal generic list for anywhere else
- `analyzeHolidays()` walks each holiday and, based on which day of the week it falls on, computes one or more "bridge" strategies — e.g. a Thursday holiday suggests taking Friday off for a 4-day weekend, or all of Mon–Wed for a 9-day mega-break
- The **Calendar** view builds a full 12-month grid per year client-side, color-coding holidays, weekends, long-break days, and any in-progress date-range selection
- Saved plans (individual holidays or custom ranges) and the last-selected country/year persist via `localStorage`, so your setup survives a page reload
- Export builds a plain-text summary of your saved plan and all holidays for the year, downloaded as a `.txt` file via a Blob URL

## 📁 Project Structure

```
holiday-hack/
│
├── index.html       → Entire app — markup, styling, and all JS logic in one file
└── README.md
```

## 🌟 Ideas for Extending

- Combine with a user's actual leave balance to auto-optimize break suggestions
- Multi-country comparison for travelers deciding where to go
- Calendar export (`.ics`) for saved plans
- Real destination data/images for the Inspiration tab instead of a static curated list

## 👩🏻‍💻 Author

**Shreya Jain**
BCA | Data Analytics | Python | SQL | Tableau
