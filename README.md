# Free WHMCS Zoho Books Module - Indian GST Act Compliant

Looking for the best **Free WHMCS Zoho Books Module**? The Hostpug Zoho Books Sync Module provides a seamless, real-time automated integration between your WHMCS billing platform and Zoho Books accounting software. 

Specially designed to comply strictly with the **Indian GST Act**, this **Free WHMCS GST Module** intelligently categorizes transactions, accurately maps Place of Supply, and files invoices perfectly for your GSTR-1 returns. Whether you are billing domestic B2B/B2C clients or handling overseas exports, this module completely automates your accounting compliance.

## Screenshots

*(Add screenshots here showing the Dashboard, Settings, Migration tab, etc.)*
<!-- TODO: Add image links like ![Dashboard Screenshot](link/to/image.png) -->

## Features of module

*   **Automated Invoice Syncing:** Instantly pushes WHMCS invoices to Zoho Books when marked as Paid. Line items, taxes, and transaction gateways are mapped precisely for effortless accounting.
*   **Indian GST Act Compliance Engine:** A true Free WHMCS GST Module that automatically maps the Place of Supply and categorizes clients into the appropriate GST treatments (B2B, B2C, or Export) based on their state and country data.
*   **Export Zero-Rated Tax Automation (IGST 0%):** Automatically queries your Zoho Books account for the "IGST 0%" tax ID and seamlessly applies it to all line items for overseas export customers, guaranteeing your export invoices correctly appear in the GSTR-1 tables.
*   **Smart State Code Mapping:** Automatically maps standard WHMCS state abbreviations (like AP) to Zoho's strict 2-letter Indian GST state codes (like AD for Andhra Pradesh) to prevent API validation errors.
*   **Refund & Credit Note Automation:** Automatically generates and applies GST-compliant Credit Notes in Zoho Books when an invoice is marked as Refunded in WHMCS.
*   **Advanced Currency Handling:** Converts foreign currency invoices (e.g., USD, GBP, EUR) to INR using accurate historical exchange rates based on the original invoice payment date.
*   **Customer Sync & Caching:** Automatically creates or matches contacts in Zoho Books. Local caching prevents redundant API calls and keeps operations lightning fast.
*   **Bulk Data Migration Tool:** A dedicated UI allows administrators to bulk migrate older, unsynced historical invoices and refunds directly into Zoho Books with detailed progress tracking.
*   **Account Credit Support:** Properly handles invoices paid partially or entirely via WHMCS account credit, logging them as "Customer Credit" payments in Zoho Books.
*   **Comprehensive API Logging:** Features a built-in API log viewer to inspect raw JSON request and response payloads for easy debugging and audit trails.
*   **Over-The-Air Updates:** Built-in mechanism to check for and install updates directly from GitHub.

## Prerequisites

*   WHMCS 8.x or higher
*   PHP 7.4 or higher
*   A Zoho Books Account with API access enabled (India Edition Recommended for GST features)
*   Zoho API Client ID and Client Secret (generated via Zoho API Console)
*   A valid Hostpug Module License Key

## How to install

1.  Download the latest release ZIP file and extract its contents.
2.  Upload the `Zohosync_hp` folder to the `modules/addons/` directory of your WHMCS installation.
3.  Log in to your WHMCS Admin Area.
4.  Navigate to **System Settings** > **Addon Modules**.
5.  Locate the **Zoho Books Sync** module and click **Activate**.
6.  Click **Configure**, select the administrative roles that should have access (e.g., Full Administrator), and save your settings.

## How to get Free WHMCS Zoho Module License

1. Visit the Hostpug portal: [https://my.hostpug.in/login](https://my.hostpug.in/login)
2. Register for an account or log in to your existing account.
3. Navigate to the Products/Services section and claim your **Free WHMCS Zoho Module License**.
4. Once generated, copy the License Key from your dashboard.
5. In your WHMCS Admin Area, go to **System Settings** > **Addon Modules** > **Configure** for this module, and paste your License Key.

## Configuration and Setup

### 1. Zoho API Authentication
Before this Free WHMCS Zoho Books Module can sync data, you must authorize it with Zoho:
1.  Navigate to **Addons** > **Zoho Books Sync**.
2.  On the Dashboard tab, click the **Authorize with Zoho** button.
3.  You will be redirected to Zoho to grant permissions. Upon approval, you will be returned to the WHMCS dashboard, and your connection status will display as "Connected".

### 2. Item Mapping
Before invoices can be synced, the module requires a precise mapping between your WHMCS product categories and your Zoho Books inventory/service items. 

**Important Prerequisite:** You must first log in to your Zoho Books dashboard and manually create a generic Item for each product category you sell (e.g., "Shared Hosting", "Domain Registration", "Late Fee").

Once the items exist in Zoho Books:
1.  Navigate to the **Setup** tab within the WHMCS module.
2.  Ensure your Organization ID is selected.
3.  Enter the corresponding **Zoho Item ID** for each category block provided in the settings.
4.  Click **Save Settings**.

## Usage guide

### Dashboard
The Dashboard provides a high-level overview of your integration health. You can monitor your daily Zoho API limits, verify connection status, and review a quick summary of synced GST data (IGST, CGST, SGST).

### Bulk Migration
To sync historical invoices that were generated before the module was installed:
1.  Navigate to the **Migration** tab.
2.  Select the target month. The system will identify all Paid or Refunded invoices that do not exist in Zoho Books.
3.  Click **Start Migration**. 
4.  The system will process the invoices sequentially. Upon completion, a final report will display successful syncs and any failures. You can retry failed invoices directly from this report.

### Invoices & Credit Notes Management
The **Invoices** and **Credit Notes** tabs serve as your primary reporting interfaces.
*   View all invoices processed by the system along with their exact conversion rates and Zoho Invoice IDs.
*   Filter records by month, supply type (B2B, B2C, Export), or use the search bar.
*   If an invoice fails to sync during an automated hook, it will be flagged here in red. You can review the exact API error and click **Retry** to push it again.
*   Export the current view to a CSV file for accounting purposes.

### API Logs
For troubleshooting, the **Logs** tab records every outbound request sent to the Zoho API. You can click "View" on any log entry to inspect the raw JSON payload and the exact response received from Zoho Books.

## Support

This **Free WHMCS GST Module** is developed and maintained by [Hostpug](https://www.hostpug.in/). 

For any bugs, feature requests, or technical support, please contact our team at **support@hostpug.in**.
