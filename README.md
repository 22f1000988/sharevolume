# Company Stock Shares Outstanding Dashboard

This project provides a single-page, responsive HTML application built with Tailwind CSS to display the maximum and minimum common stock shares outstanding for a given company, sourced from SEC XBRL data.

## Features

*   **Dynamic CIK Lookup**: Fetch and display data for any 10-digit CIK by appending it to the URL (e.g., `index.html?CIK=0001018724`).
*   **Responsive Design**: Built with Tailwind CSS for an optimal viewing experience across various devices.
*   **Live Data**: Retrieves up-to-date shares outstanding data directly from the SEC EDGAR API.
*   **Max/Min Analysis**: Highlights the highest and lowest common stock shares outstanding values since fiscal year 2021.

## Technologies Used

*   **HTML5**: Structure of the web page.
*   **Tailwind CSS**: Utility-first CSS framework for styling.
*   **JavaScript (ES6+)**: For fetching and processing data, and dynamically updating the UI.
*   **SEC EDGAR API**: Data source for company financial information.

## Getting Started

To run this application, simply open the `index.html` file in your web browser. No special server setup is required for basic functionality.

### Prerequisites

*   A modern web browser.

### Installation

1.  Clone this repository or download the `index.html`, `README.md`, `LICENSE`, and `uid.txt` files.
2.  Ensure all files are in the same directory.

### Usage

*   **Default View**: Open `index.html` to view the shares outstanding data for Advanced Micro Devices (AMD) (CIK: 0000002488).
*   **Custom CIK**: To view data for a different company, append `?CIK=<your_10_digit_cik>` to the URL.
    *   Example: `index.html?CIK=0001018724` (for Apple Inc.)

## Data Source

The data is fetched from the SEC EDGAR API's XBRL company concept endpoint.
Specifically, `https://data.sec.gov/api/xbrl/companyconcept/CIK<CIK>/dei/EntityCommonStockSharesOutstanding.json`.

**Note on User-Agent and Proxy**:
The SEC guidance recommends setting a descriptive `User-Agent` header for API requests. For client-side JavaScript, direct control over this header is limited due to browser security policies. When fetching data for custom CIKs, a proxy (e.g., AIPipe) is recommended to handle cross-origin requests, rate limiting, and to properly set the `User-Agent` header. The provided `index.html` demonstrates how to integrate a proxy endpoint, but a functional proxy service would need to be configured separately. For simplicity, this client-side code directly fetches from SEC, which might encounter CORS issues depending on browser and environment.

## License

This project is open-source and available under the MIT License. See the `LICENSE` file for more details.
