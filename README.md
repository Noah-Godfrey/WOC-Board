# WOC Follow-Up Board

A phone-first follow-up tracker for work orders moving through the contractor lifecycle. It sits alongside your main database and answers one question: **what needs follow-up today?**

## Using it on your phone

1. Open the site link on your phone.
2. Add it to your home screen so it opens like an app:
   - **iPhone (Safari):** Share → Add to Home Screen
   - **Android (Chrome):** ⋮ menu → Add to Home screen (or Install app)
3. After the first visit it also works without a signal.

## How it works

- **Work order cards (WOCs)** show the Reference #, Work Order #, store, age, and Days Since Follow-Up. From S2 on they show the contractor; from S3 through S7 they show the ETA.
- **Green means Action Required. Grey means followed up.** Every card turns green again at 8am each day, except:
  - **S3 Contractor Accepted** cards wait until 8am on the ETA date.
  - **S11 Completed Invoice** cards never need action.
- Open a card and tap **Followed Up** to turn it grey. That resets its Days Since Follow-Up (DSF). If more comes up the same day, tap the grey button and confirm **Mark as Follow-Up Needed?** to turn it green again.
- **Notes** give a card context at its current stage (for example, "Waiting on PO from DM"). They show under the store name and are edited in the card's detail view, which also shows when the note was last updated and in which stage.
- **Emergency** work orders: switch on Emergency when you add the card, or later in its detail view. The card's stage band gets white diagonal stripes and an Emergency label in every stage, through S11, until you switch it off or delete the card.
- Green cards sort in this order: **emergencies**, then **today's ETAs**, then the highest **DSF**. Grey cards drop to the bottom, with emergencies first among them.
- **Next Stage** and **Previous** move a card. Moving into S2 asks for the contractor, and moving into S3 asks for the ETA. Moving from S3 back to S2 asks for a contractor again. Every move shows an **Undo** button for 5 seconds.

### Stages

| # | Tab | Full name |
|---|-----|-----------|
| S1 | Created | Created |
| S2 | Sent | Dispatch Sent |
| S3 | Accepted | Contractor Accepted |
| S4 | Onsite | Onsite Contractor |
| S5 | Quote | Return Needs Quote |
| S6 | Pending | Quote Needs Approval |
| S7 | Approved | Approved Quote |
| S8 | Repaired | Work Complete |
| S9 | Invoice | Invoice Needed |
| S10 | Submitted | Submitted Invoice |
| S11 | Completed | Completed Invoice |

## Your data

Everything is saved in your phone's browser, on that device only. Nothing is sent anywhere, and this GitHub repository holds only the app's code, never your work orders.

Because the data lives on one device, **make backups**: Overview → Settings → **Create Backup** saves a `.json` file you can keep in iCloud Drive, Google Drive, or email to yourself. **Load Backup** restores one (on the same phone or a new one).

Clearing your browser's website data will erase the board, so back up first.

## Settings

- **Manage Contractors**: edit names, emails, phone numbers, and notes.
- **Create Backup / Load Backup**
- **EOM Completion Wipe**: removes the cards in S11 Completed Invoice and nothing else.
- **Reset All Data**: deletes every work order (two confirmations). The contractor list stays.

## Files

- `index.html` is the whole app (styles, markup, and code in one file).
- `manifest.webmanifest`, `icons/`, and `sw.js` let it install to the home screen and work offline.
