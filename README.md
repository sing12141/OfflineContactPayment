# Offline Contact Payment

Native Android (Java 17 + WebView) offline contact/payment tracker.

## Offline guarantees
- All application UI assets are local.
- No server, Firebase, Supabase, login, analytics, tracking, cloud database, or remote API.
- Contact/payment/remark/called data is persisted in WebView localStorage.
- CALL uses Android `ACTION_DIAL`; it never places a call automatically.
- Excel export uses the native bridge to save to public Downloads.

## Build
GitHub Actions builds the debug APK with JDK 17 and Gradle 8.11.1. Use the `workflow_dispatch` action for a manual build.

Expected output: `app/build/outputs/apk/debug/app-debug.apk`

## Data model
Storage key: `offline_contact_payment_v2`.
Each contact contains name, contact, dynamic year/session payments, called, calledAt, and multiple remarks.

## Excel
The application expects the bundled `app/src/main/assets/xlsx.full.min.js` SheetJS runtime and does not use a CDN. The runtime must be committed to the repository before Excel import/export can be considered complete.
