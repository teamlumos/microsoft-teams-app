# Lumos Microsoft Teams app

The app package for the Lumos app in Microsoft Teams. Install it to receive Lumos notifications in Teams and to approve access requests and complete manual provisioning tasks from adaptive cards.

## Download

[LumosTeams.zip](https://github.com/teamlumos/microsoft-teams-app/raw/main/LumosTeams.zip)

Upload the zip as-is. Don't unzip or repackage it. Teams requires `manifest.json` and both icons at the root of the archive.

To check the download, compare its SHA-256 with this value:

```bash
shasum -a 256 LumosTeams.zip
# b9e6ae189a44da9ea3a2100a5130ea4c10f163cb33e3bf0d7d37101b6a9c2c59
```

## Before you start

- You need a Microsoft Teams admin who can upload and publish apps to your organization's app scope.
- The Microsoft 365 / Entra ID integration must be connected in Lumos. See [Connecting Microsoft 365 / Entra ID](https://docs.lumos.com/integrations/library/microsoft-365-azure-ad-entra-id).

## Install

In Microsoft Teams:

1. Go to Apps > Manage your apps.
2. Click Upload an app, then upload `LumosTeams.zip` to your organization's app scope.
3. Publish the app so it's available to your employees. You can publish to the whole company or to a small test group first.

In Lumos:

1. Go to Settings > Notifications.
2. Enable the Microsoft Teams channel for the domains where you want notifications and tasks delivered.
3. Click Save Changes.

Users in those domains start receiving notifications and adaptive cards in Teams.

For the full walkthrough, see [Access Requests in Microsoft Teams](https://docs.lumos.com/for-admins/appstore/access-requests-in-microsoft-teams) and the notifications section of [Microsoft Teams](https://docs.lumos.com/integrations/library/microsoft-teams).

## If the upload is blocked

If your Teams tenant policy blocks custom app uploads, ask your Teams admin to allow uploading the Lumos app package. If that doesn't resolve it, contact [support@lumos.com](mailto:support@lumos.com).

## What's in the package

| File | Purpose |
| --- | --- |
| `manifest.json` | App definition: name, bot, personal tabs, and permissions |
| `color.png` | 192x192 color icon |
| `outline.png` | 32x32 outline icon |

The app is scoped to personal use. It has a bot for notifications, two personal tabs (Conversations and About), and requests the `notifications` and `openExternal` device permissions. Employees can't submit access requests from Teams. They submit through the AppStore, Albus, Slack, or a connected agent, and the resulting notifications and tasks appear in Teams.
