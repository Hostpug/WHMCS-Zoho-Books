# WHMCS Zoho Books Sync Module

This WHMCS addon module provides a seamless, automated integration between your WHMCS billing system and Zoho Books. Designed for reliability and compliance, it accurately maps clients, invoices, payments, and refunds into Zoho Books in real-time, while offering a robust bulk migration engine for historical data.

## Key Features

*   **Automated Invoice Syncing:** Instantly pushes WHMCS invoices to Zoho Books when marked as Paid. Line items, taxes, and transaction gateways are mapped precisely.
*   **Refund & Credit Note Automation:** Automatically generates and applies Credit Notes in Zoho Books when an invoice is marked as Refunded in WHMCS.
*   **Advanced Currency Handling:** Converts foreign currency invoices (e.g., USD) to INR using accurate historical exchange rates based on the original invoice payment date.
*   **GST Compliance Engine:** Intelligently maps the Place of Supply and categorizes clients into appropriate GST treatments (B2B, B2C, or Export) based on state and country data.
*   **Customer Sync & Caching:** Automatically creates or matches contacts in Zoho Books. Local caching prevents redundant API calls and keeps operations fast.
*   **Bulk Data Migration:** A dedicated UI allows administrators to bulk migrate older, unsynced invoices and refunds directly into Zoho Books with detailed progress tracking.
*   **Account Credit Support:** Properly handles invoices paid partially or entirely via WHMCS account credit, logging them as "Customer Credit" payments in Zoho.
*   **Comprehensive Logging:** Features a built-in API log viewer to inspect raw request and response payloads for easy debugging and audit trails.
*   **Over-The-Air Updates:** Built-in mechanism to check for and install updates directly from GitHub.

## Prerequisites

*   WHMCS 8.x or higher
*   PHP 7.4 or higher
*   A Zoho Books Account with API access enabled
*   Zoho API Client ID and Client Secret (generated via Zoho API Console)

## Installation

1.  Download the latest release and extract the contents.
2.  Upload the `Zohosync_hp` folder to the `modules/addons/` directory of your WHMCS installation.
3.  Log in to your WHMCS Admin Area.
4.  Navigate to **System Settings** > **Addon Modules**.
5.  Locate the module and click **Activate**.
6.  Click **Configure**, select the administrative roles that should have access, and enter your License Key, Zoho Client ID, and Zoho Client Secret.
7.  Save the configuration.

## Configuration & Setup

### 1. Zoho API Authentication
Before the module can sync data, you must authorize it with Zoho:
1.  Navigate to **Addons** > **Zoho Books Sync**.
2.  On the Dashboard tab, click the **Authorize with Zoho** button.
3.  You will be redirected to Zoho to grant permissions. Upon approval, you will be returned to the WHMCS dashboard, and your connection status will display as "Connected".

### 2. Item Mapping
The module must know which Zoho Books Items correspond to your WHMCS products and fees.
1.  Navigate to the **Setup** tab within the module.
2.  Ensure your Organization ID is selected.
3.  Map the default Zoho Item IDs for each category (Shared Hosting, Reseller Hosting, Domains, Late Fees, Handling Fees, etc.). 
4.  Click **Save Settings**.

*Note: You must create these items manually in Zoho Books first to obtain their Item IDs.*

## Usage Guide

### Dashboard
The Dashboard provides a high-level overview of your integration health. You can monitor your daily Zoho API limits, verify connection status, and review a quick summary of synced tax data (IGST, CGST, SGST).

### Bulk Migration
To sync historical invoices that were generated before the module was installed:
1.  Navigate to the **Migration** tab.
2.  Select the target month. The system will identify all Paid or Refunded invoices that do not exist in Zoho Books.
3.  Click **Start Migration**. 
4.  The system will process the invoices sequentially. Upon completion, a final report will display successful syncs and any failures. You can retry failed invoices directly from this report.

### Invoices & Credit Notes Management
The **Invoices** and **Credit Notes** tabs serve as your primary reporting interfaces.
*   View all invoices processed by the system along with their exact conversion rates and Zoho Invoice IDs.
*   Filter records by month, supply type (B2B/B2C/Export), or use the search bar.
*   If an invoice fails to sync during an automated hook, it will be flagged here in red. You can review the exact API error and click **Retry** to push it again.
*   Export the current view to a CSV file for accounting purposes.

### API Logs
For troubleshooting, the **Logs** tab records every outbound request sent to the Zoho API. You can click "View" on any log entry to inspect the raw JSON payload and the exact response received from Zoho Books.

## Support
For technical assistance, bug reports, or feature requests, please contact the development team or open an issue on the repository.
