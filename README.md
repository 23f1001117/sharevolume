# SEC Entity Common Stock Shares Outstanding Viewer

This single-page responsive web application fetches and displays the maximum and minimum "Entity Common Stock Shares Outstanding" data for a given company, sourced directly from the SEC EDGAR API.

## Features

-   **Company Data Display:** Shows the `entityName` and highlights the highest and lowest shares outstanding values, along with their respective fiscal years, for entries with `fy > 2020` and a numeric `val`.
-   **Default Company:** By default, the application displays data for Arista Networks (CIK: `0001596532`).
-   **Dynamic CIK Loading:** The application supports loading data for any 10-digit CIK by appending `?CIK=YOUR_CIK_NUMBER` to the URL (e.g., `index.html?CIK=0001018724`). The page updates dynamically without a full reload.
-   **Responsive Design:** Built with Tailwind CSS, ensuring a consistent and user-friendly experience across various devices.
-   **Loading Indicator:** Provides visual feedback while data is being fetched.

## How to Use

1.  **Open `index.html`:** Simply open the `index.html` file in your web browser. It will automatically load Arista Networks' data.
2.  **View Another Company:** To view data for a different company, append the `?CIK=` query parameter to the URL in your browser's address bar. For example, to view Apple Inc.'s data (CIK: `0000320193`), you would navigate to:
    `file:///path/to/your/index.html?CIK=0000320193` (or `http://localhost/index.html?CIK=0000320193` if served via a local web server).

## Technical Details

-   **Frontend:** HTML, CSS (Tailwind CSS via CDN), JavaScript.
-   **Data Source:** SEC EDGAR API (`https://data.sec.gov/api/xbrl/companyconcept/`).
-   **CORS Proxy:** Uses `https://api.allorigins.win/raw?url=` to bypass CORS restrictions for client-side API requests to the SEC endpoint. While a User-Agent header is included in the fetch request, due to browser security policies and the use of a public CORS proxy, its direct transmission to the SEC API cannot be guaranteed from the client-side.

## Project Structure

-   `index.html`: The main single-page application file.
-   `README.md`: This file.
-   `LICENSE`: The MIT License for this project.
-   `uid.txt`: An attachment provided as-is (not directly used in `index.html`).