---
sidebar_position: 1
---

# Permissions

Mikoto permission system uses a bitset to represent permissions. Keep in mind that the Mikoto API will return the bitset as a string, and you will need to convert it to a number before you can use it. You should be using your language's big integer to handle the bitset.

## Management Permissions

### `Superuser` (1 << 0)

Grants all control over the space, overriding all permissions. Gives the user exact same permissions as being the server owner.

### `ManageSpace` (1 << 1)

Edit space settings.

### `ManageChannel` (1 << 2)

Edit/Rename/Delete all channels, and subchannels. Do not use this role for granting access for subchannel management.

### `ManageRoles` (1 << 3)

Create/Delete new roles. Cannot create or delete roles equal or above the rank of user, or create a new role to be greater than existing role.

### `ManageMemberRoles` (1 << 4)

Ability to modify permissions of users below them. Cannot modify users equal or below the rank, or grant any users equal or greater rank (unless overridden by superuser)

### `ManageMemberProfile`

Ability to edit the space profile of other users with lower rank.

### `ManageInvites`

Ability to delete messages.

### `ManageMessages`

Ability to delete messages.

### `Ban`

Ability to kick and ban users.

## Channel Permissions

### `ReadChannel`

Ability to read channel. In voice, this means that the user will be able to spectate, but not participate in conversation.

### `SendInChannel`

Ability to send message in the channel.

### `CreateSubChannel`

Ability to create subchannels in a given channel, as well as delete threads created by self.

### `ManageSubchannels`

Superset of CreateSubchannel. Gives the ability to create threads and subchannels, as well as to delete and move them.
