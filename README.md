# Supplier Delay Early-Warning

**Live demo:** https://adi29102000-s.github.io/supplier-delay-early-warning/

## 1. Problem

Some suppliers cause many late deliveries. Checking delivery records by hand can make it hard to notice a problem early.

## 2. User

A supply chain or operations manager who has delivery data in a CSV file.

## 3. Idea

A small web page that reads delivery dates in your browser and highlights suppliers whose recent deliveries may need attention.

## 4. How it works

The page reads a CSV with `supplier`, `planned_date`, and `actual_date` columns. It calculates delivery measures for each supplier and shows a risk level, a recent trend, and suggested actions. Your data stays in your browser; the page does not upload it.

## 5. Risk rules

- Deliveries are sorted by planned date. The latest 10 are counted, or all deliveries when there are fewer than 10.
- A delivery is late when its actual date is later than its planned date. Days late is the calendar-day difference; early and on-time deliveries count as zero.
- Late rate is the percentage of counted deliveries that were late. Average days late uses only late deliveries.
- Trend compares the latest five deliveries with the five before them. A higher late rate means “Getting worse,” a lower rate means “Improving,” and an equal rate (or fewer than six deliveries) means “Stable.”
- “On track” means below 10%. “Watch” means 10% through 30%. “High risk” means above 30%, or 20% through 30% with a “Getting worse” trend.
- The overall on-time summary uses every valid delivery in the file; supplier risk uses each supplier's latest 10.

## 6. How to use it

1. Open `index.html` in a recent web browser.
2. Choose **Load sample data** to try the example, or **Upload CSV** to choose your own CSV.
3. Select a supplier row to view its delivery history. Use **Download results as CSV** to save the supplier summary.
4. The live version is published with GitHub Pages: https://adi29102000-s.github.io/supplier-delay-early-warning/

Your uploaded data is processed locally in your browser and is not sent to GitHub or another service by this page.

## 7. Limitations

This is a prototype with simple rules and fictional sample data. It does not use real company data, predict future delivery dates, or account for holidays, supplier importance, or order value.

## 8. Next steps

- Add optional email alerts.
- Connect to SAP or another ERP system.
- Give more weight to important suppliers or high-value orders.
- Explore AI suggestions for supplier actions.

## 9. Built with

HTML, CSS, JavaScript, and GitHub Copilot.
