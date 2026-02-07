# Airline Data Challenge – Project Elevate (US Domestic Market Entry)

## Project Background
A startup airline is planning to enter the **U.S. domestic market** by launching **five round-trip routes** between **medium and large airports**. The brand promise is punctuality: **On time, for you**.

The business wants a data-backed recommendation on:
- Which routes are the **busiest** and **most profitable**
- Which **five** routes to invest in (with a balanced view of profitability + operations)
- How many flights are required to **breakeven** on a **$90M upfront cost per airplane**

This analysis uses **Q1 2019 (Jan–Mar 2019)** flight data to evaluate routes using a composite investment framework.

Insights and recommendations are provided on the following key areas:
- **Category 1:** Market demand (traffic + occupancy)
- **Category 2:** Profitability (revenue vs operating + delay cost)
- **Category 3:** Operational performance (delays, early arrivals, taxi time efficiency)
- **Category 4:** Investment viability (breakeven flights + route score)







## Data Structure & Initial Checks
The analysis dataset is modeled around domestic flight operations in Q1 2019. The working structure consists of the following core tables (logical model):

- **flights_fact:** One row per flight (date, origin, destination, dep/arr delays, distance, airtime, taxi time, cancelled/diverted flags, etc.)
- **airports_dim:** Airport metadata (airport code, city/state, airport type/classification)
- **carriers_dim:** Airline/carrier details (carrier code, carrier name)
- **costs_params:** Business assumptions (operating cost per mile, delay cost per minute, aircraft upfront cost, etc.)

> Note: Exact table names may differ depending on the dataset version used. The logical model above reflects how the analysis was structured.





## Executive Summary

### Overview of Findings
Across Q1 2019, a small set of transcontinental and high-demand domestic routes consistently lead on **traffic volume, profitability potential, and load strength**. However, the best investment routes are not always the highest-revenue routes because **delay costs and distance-based operating costs** can erode net profitability.

Using a composite investment score weighted by **punctuality (40%)**, **profitability (30%)**, **occupancy (20%)**, and **distance efficiency (10%)**, five routes were recommended for immediate investment.





## Insights Deep Dive

### Category 1: Market Demand (Traffic + Occupancy)
* **High-demand corridors dominate volume.** The busiest routes cluster around major hubs and coastal markets where consistent passenger flow supports higher frequency operations.
* **Occupancy is a stronger signal than raw passenger counts.** Routes with high frequency can look “busy” but still underperform if occupancy is unstable.
* **Route stability matters.** Q1 has seasonal effects; routes with consistent weekly performance are safer early-entry bets.




### Category 2: Profitability (Revenue vs Costs)
* **Profitability is highly sensitive to cost assumptions.** Operating costs per mile and delay cost per minute can flip a “top revenue” route into a mediocre net route.
* **Delay-heavy airports create hidden margin leakage.** Departure and arrival delay minutes introduce real cost pressure that is easy to ignore if only revenue is considered.
* **Some long-haul routes remain attractive** if demand and on-time performance stay strong enough to offset distance-based operating costs.




### Category 3: Operational Performance (Punctuality & Experience)
* **Punctuality is a brand promise, so it’s treated as a first-class metric.** Routes with frequent delays were penalized even when they looked financially strong.
* **Early arrivals are a useful quality signal** when they are consistent and not driven by schedule padding alone.
* **Airport operational patterns matter.** Certain hubs show systematic delay behavior that impacts downstream reliability.




### Category 4: Investment Viability (Breakeven + Composite Score)
* **Composite scoring prevents “one-metric traps.”** The final selection balances customer experience + financial return.
* **Breakeven varies widely by route** because net profit per round-trip varies widely.
* **Example breakeven spread:**  
  - **IAD ↔ SFO:** ~**1,741** round-trip flights to breakeven (strong net economics)  
  - **JFK ↔ LAX:** ~**5,649** round-trip flights to breakeven (requires more volume/time)





## Final Recommended Routes (Top 5)
Based on the composite investment score (Punctuality 40%, Profitability 30%, Occupancy 20%, Distance Efficiency 10%), the recommended five routes are:

1. **JFK ↔ SFO**  
2. **CLT ↔ PHX**  
3. **EWR ↔ SFO**  
4. **JFK ↔ LAX**  
5. **IAD ↔ SFO**  

These five routes represent the strongest balance of:
- strong demand and occupancy consistency
- attractive net profitability after costs
- acceptable operational reliability aligned to the brand promise



## KPI Framework (How Success Will Be Measured)

### Financial Performance KPIs
- **Net Profit per Round Trip**
- **Profit Margin (%)**
- **Cost per Mile**
- **Delay Cost per Flight (minutes × $/min)**

### Operational Efficiency KPIs
- **Average Occupancy (%)**
- **Average Distance Efficiency (profit per mile)**
- **Taxi-Out / Taxi-In time trends**
- **Cancellation / Diversion rate**

### Punctuality & Experience KPIs
- **On-Time Departure Rate**
- **On-Time Arrival Rate**
- **Average Departure Delay (minutes)**
- **Average Arrival Delay (minutes)**
- **Early Arrival Rate**



## Recommendations
Based on the insights and findings above, we recommend the airline leadership team consider the following:

* **Launch the Top 5 routes as the Phase-1 network**, prioritizing routes with the best punctuality + net economics balance.
* **Instrument delay drivers early** (airport, time-of-day, carrier/operations factors) because delay costs materially impact profitability.
* **Standardize an on-time operating playbook** for the chosen airports to protect the brand promise in the first 90 days.
* **Adopt route-level profitability reporting** (profit per round-trip) rather than only revenue reporting to avoid misleading winners.
* **Run a sensitivity analysis** on operating cost per mile and delay cost per minute to understand how fragile each route’s breakeven is.



## Assumptions and Caveats
Throughout the analysis, several assumptions were required to keep evaluation consistent:

* **Cost assumptions are business inputs** (e.g., operating cost per mile, delay cost per minute, aircraft cost). Actuals may differ by fleet type, labor, and fuel hedging.
* **Q1 2019 is a seasonal snapshot.** Demand and delay patterns may change across summer peaks and holiday periods.
* **Breakeven is computed using average net profit estimates.** Real breakeven will vary with pricing, load factor swings, disruptions, and competitive response.
* **Operational metrics are treated as strategic constraints.** Some financially attractive routes were deprioritized due to punctuality risk.



---

