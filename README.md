# 🎬 Pan-India Cinema Intelligence Dashboard

> An interactive 5-page Power BI dashboard analyzing **141 films** across **6 Indian film industries** (2012–2025)

![Dashboard Preview](https://img.shields.io/badge/Tool-Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Data-Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![DAX](https://img.shields.io/badge/Language-DAX-0078D4?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-27AE60?style=for-the-badge)

---

## 📌 Project Overview

This dashboard explores the business intelligence behind Indian cinema — comparing box office performance, star power, OTT trends, and the rise of Pan-India films across **Tollywood, Kollywood, Mollywood, Sandalwood, Bollywood, and Marathi** industries.

---

## 🖥️ Dashboard Pages

| Page | Title | Key Visuals |
|------|-------|-------------|
| 1 | **Overview** | Donut chart, Clustered bar, 6 KPI cards |
| 2 | **Box Office Battle** | Budget vs ROI Scatter, Top 10 films, Matrix |
| 3 | **Star Power Index** | Actor rankings, Gauge, Hit/Flop donut |
| 4 | **OTT vs Theatre** | Platform bar chart, Revenue pie, OTT trend line |
| 5 | **Pan-India Phenomenon** | Collection line chart, ROI comparison, Hero stat |

---

## 📊 Key Insights

- 🟡 **Tollywood dominates** with 41% of total worldwide collections
- 📺 **Amazon Prime Video** leads OTT with 40+ film acquisitions
- 🌍 **Pan-India films deliver 2× better ROI** than regional-only releases
- 📅 **2022** — the year South Indian cinema crossed Bollywood in total collections
- ⏱️ Average **OTT window is 47 days** after theatrical release

---

## 🧮 DAX Measures

```dax
-- Hit Rate %
Hit Rate % =
DIVIDE(
    CALCULATE(COUNTROWS(Movies),
        Movies[Verdict] IN {
            "ALL-Time Blockbuster","Blockbuster","Super Hit","Hit"
        }),
    COUNTROWS(Movies)
) * 100

-- ROI %
ROI % =
DIVIDE(
    SUM(Movies[Collection_Worldwide_Cr]) - SUM(Movies[Budget_Cr]),
    SUM(Movies[Budget_Cr])
) * 100

-- Pan India Films
Pan India Films =
CALCULATE(COUNTROWS(Movies), Movies[Is_Pan_India] = "Yes")

-- Avg OTT Window
Avg OTT Window = AVERAGE(Movies[OTT_Days_After_Release])
```

---

## 📁 Dataset Structure

| Sheet | Rows | Description |
|-------|------|-------------|
| `Movies` | 141 | Main film data — budget, collections, verdict, OTT |
| `Industry_Summary` | 55 | Aggregated by industry × year |
| `Stars` | 87 | Actor-level hit rate and collection data |
| `Directors` | 102 | Director-level performance metrics |

### Key Columns
`Movie_ID` · `Industry` · `Language` · `Year` · `Genre` · `Budget_Cr` · `Collection_India_Cr` · `Collection_Worldwide_Cr` · `Verdict` · `OTT_Platform` · `OTT_Days_After_Release` · `IMDB_Rating` · `Director` · `Lead_Actor` · `Is_Pan_India` · `Is_Sequel`

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|------|-------|
| **Power BI Desktop** | Dashboard building, DAX measures |
| **Microsoft Excel** | Data collection and cleaning |
| **Python (pandas, openpyxl)** | Data preprocessing and formatting |
| **Canva** | Dashboard background design |
| **Flaticon** | KPI card icons |

---

## 🎨 Industry Color System

| Industry | Color | Hex |
|----------|-------|-----|
| 🟡 Tollywood | Gold | `#F4C430` |
| 🔴 Kollywood | Red | `#E74C3C` |
| 🟢 Mollywood | Green | `#27AE60` |
| 🟤 Sandalwood | Brown | `#A0522D` |
| 🔵 Bollywood | Blue | `#2980B9` |
| 🟣 Marathi | Purple | `#8E44AD` |

---

## 📂 Repository Structure

```
📦 Pan-India-Cinema-Dashboard
├── 📊 CinemaDash.pbix          ← Power BI Dashboard file
├── 📋 Cinema_PowerBI_Ready.xlsx ← Cleaned dataset (4 sheets)
├── 📸 Screenshots/
│   ├── Overview.png
│   ├── BoxOffice.png
│   ├── Stars.png
│   ├── OTT.png
│   └── PanIndia.png
└── 📄 README.md
```

---

## 🚀 How to Open

1. Download `CinemaDash.pbix`
2. Open with **Power BI Desktop** (free download at powerbi.microsoft.com)
3. If prompted about data source, click **Continue** → the Excel file is embedded
4. Explore all 5 pages using the left navigation panel

---

## 👤 Author

**Pranav Roy** — BBACA Graduate | Data Analytics Enthusiast

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat&logo=linkedin)](https://linkedin.com/in/PranavRoy07)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=flat&logo=github)](https://github.com/PranavRoy07)

---

## 📜 License

This project is open source under the [MIT License](LICENSE).
Dataset compiled manually from public sources (Wikipedia, Koimoi, Box Office India).
