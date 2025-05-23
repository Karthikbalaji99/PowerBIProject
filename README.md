# 📊 Amazon Sales Insights — Power BI Storytelling Dashboard  
*(Dataset Source: [Kaggle – “Amazon Sale Report”](https://www.kaggle.com/))*

> **Purpose:** Showcase my end-to-end Power BI skill set—data wrangling, modeling, DAX, custom visuals, and data-driven storytelling—by turning raw Amazon product and review data into meaningful, actionable insights.

---

## 1. Data Journey & Preparation

| Step | What I did | Why it matters |
|------|------------|----------------|
| **Raw Ingest** | Imported CSV from Kaggle into Power Query | Reproducible and free source for portfolio viewers |
| **Currency Cleaning** | Stripped “₹”, removed thousand-separators, converted to *Decimal* | Enables price calculations / currency formatting |
| **Discount % Parsing** | Removed “%”, cast to *Decimal* | Allows numeric analytics on discount depth |
| **Category Hierarchy Split** | `category` → `Category_Main`, `Sub1`, `Sub2`, `Sub3`, `Sub4` (delimiter `|`) | Unlocks drill-down and drill-through visuals |
| **Review Normalization** | Comma-separated IDs, names, titles, contents → *split into rows* | 1-to-many product-review model for robust sentiment analytics |
| **Calculated Columns** | `Revenue`, `Discount_Amount`, `Is_High_Rated` | Creates ready-to-use KPIs |
| **Sentiment Tag** | Keyword rule-based **Positive / Neutral / Negative** on `review_content` | Adds qualitative layer without external services |
| **Error / Null Handling** | *Removed rows with rating errors*; filled `rating_count` nulls with 0; kept missing deep sub-cats as “N/A” | Data quality → reliable metrics |

---

## 2. Report Structure — Every Page Tells a Story

### 🟢 **Page 1 — “How’s Business Doing?” (Sales Overview I)**  
*Story:* *“What’s our top-line performance at a glance?”*  

- **Cards** – Total Revenue, Avg Rating, Distinct Products, Total Reviews  
- **Line Chart** – Revenue trend (mock monthly index) shows momentum  
- **Category Sales Bar** – Reveals which main categories pay the bills  
- **Detail Table** – Combined view for quick product lookup  

> **Insight Example:** “USB Cables contribute 42 % of revenue while averaging only a 4.0 star rating—opportunity to improve quality messaging.”

---

### 🟢 **Page 2 — “Are We Pricing Smartly?” (Sales Overview II)**  
*Story:* *“Dig into pricing efficiency and discount tactics.”*  

- **Eight KPI Cards** – SUM / AVG / MAX / MIN of *actual* vs *discounted* prices  
- **Category–Subcategory Slicer** – Dropdown enables granular focus  
- **Revenue Treemap (drill-down)** – Instantly spot sub-niches with high takers vs. low discounts  

> **Insight Example:** “Type-C cables in ‘Accessories & Peripherals › Cables’ sell most on 43 % average discount—aggressive discounting drives volume.”

---

### 🟢 **Page 3 — “Who Says What?” (Product-Wise Information)**  
*Story:* *“Zoom into individual customer voices for any product.”*  

- **Product Name Slicer** – Single-select filters the whole page  
- **Cards** – Sum & Average Rating = health signals  
- **Image Card** – Visual product identity  
- **Review Table** – User, rating, title & full comment in one scrollable pane  

> **Insight Example:** “Wayona Nylon Braided Cable earns 24 k reviews averaging 4.2; frequent keywords: ‘durable’, ‘fast charging’.”

---

### 🟢 **Page 4 — “How Do Customers Feel?” (Sentiment Analysis)**  
*Story:* *“Translate thousands of words into a pulse of sentiment.”*  

- **Slicers** – Category filter, sentiment type, rating range  
- **Donut Chart** – Share of Positive / Neutral / Negative reviews  
- **Bar Chart** – Avg Rating by Sentiment category (validates model)  
- **Review-Sentiment Table** – Qualitative drill for CX teams  

> **Insight Example:** “Despite 85 % Positive reviews overall, ‘Micro USB’ sub-category shows 22 % Negative—pain points are ‘doesn’t support fast charge’.”

---

### 🟢 **Page 5 — “Which Categories Win Hearts & Wallets?” (Category Performance)**  
*Story:* *“Balance of earnings and love across categories.”*  

- **Treemap** – Revenue share + tool-tip Avg Rating; drill down to Sub-Cats  
- **Stacked Column** – Sentiment counts layered per main category  

> **Insight Example:** “Networking Devices command lower revenue but highest average rating (4.3) indicating brand strength; potential to upsell accessories.”

---

### 🟢 **Page 6 — “Tell Me EVERYTHING About This Product” (Product Deep Dive)**  
*Story:* *“One-click forensic report card.”*  

- **Product Slicer** – Pick any item  
- **Six KPI Cards** – Revenue, Discounted & Actual Price, Rating, Rating Count, Discount %  
- **Image Card** – Product photo renders inline  
- **Sentiment Pie** – Real-time Positive/Neutral/Negative split  
- **Buy on Amazon Button** – Dynamic web link → live product page  

> **Insight Example:** “boAt Deuce USB 300 sells ₹31 M revenue, 3-A charging & braided cable features resonate; but 12 % Negative citing ‘connector loosens after 3 months’—possible design tweak.”

---

## 3. Technical Highlights

- **Power Query**: advanced “split into rows”, conditional columns, column profiling  
- **DAX Measures**: dynamic KPI cards (e.g., `SelectedProductURL = SELECTEDVALUE( Products[product_link] )`)  
- **Custom Visuals**: **Image Viewer** (product photos), **Word Cloud** (review keywords)  
- **Drill-Through & Drill-Down**: right-click product → Deep Dive; treemap hierarchy walk-downs  
- **User Experience**: single-select slicers, bookmarks, and a polished theme palette  

---

## 4. Business Impact Scenario

| Question | Answered by the Dashboard |
|----------|---------------------------|
| *Which categories deserve marketing spend?* | Page 1 & 2 revenue and discount efficiency |
| *What’s driving negative sentiment?* | Page 4 sentiment filters + review drill |
| *Which products can tolerate price hikes?* | Page 6 KPI vs. sentiment balance |
| *Where to upsell premium cables?* | Page 5 Category Performance (high rating, low revenue) |

---

## 5. Next-Step Enhancements

1. **Azure Cognitive Services** – Replace rule-based sentiment with ML accuracy  
2. **Time-Series Integration** – Add sales timestamp for genuine trends & seasonality  
3. **RLS Demo** – Row-Level Security to simulate vendor-specific portals  
4. **Automated Refresh** – Gateway + schedule for near-real-time monitoring  

---

## 6. How to Explore

1. Download or open the `.pbix` file in Power BI Desktop.  
2. Navigate via page tabs or interactive buttons.  
3. Use slicers to filter categories, sentiment, or specific products.  
4. Right-click any product → **Drill-through → Product Deep Dive** for the micro-story.

---



Feel free to clone this project, give feedback, or discuss data storytelling ideas!

---

*© 2025 — Built with passion for data and customer insight.*
