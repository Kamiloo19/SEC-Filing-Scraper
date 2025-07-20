# SEC-Filing-Scraper
This Python script retrieves and visualizes financial data for a specified company from the SEC's EDGAR database using the company's CIK (Central Index Key).
Below is a concise and professional description of the provided Python script's functionality in a GitHub repository's README file. It summarizes the script's purpose, features, and usage in a clear and engaging manner.

---

## SEC Filing Scraper - Financial Analysis and Visualization

This Python script retrieves and visualizes financial data for a specified company from the SEC's EDGAR database using the company's CIK (Central Index Key). It generates two types of visualizations: time-series plots of key financial metrics and donut charts comparing asset composition for the last two fiscal years. The script is designed for financial analysts, researchers, or enthusiasts interested in exploring public company financials.

### Features
1. **Time-Series Analysis**:
   - Fetches financial data for key metrics (e.g., Revenues, Net Income, Liabilities, Stockholders' Equity, Cash Flow from Operations) from SEC filings (10-K and 10-Q forms).
   - Plots each metric in a separate subplot with a line chart, showing trends over time.
   - Values are formatted in billions (USD) for readability, with data points marked for clarity.

2. **Asset Composition Analysis**:
   - Retrieves asset-related data for the latest two fiscal years from annual reports (10-K forms).
   - Visualizes the breakdown of assets (e.g., Cash, Marketable Securities, Inventory, etc.) using vertical donut charts.
   - Aggregates smaller asset categories into an "Other Assets" slice for simplicity (threshold: 4% of total assets).
   - Displays total assets in the center of each donut chart for quick reference.

3. **Customizable and Robust**:
   - Uses a predefined dictionary to map XBRL tags to user-friendly English labels.
   - Handles errors gracefully, skipping invalid or missing data while providing informative feedback.
   - Configurable for any company by updating the CIK code.

### Prerequisites
- **Python Libraries**: `requests`, `pandas`, `matplotlib`
- **Setup**: Install dependencies using:
  ```bash
  pip install requests pandas matplotlib
  ```
- **SEC EDGAR Access**: Ensure a valid `User-Agent` header (e.g., `yourname@yourdomain.com`) is provided to comply with SEC API requirements.

### Usage
1. Update the `cik` variable with the target company's CIK (e.g., `0000320193` for Apple Inc.).
2. Set your `User-Agent` in the `headers` variable.
3. Run the script:
   ```bash
   python sec_filing_scraper.py
   ```
4. The script will:
   - Fetch data from the SEC EDGAR API.
   - Generate a multi-subplot figure for time-series financial metrics.
   - Produce a vertical dual-donut chart comparing asset composition for the last two fiscal years.

### Output
- **Time-Series Plot**: A figure with subplots for each financial metric, showing historical trends with values in billions (USD).
- **Asset Composition Plot**: Two vertically arranged donut charts showing the proportion of asset categories for the latest two fiscal years, with total assets displayed prominently.

### Example
For CIK `0000320193` (Apple Inc.), the script will:
- Plot time-series data for Revenues, Net Income, Liabilities, Stockholders' Equity, and Cash Flow from Operations.
- Show asset breakdowns (e.g., Cash, Marketable Securities, Inventory) for the two most recent fiscal years.

### Notes
- Ensure a stable internet connection for API requests.
- The script skips invalid or missing data and provides error messages for debugging.
- Customize `concepts_to_plot` or `common_asset_tags` dictionaries to analyze different financial metrics or asset categories.

### License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---


