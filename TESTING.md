
# Pixela Photographer Portal — Local Test Guide

## Prerequisites
- Node.js 18+
- npm 9+

## Install
```bash
npm install
```

## Run (Dev)
```bash
npm run dev
# open the shown localhost URL
```

## Build (Preview)
```bash
npm run build
npm run preview
```

## Demo Logins
- **Event Code**: `PIXELA2025` (demo)
- **OTP (demo)**: `123456`
- **Customer Portal**: Navigate via the Event page after login.

## Common Fixes in this build
- Inquiry form field names fixed (`lastName`, correct input types for email & phone).
- OTP demo normalized to `123456` across the flow.
- Added `src/lib/pdf.js` with robust html2pdf settings for non-blank receipts.
- Customer Portal now shows studio branding (logo, name, contact) at the top.
- Receipt root ensures white background to avoid transparent/blank PDFs.

If you still see blank PDFs:
- Make sure the Receipt section is visible when you click **Download Receipt**.
- Try again after images finish loading.
- On Safari/iOS, prefer Chrome for PDF download.
