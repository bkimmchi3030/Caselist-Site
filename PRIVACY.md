# Privacy Policy for Caselist

**Last updated: September 16, 2026**

Caselist is a Chrome extension that automates disclosure on openCaselist, the site where competitive debaters publish the rounds they have debated and the documents they read in them.

This policy explains what the extension accesses, why, and where that information goes.

## Summary

Caselist has no backend server. There is no account to create, no analytics, and no telemetry. Everything the extension reads is processed inside the user's own browser. The only time information leaves the user's device is when the user deliberately publishes a round or a document to openCaselist — the destination they chose, using their own openCaselist account.

## What the extension accesses

**Gmail (read-only).** With the user's explicit Google sign-in consent, Caselist requests the `gmail.readonly` scope and reads the user's own mailbox to locate two things:

- Pairing emails from Tabroom.com, to extract the tournament, round, side, and opponent for a debate round.
- Speech documents sent on round email chains, so they can be published without being downloaded and re-uploaded by hand.

The only Google scope requested is `https://www.googleapis.com/auth/gmail.readonly`; no other Google data is accessed.

The extension only reads mail. It cannot send, delete, or modify messages, and the read-only scope makes that technically enforced rather than a promise. Mail is searched for the specific messages described above; the extension does not index, copy, or retain the user's mailbox.

On a round's email chain, the extension reads the From, To, and Cc headers of the messages on it to identify who was on the chain — for example, to suggest the judge's name. It does not read the content of any message other than the user's own and their partner's.

**openCaselist.** The extension reads caselist data — schools, teams, rounds, and cites, all of which are published publicly by debaters on openCaselist — and writes new rounds and documents when the user chooses to publish.

**Local storage.** The extension uses `chrome.storage.local` to hold exactly the following: the caselist, school, and team code chosen in setup; the partner email addresses the user entered; the mail look-back window; which half of the extension (mailer or searcher) was last open; the signed-in Gmail address, so it can tell the user apart from other people on a mail chain; and a cached index of the schools and teams on the chosen caselist, so searching is fast and works offline. All of this stays in the user's browser.

## What the extension does not do

- It does not sell or transfer information to third parties.
- It does not use information for advertising, ad personalization, or ad targeting.
- It does not use information for creditworthiness or lending purposes.
- It does not allow humans to read the user's data. The developer has no access to it, because there is no server that receives it.
- It does not read browsing history, and does not read pages other than openCaselist.
- It does not use the data for any purpose unrelated to the extension's single purpose described above.

## Credentials

Caselist is designed so that it never holds a credential.

The Google OAuth token is issued by Chrome through `chrome.identity` and stays on the device; it is used only for requests to the Gmail API and is never transmitted anywhere else.

openCaselist authenticates with a session cookie scoped to its own origin. Rather than asking for a password or storing a session token, the extension relays its openCaselist requests through a content script in the user's already signed-in openCaselist tab, so the browser attaches the cookie itself. The extension never reads or stores that token.

## Google API Services User Data Policy

Caselist's use and transfer of information received from Google APIs adheres to the [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy#additional_requirements_for_specific_api_scopes), including the Limited Use requirements.

## Data retention and deletion

The extension retains nothing on any server, because there is no server. Locally cached data can be cleared at any time by using the extension's "Rebuild the index" option or by removing the extension from Chrome, which deletes its local storage.

Access to Gmail can be revoked at any time at [myaccount.google.com/permissions](https://myaccount.google.com/permissions), independently of whether the extension is installed.

Rounds and documents that the user has published to openCaselist are governed by openCaselist's own policies and can be edited or removed through that site.

## Children's privacy

Caselist is used by high school and college debaters. It collects no information beyond what is described above, requires no account with the developer, and does not build user profiles.

## Changes

If this policy changes, the updated version will be posted at this URL with a revised date above.

## Contact

Questions about this policy can be sent to jinah0620@gmail.com.
