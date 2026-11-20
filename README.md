# RENDEVO — Auto Repair

Mobile-first French booking-request website for an automotive garage.

## Live setup

- Frontend: `index.html`
- Backend: Google Apps Script Web App
- Backend endpoint is configured in `index.html` as `API_URL`.
- Apps Script actions used by this frontend:
  - `GET ?action=init&callback=...` to load the garage name.
  - `GET ?action=availability&date=YYYY-MM-DD&callback=...` to load open time slots.
  - `POST action=book` to submit a booking request through a hidden iframe.

## Publish with GitHub Pages

1. Open **Settings → Pages** in this repository.
2. Under **Build and deployment**, select **Deploy from a branch**.
3. Choose branch **main** and folder **/(root)**, then save.
4. Wait for GitHub Pages to publish.

## Before using it for a real garage

1. In Apps Script, edit `SETTINGS.BUSINESS_NAME` and `SETTINGS.ADMIN_EMAIL`.
2. Confirm the timezone, opening days and hours, service list, and Calendar account.
3. Run `setupRendevo()` once and authorize it.
4. Deploy as a Web App with **Execute as: Me** and access set to **Anyone**.
5. Test a booking request end-to-end and confirm it appears in the sheet and Calendar and that emails are delivered.
6. Configure the garage's real contact details and terms before sharing the link.

**Important:** customers submit a request, not a confirmed repair appointment. The garage must confirm or reject the request. A 30-minute slot blocks intake time only; it does not estimate or guarantee repair duration.
