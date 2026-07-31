# MCSyncDrive - Privacy Policy

[English](PRIVACY.md) · [Português](pt-BR/PRIVACY.md)

Last updated: July 30, 2026

Document version: `mcsyncdrive-privacy-2026-07-30`

This Privacy Policy explains how MCSyncDrive ("MCSyncDrive", "the application",
"we", "us") handles information when you use the application on your Mac. The
application is developed and maintained by Magno Ciqueira under the Nexus
platform and processed under the Brazilian General Data Protection Law
(LGPD — Law No. 13,709/2018) and, where applicable, other data protection laws.

By installing or using MCSyncDrive, you acknowledge having access to this
policy.

## 1. Controller Identification

MCSyncDrive is developed and maintained by Magno Ciqueira, who is responsible
for the personal data processing described in this policy.

Privacy contact: [sync@mcnexus.app](mailto:sync@mcnexus.app)

## 2. What MCSyncDrive Does

MCSyncDrive is a native macOS application that connects to your Google Drive
account and transfers files between Google Drive and local storage devices (SSDs
or other volumes). All transfer operations are performed locally on your Mac
using rclone, a command-line tool bundled inside the application. No files,
previews, or metadata are uploaded to any server operated by Magno Ciqueira or
the Nexus platform.

## 3. Information Collected and How It Is Used

### 3.1 Google Account and Drive Access

MCSyncDrive connects to your Google account using OAuth 2.0. Depending on the
access scope you choose, the application may request:

- **`drive`** — read and write access to files your account can access in
  Google Drive, My Drive, Shared with me, and Shared Drives; or
- **`drive.readonly`** — read and download access only, with no ability to
  upload or modify files.

The application uses the scope you explicitly select. You can change the scope
by reconnecting your account from within the application.

Your name and email address may be displayed within the application to confirm
which account is connected. This information is read from your Google profile
and is never transmitted to any server other than Google's.

### 3.2 OAuth Tokens

Authentication tokens issued by Google are stored exclusively in the rclone
configuration file located at:

```
~/Library/Application Support/MCSyncDrive/rclone.conf
```

This file is encrypted by rclone. The encryption key is generated randomly for
your Mac, protected with AES-GCM, and stored at:

```
~/Library/Application Support/MCSyncDrive/Security/rclone-secret.v1
```

Tokens are never logged, never included in operation reports, and never
transmitted to any server operated by Magno Ciqueira or the Nexus platform.
File permissions for the configuration file are set to `0600` (owner read and
write only).

### 3.3 Local File Operations

MCSyncDrive reads and writes files on the storage volumes and Google Drive
folders you select. The application:

- accesses only the source and destination folders you explicitly choose for
  each operation;
- does not read, copy, or transmit your files to any server other than the
  Google Drive endpoint you configure;
- does not scan folders you have not selected;
- does not index or cache file contents beyond what rclone requires for transfer
  and verification.

### 3.4 Operation History and Logs

MCSyncDrive maintains a local operation history that records:

- project name and operation type;
- transfer direction, source, and destination paths;
- volume identifiers for external SSDs (path and UUID when available);
- timestamps for start and end of each operation;
- file and folder counts, total size, bytes transferred, average speed, and
  duration;
- transfer mode, verification type, and applied filters;
- rclone exit code and a summary of missing, different, or failed files;
- the name of the user who confirmed a cleanup operation.

This history is stored locally in:

```
~/Library/Application Support/MCSyncDrive/
```

Operation logs are stored in:

```
~/Library/Logs/MCSyncDrive/
```

None of this data is sent to any remote server. It is retained locally until
you clear the history from within the application or uninstall the application.

### 3.5 No Analytics or Telemetry

MCSyncDrive does not include analytics libraries, crash reporters, telemetry
agents, or advertising SDKs. No usage data is collected or transmitted
automatically.

## 4. Google Drive API and Data Minimization

The application accesses Google Drive solely through the Google Drive API using
your own Google account credentials. Only the data required to list, transfer,
and verify the files you select is requested. MCSyncDrive does not read Gmail,
Google Calendar, Google Contacts, or any other Google service.

The application does not share, sell, or use your Google Drive data for any
purpose other than the file transfer operations you initiate.

## 5. Use of rclone

MCSyncDrive bundles rclone ([rclone.org](https://rclone.org)) to perform file
transfers and verifications. rclone communicates directly with Google Drive on
your behalf using your OAuth token. The rclone process runs locally on your Mac
and does not relay data through any intermediary server operated by Magno
Ciqueira or the Nexus platform.

Third-party notices for rclone and its dependencies are included inside the
application bundle in `ThirdPartyNotices.txt`.

## 6. Permissions Requested

| Permission | Reason |
|---|---|
| Google Drive (read & write or read-only) | Perform file transfers and verifications you initiate |
| Local folder access (Finder picker) | Read from or write to the local SSD volumes you select |
| Network access | Connect to the Google Drive API on your behalf |

MCSyncDrive does not request access to your contacts, microphone, camera,
location, or any other system resource not listed above.

## 7. Data Stored on Your Mac

All application data remains on your Mac:

| Location | Contents |
|---|---|
| `~/Library/Application Support/MCSyncDrive/` | rclone configuration (encrypted), operation history, project data, manifests |
| `~/Library/Logs/MCSyncDrive/` | Operation and transfer logs |
| `~/Library/Caches/MCSyncDrive/` | Temporary remote listings (reconstructable, may be cleared by macOS) |

Uninstalling the application does not automatically remove these directories.
You can delete them manually if you wish to remove all local data.

## 8. Data Sharing

MCSyncDrive does not share your data with any third party, except:

- **Google LLC:** your files and credentials are transmitted to Google Drive
  through the Google Drive API as part of the transfer operations you initiate.
  Google's own
  [Privacy Policy](https://policies.google.com/privacy) and
  [API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy)
  apply to data processed by Google.

No other data is shared with any party. MCSyncDrive does not sell or rent data.

## 9. Security

MCSyncDrive applies the following measures to protect your data:

- OAuth tokens stored in an rclone-encrypted configuration file with `0600`
  permissions;
- encryption key protected with AES-GCM and bound to your Mac;
- no token logging in operation logs or history records;
- file paths passed as process arguments, not concatenated shell commands;
- network communication with the Google Drive API performed over HTTPS only.

## 10. Children and Minors

MCSyncDrive is a professional application intended for audiovisual
post-production workflows and is not directed to people under 18. We do not
intentionally collect data from children or minors.

## 11. Data-Subject Rights

Subject to applicable law, you may request:

- confirmation that processing takes place;
- access to data held about you;
- correction of inaccurate or outdated data;
- deletion of data, subject to legal and operational requirements.

Because MCSyncDrive stores all data locally on your Mac, you can inspect,
export, or delete your data at any time by accessing the directories listed in
Section 7. To exercise rights related to any data processed by Magno Ciqueira
outside the application, contact:

[sync@mcnexus.app](mailto:sync@mcnexus.app)

## 12. International Users and Transfers

MCSyncDrive is operated from Brazil. We seek to comply with the data-protection
requirements applicable to each relationship, including, where relevant, the
GDPR for residents of the European Economic Area and United Kingdom and privacy
laws applicable to California residents.

Because all application data is stored locally on your own device and is
transmitted only to Google's servers under your own account, no personal data
is transferred to servers operated by Magno Ciqueira outside Brazil.

## 13. Changes

This policy may be updated to reflect changes to the application, legal
requirements, or the services it integrates. The latest revision date will
appear at the beginning of the document. Material changes may be communicated
through the application repository or the support channel listed below.

## 14. Contact

- Privacy: [sync@mcnexus.app](mailto:sync@mcnexus.app)
- Technical support: [github.com/ciqueira/MCSync/issues](https://github.com/ciqueira/MCSync/issues)
