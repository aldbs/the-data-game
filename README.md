# 🎮 Data Game – Collaboration Challenge

A browser-based serious game designed to teach data teams how to collaboratively manage data resources, prioritise infrastructure investments, and deliver analyses under pressure.

---

## 📖 Overview

**Data Game** is a turn-based resource management game played over **10 turns**. Each turn, your team receives data from four business domains and must use it to complete analysis requests. By investing in infrastructure projects, you can boost your data production and storage capacity — but every turn counts, and falling behind on analyses costs you customer satisfaction.

The game is built as a single standalone HTML file using **React 18**, **Tailwind CSS**, and **Babel** (no build step required).

---

## 🚀 Getting Started

Simply open the file in any modern browser:

```
open data-game-en.html
```

No installation, no dependencies, no server required.

---

## 🎯 Game Objective

Maximise the number of **completed analyses** across 10 turns while keeping **Customer Satisfaction** as high as possible.

- ✅ Completing an analysis on time: **+8% satisfaction**
- ⏰ Each overdue analysis at the start of a new turn: **-5% satisfaction**
- 🤖 Using the ML Model (pay 1, get 2): **+15% satisfaction**

---

## 🔄 Turn Structure

Each turn follows this sequence:

1. **Receive Data** — Click the "Receive Data" button to collect produced data into your storage. Data exceeding storage capacity is lost.
2. **Complete Analyses** — Use stored data to deliver pending analysis requests. Backlogged analyses from previous turns are highlighted in red.
3. **Invest in Projects** *(optional)* — After receiving data, spend resources on infrastructure or analytics projects to improve future turns.
4. **Validate the Turn** — Move to the next turn. Any incomplete analyses are added to the backlog and will penalise satisfaction.

---

## 📊 Data Domains

Each turn, data is produced across **4 domains**:

| Domain | Emoji | Starting Production | Starting Capacity |
|---|---|---|---|
| Marketing | 📈 | 2 / turn | 2 |
| Ops | ⚙️ | 2 / turn | 2 |
| Product | 🎯 | 2 / turn | 2 |
| Tech | 💻 | 2 / turn | 2 |

Analysis requests require a specific amount of data from each domain. Requirements scale up progressively over the 10 turns.

---

## 🔢 Analysis Requirements by Turn

| Turn | Marketing | Ops | Product | Tech |
|---|---|---|---|---|
| 1 | 2 | 0 | 1 | 1 |
| 2 | 2 | 0 | 1 | 1 |
| 3 | 3 | 0 | 2 | 2 |
| 4 | 4 | 0 | 3 | 3 |
| 5 | 4 | 0 | 3 | 3 |
| 6 | 5 | 1 | 4 | 4 |
| 7 | 5 | 1 | 4 | 4 |
| 8 | 5 | 1 | 4 | 4 |
| 9 | 6 | 1 | 5 | 5 |
| 10 | 6 | 0 | 5 | 5 |

---

## 🚀 Improvement Projects

Projects are split between two team roles. Each project costs data from **all 4 domains** and must be purchased after receiving data for that turn.

### 🔧 Data Engineers — Infrastructure & Production

| Project | Cost | Effect | Repeatable |
|---|---|---|---|
| 🔌 Set up an extraction tool | 1 / domain | +1 production / domain / turn | ✅ Yes |
| ✨ Implement Data Quality rules | 1 / domain | +1 production / domain / turn | ✅ Yes |
| ⚡ Deploy an automated pipeline | 2 / domain | +2 production / domain / turn | ✅ Yes |
| 📁 Organise file storage | 1 / domain | +1 capacity / domain | ❌ Once |
| 💾 Create a database | 1 / domain | +1 capacity / domain | ❌ Once (requires file storage) |
| 🏢 Deploy a Data Warehouse | 1 / domain | +1 capacity / domain | ❌ Once (requires database) |

### 📈 Data Analysts — Exploitation & Visualisation

| Project | Cost | Effect | Repeatable |
|---|---|---|---|
| 📖 Set up a Data Catalog | 1 / domain | +1 capacity / domain | ❌ Once |
| 📊 Deploy a BI tool | 1 / domain | +1 capacity / domain | ❌ Once |
| 💾 Advanced storage optimisation | 2 / domain | +2 capacity / domain | ✅ Yes |
| ⚡ Create real-time dashboards | 1 / domain | -1 data cost on next analysis | ❌ Once |
| 🤖 Deploy an ML model | 3 / domain | Pay 1 analysis, complete 2! | ❌ Once |

> **Storage chain dependency:** File Storage → Database → Data Warehouse (must be unlocked in order)

---

## 🤖 ML Model — Special Mechanic

Once deployed, the ML Model button appears in the backlog when **2 or more analyses are pending**. When activated:
- The game pays for the **cheapest affordable** analysis automatically.
- A **second analysis** (the next cheapest) is completed **for free**.
- Customer satisfaction is boosted by **+15%**.
- The ML Model is consumed after a single use.

---

## 😊 Customer Satisfaction

Satisfaction starts at **100%** and evolves based on your performance:

| Event | Impact |
|---|---|
| Analysis delivered | +8% |
| Each overdue analysis (at turn start) | -5% |
| ML Model double delivery | +15% |

**Final rating:**
- 😊 ≥ 70% — Great job!
- 😐 40–69% — Room for improvement
- 😞 < 40% — Critical situation

---

## 🛠️ Technical Details

| Tech | Version |
|---|---|
| React | 18 (UMD CDN) |
| ReactDOM | 18 (UMD CDN) |
| Babel Standalone | Latest |
| Tailwind CSS | CDN |

The entire game runs in a **single HTML file** with no build process, no package manager, and no backend. It can be hosted on any static file server or shared as a direct file attachment.

---

## 💡 Tips & Strategy

- **Invest early** in extraction tools and data quality to compound production gains over multiple turns.
- **Don't neglect storage** — overflowing data is wasted data. File Storage → Database → Data Warehouse is a strong early chain.
- **Prioritise Ops data** carefully: it only appears in mid-to-late turn requirements, so don't over-invest early.
- **Save the ML Model** for a turn when you have a large backlog and can maximise the double-delivery bonus.
- **Real-time dashboards** are most effective when the next analysis has a high Ops or Marketing cost.

---

## 📄 License

This project is intended for internal educational and team-building purposes.
