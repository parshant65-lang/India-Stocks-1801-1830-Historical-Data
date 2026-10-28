# India-Stocks-1801-1830-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 1801 to 1830)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-1801-1830-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (1801 to 1830)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 1801 | `OILCOUNTUB` | Oil Country Tubular Limited | `OILCOUNTUB.NS` |
| 1802 | `OMAXAUTO` | Omax Autos Limited | `OMAXAUTO.NS` |
| 1803 | `OMAXE` | Omaxe Limited | `OMAXE.NS` |
| 1804 | `OMFREIGHT` | Om Freight Forwarders Limited | `OMFREIGHT.NS` |
| 1805 | `OMINFRAL` | OM INFRA LIMITED | `OMINFRAL.NS` |
| 1806 | `OMNI` | Omnitech Engineering Limited | `OMNI.NS` |
| 1807 | `OMPOWER` | Om Power Transmission Limited | `OMPOWER.NS` |
| 1808 | `ONEGLOBAL` | One Global Service Provider Limited | `ONEGLOBAL.NS` |
| 1809 | `ONELIFECAP` | Onelife Capital Advisors Limited | `ONELIFECAP.NS` |
| 1810 | `ONEPOINT` | One Point One Solutions Limited | `ONEPOINT.NS` |
| 1811 | `ONIDA` | Onida Electronics Limited | `ONIDA.NS` |
| 1812 | `ONIXSOLAR` | Onix Solar Energy Limited | `ONIXSOLAR.NS` |
| 1813 | `ONMOBILE` | OnMobile Global Limited | `ONMOBILE.NS` |
| 1814 | `ONWARDTEC` | Onward Technologies Limited | `ONWARDTEC.NS` |
| 1815 | `OPTIEMUS` | Optiemus Infracom Limited | `OPTIEMUS.NS` |
| 1816 | `OPTIFIN` | Optimus Finance Limited | `OPTIFIN.NS` |
| 1817 | `ORBTEXP` | Orbit Exports Limited | `ORBTEXP.NS` |
| 1818 | `ORCHASP` | Orchasp Limited | `ORCHASP.NS` |
| 1819 | `ORCHPHARMA` | Orchid Pharma Limited | `ORCHPHARMA.NS` |
| 1820 | `ORICONENT` | Oricon Enterprises Limited | `ORICONENT.NS` |
| 1821 | `ORIENTALTL` | Oriental Trimex Limited | `ORIENTALTL.NS` |
| 1822 | `ORIENTBELL` | Orient Bell Limited | `ORIENTBELL.NS` |
| 1823 | `ORIENTCABL` | Orient Cables (India) Limited | `ORIENTCABL.NS` |
| 1824 | `ORIENTCEM` | Orient Cement Limited | `ORIENTCEM.NS` |
| 1825 | `ORIENTCER` | ORIENT CERATECH LIMITED | `ORIENTCER.NS` |
| 1826 | `ORIENTELEC` | Orient Electric Limited | `ORIENTELEC.NS` |
| 1827 | `ORIENTHOT` | Oriental Hotels Limited | `ORIENTHOT.NS` |
| 1828 | `ORIENTLTD` | Orient Press Limited | `ORIENTLTD.NS` |
| 1829 | `ORIENTPPR` | Orient Paper & Industries Limited | `ORIENTPPR.NS` |
| 1830 | `ORIENTTECH` | Orient Technologies Limited | `ORIENTTECH.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream OILCOUNTUB 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-1801-1830-Historical-Data/main/OILCOUNTUB/1m/2026/10/OILCOUNTUB_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
