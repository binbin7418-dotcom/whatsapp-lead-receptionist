# WhatsApp Lead Receptionist — n8n workflow sample

An n8n workflow for local businesses that turns WhatsApp messages into scored, logged, answered leads — including after hours.

## What it does
1. **Webhook intake** receives WhatsApp Cloud API events
2. **Normalize (Code)** cleans the payload into a standard lead record
3. **Score & Route (Code)** scores the lead (Hot ≥ 70, Warm ≥ 45) from service, budget and urgency signals
4. Malformed payloads go to a **dead-letter sheet** instead of breaking the flow
5. Every lead is **logged to Google Sheets**
6. **Hot leads** trigger an instant **Gmail alert** to the owner
7. **Auto-reply**: normal text inside WhatsApp's 24h window, template message to reopen the window after it expires

## Testing
The two Code nodes (normalize + score/route) were verified locally with 41 assertions covering scoring thresholds, malformed payloads and routing.

## Setup
Import the JSON into n8n, then connect your own credentials: WhatsApp Cloud API, Google Sheets, Gmail. Add your scoring keywords, services and reply texts in the Code nodes and sticky note.

## Credits & licence
Original enhanced sample by visionwei. Built with patterns from the community n8n workflow collections (MIT — see LICENSE-BASE-MIT.txt). Free to use and adapt with attribution.
