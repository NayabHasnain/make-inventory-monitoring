# Safe Setup Guide

## Requirements

- A Make.com account
- A Gmail account or approved Gmail connection
- A Google Sheet for the monitoring log

Suggested sheet columns:

1. Alert Timestamp
2. Products Scanned
3. Reorder Products
4. Email Status

## Import and configure

1. In Make, create a new scenario.
2. Open the scenario menu and select **Import Blueprint**.
3. Import `workflow/inventory-monitoring.sanitised.json`.
4. Keep the scenario inactive while configuring it.
5. Open the Gmail module and create or select your own connection.
6. Replace `inventory-alerts@example.com` with the intended alert recipient.
7. Open the Google Sheets module and create or select your own connection.
8. Replace `REPLACE_WITH_SPREADSHEET_ID` and `REPLACE_WITH_SHEET_NAME` with your own sheet details.
9. Confirm that the **Reorder Required** filter is `stock <= 10`.
10. Select **Run once** and inspect every module output.
11. Confirm that the email contains only intended demo or business data and that one log row is added.
12. Activate or schedule the scenario only after the test succeeds.

## Safety checklist before publishing

- Export a fresh copy only after disconnecting or sanitizing account-specific fields.
- Remove personal recipients, connection IDs, spreadsheet IDs, webhook URLs, tokens, and customer data.
- Use fictional or public demo data in screenshots.
- Review screenshots for account names, browser profiles, URLs, and notifications.
- Never commit `.env` files or original private exports.

## Notes

The included HTTP module reads from DummyJSON, a public demo source. Replace it with a production API only after reviewing that API's authentication, privacy, rate limits, and terms.
