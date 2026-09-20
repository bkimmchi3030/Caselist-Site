# Privacy Policy for Caselist Mailer

**Last updated: September 20, 2026**

Caselist Mailer (listed as "Caselist" on the Chrome Web Store) is a Chrome extension that automates disclosure on openCaselist, the site where competitive debaters publish the rounds they have debated and the documents they read in them.

This policy explains what the extension accesses, why, and where that information goes.

## Summary

Caselist has no backend server. There is no account to create, no analytics, and no telemetry. Everything the extension reads is processed inside the user's own browser. The only time information leaves the user's device is when the user deliberately publishes a round or a document to openCaselist — the destination they chose, using their own openCaselist account.

## Google user data the extension accesses

With the user's explicit consent on Google's sign-in screen, Caselist requests one Google scope, `https://www.googleapis.com/auth/gmail.readonly`, and no other. Through it the extension accesses the following, from the user's own Gmail account only:

- **The account's email address**, from the Gmail profile.
- **Search results** for three searches: round email chains sent by the user or by a partner the user named, within the look-back window the user set; Tabroom.com pairing emails, including pairings the user or their partner forwarded; and whether any mail exists from a partner address the user typed, which is a yes-or-no check that opens no message.
- **The email chains the first search finds.** Gmail returns each chain as a whole thread. From the chain the extension uses the subject line, the names and sizes of attached files, and, for every message on it, the From, To and Cc headers, the date, and Gmail's Sent label. It uses body text (or Gmail's short snippet when a message has no plain-text part) only from messages sent by the user or their partner. Body text from anyone else on the chain is discarded without being parsed, displayed or stored.
- **The body text of Tabroom pairing emails.**
- **One attachment at a time:** the file the user selects, downloaded when they press Publish.

The extension cannot send, delete, or modify mail; the read-only scope enforces that technically. It does not index, copy, or retain the mailbox.

## How the extension uses Google user data

Google user data is used only to provide the features the user sees in the side panel:

- The email address tells the user's own messages apart from other people's on a chain, for example so the user is never suggested as the judge.
- Search results and chain contents build the list of rounds and documents shown in the panel, and pre-fill the tournament, round, side, opponent and judge in the publish form. Every pre-filled value is visible and editable before anything is published.
- Pairing emails fill in the same round details, and power Autosearch, which looks up the user's next opponent on openCaselist.
- The partner-address check tells a mistyped address apart from a quiet inbox during setup.
- The selected attachment is uploaded to openCaselist when the user presses Publish.

Google user data is not used for advertising, is not sold, is not used to build profiles, and is not used to develop, improve or train AI or machine-learning models.

## Sharing and transfer of Google user data

Google user data goes to exactly one place, and only when the user presses Publish: openCaselist (`https://api.opencaselist.com`), through the user's own signed-in session. What is sent is the file the user chose, its file name, and the round details shown in the form. Nothing is sent to the developer or to any other party, because there is no server to receive it.

## How Google user data is protected

- **It stays on the device.** Processing happens inside the user's browser. There is no backend, so neither the developer nor any other person can access a user's mail.
- **Encrypted in transit.** The extension makes network requests only to the Gmail API and to openCaselist, always over HTTPS (TLS).
- **The access token is held by Chrome, not by the extension.** The extension asks Chrome for the token at each request, never writes it to storage, and sends it only to the Gmail API. A token Gmail rejects is discarded immediately.
- **Mail content is never written to disk.** Message text, subjects, sender lists, file names and attachments exist only in memory while the panel is open. A downloaded attachment is held only between the download and the upload, then deleted.
- **What is stored is minimal and private.** The only Gmail-derived values kept are the signed-in address and, for up to 200 published documents, the Gmail message id and attachment id. They sit in `chrome.storage.local`, which only this extension can read.
- **Read-only by design.** The scope cannot send, modify or delete anything in the account.
- **Revocable at any time** at myaccount.google.com/permissions.

## Other things the extension accesses

**openCaselist.** The extension reads caselist data — schools, teams, rounds, and cites, all of which are published publicly by debaters on openCaselist — and writes new rounds and documents when the user chooses to publish. It also asks openCaselist for the user's current Tabroom rounds, where openCaselist makes them available, to fill in round details.

**Local storage.** The extension uses `chrome.storage.local` to hold the following, and nothing else: the caselist, school, and team code chosen in setup; the partner email addresses the user entered; the mail look-back window; the user's display and behaviour preferences, such as the Autoselect choice and the tournament numbering style; which half of the extension (mailer or searcher) was last open; the signed-in Gmail address, so it can tell the user apart from other people on a mail chain; a cached index of the schools and teams on the chosen caselist, so searching is fast and works offline; and a record of the rounds the user has published (the Gmail message id and attachment id of the file, and the caselist, school and team it went to, with no mail content, limited to the 200 most recent), so the panel can mark a document as published and never post it twice. All of this stays in the user's browser.

## What the extension does not do

- It does not sell or transfer information to third parties.
- It does not use information for advertising, ad personalization, or ad targeting.
- It does not use information for creditworthiness or lending purposes.
- It does not allow humans to read the user's data. The developer has no access to it, because there is no server that receives it.
- It does not read browsing history, and does not read pages other than openCaselist.
- It does not use the data for any purpose unrelated to the extension's single purpose described above.
- It does not use information to develop, improve or train AI or machine-learning models.

## Credentials

Caselist is designed so that it never holds a credential.

The Google OAuth token is issued by Chrome through `chrome.identity` and stays on the device; it is used only for requests to the Gmail API and is never transmitted anywhere else.

openCaselist authenticates with a session cookie scoped to its own origin. Rather than asking for a password or storing a session token, the extension relays its openCaselist requests through a content script in the user's already signed-in openCaselist tab, so the browser attaches the cookie itself. The extension never reads or stores that token.

## Google API Services User Data Policy

Caselist's use and transfer of information received from Google APIs adheres to the [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy), including the Limited Use requirements.

## Data retention and deletion

The extension retains nothing on any server, because there is no server. Removing the extension from Chrome deletes all of its local storage. The extension's "Rebuild the index" option replaces the cached openCaselist index.

Access to Gmail can be revoked at any time at [myaccount.google.com/permissions](https://myaccount.google.com/permissions), independently of whether the extension is installed.

Rounds and documents that the user has published to openCaselist are governed by openCaselist's own policies and can be edited or removed through that site.

## Children's privacy

Caselist is used by high school and college debaters. It collects no information beyond what is described above, requires no account with the developer, and does not build user profiles.

## Changes

If this policy changes, the updated version will be posted at this URL with a revised date above.

## Contact

Questions about this policy can be sent to jinah0620@gmail.com.
