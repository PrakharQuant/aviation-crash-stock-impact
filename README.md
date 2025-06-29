# aviation-crash-stock-impact
This project visualizes how the Air India crash on **June 12, 2025** affected the stock prices of **Boeing (USD)** and **Airbus (EUR)**.
# ✈️ Stock Impact Analysis of the Air India Crash – Boeing vs Airbus

This project analyzes how the **Air India plane crash on 12 June 2025** affected the stock prices of **Boeing** (NYSE:BA) and **Airbus** (Euronext Paris: AIR.PA), using historical daily closing prices.

---

## 📚 Background

On June 12, 2025, an Air India aircraft manufactured by **Boeing** was involved in a major crash. The aviation industry reacts quickly to such events — especially for manufacturers involved. I wanted to explore:

- 📉 Did Boeing's stock fall after the crash?
- 📈 Did Airbus, its competitor, benefit?
- 🔁 What was the pattern over the last three months?

---

## 🔍 Data Collection

### Boeing (NYSE:BA)

I used the built-in `GOOGLEFINANCE()` function in Google Sheets:

Then I used
```excel
=GOOGLEFINANCE("NYSE:BA", "close", TODAY()-90, TODAY(), "DAILY")
={"Date","Boeing"; INDEX(GOOGLEFINANCE(...), 2, 0)}
to remove the default header row and format the dates nicely (dd mmmm like 12 June).

BUT
Airbus prices are quoted in Euros (€), but Boeing is in USD ($). Comparing raw prices would be misleading.
I converted Airbus prices using an approximate exchange rate:
EUR_TO_USD = 1.08
df['Airbus_USD'] = df['Airbus'] * EUR_TO_USD







