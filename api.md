## Introduction

Welcome to the API Documentation for FlipAnim!
All of the supported API methods are documented here.

The root URL for the API is
`/api/v1/`

All endpoints specified here will start with that URL.

## Authentication

Currently, to authenticate your requests, you'll need to log in. For more information on the login endpoint, click [here](#login) 

## Anim Methods

These methods allow for fetching, creating, updating, and deleting anims.
(TODO)

## Logging in and out

These endpoints allow for creating and destroying authenticated sessions.

### `POST /login`

To log in, send a POST request to /login with the following FormData fields.

| Field              | Expected Value |
| ------------------ | -------------- |
| username           | String         |
| password           | String         |
| h-captcha-response | String         |

### `POST /logout`

To log out, send a POST request to /logout. This terminates the session

## Comment Methods

These methods allow for fetching, creating, updating, and deleting comments on anims.

`GET /anims/:animId/comments`

Get all comments on an anim

`POST /anims/:animId/comments`

Add a new comment to an anim

`PUT /anims/:animId/comments/:commentId/`

Edit a comment on an anim

`DELETE /anims/:animId/comments/:commentId/`

Delete a comment on an anim

## User Methods

These methods allow for fetching, creating, updating, and deleting user info.

### GET /users/:userId

Get a user. See [User](#User)

### POST /users/

To create a user, pass in FormData with the following fields.

| Field              | Expected Value | Description                  |
| ------------------ | -------------- | ---------------------------- |
| username           | String         | The username of the new user |
| password           | String         | The password of the new user |
| h-captcha-response | String         | The captcha response         |

### PUT /users/:userId

Updates user info. Pass in FormData.

| Field            | Expected Value | Description                                                                        |
| ---------------- | -------------- | ---------------------------------------------------------------------------------- |
| currentPassword? | String         | The current password, for authentication. Required if updating `name` or`password` |
| name?            | String         | The new username of the updated user                                               |
| password?        | String         | The new password of the updated user                                               |
| avatarURL?       | String         | The ID of the anim the user is switching avatars to                                |
| bio?             | String         | The new About Me section of the updated user                                       |
| status?          | Object         | The new status. Properties for this are below                                      |

`status` argument properties

| Property | Expected Value | Description                                                   |
| -------- | -------------- | ------------------------------------------------------------- |
| type     | Number         | The status type. See [StatusType](#statustype)                |
| name?    | String         | The name of the status. If not provided, the status is reset. |

### DELETE /users/:userId

Deletes a user. Expects FormData.

| Property        | Expected Value | Description                                               |
| --------------- | -------------- | --------------------------------------------------------- |
| currentPassword | String         | The user's current password. Required for authentication. |

# Reference

## User

Example user object

```json
{
    "name": {
        "text": "never",
        "id": "00000"
    }, 
    "avatar": false,
    "anims": [],
    "notifications": [],
    "status": {
        "name": "gonna",
        "type": 2
    },
    "following": [],
    "followers": [],
    "password": "give",
    "bio": "you up",
    "creation": {
        "unix": 1646706752.353,
        "text": "2022-03-08T02:32:32.352Z"
    },
}
```

## StatusType

| Value | Name                |
| ----- | ------------------- |
| 0     | Invisible (Offline) |
| 1     | Online              |
| 2     | Idle                |
| 3     | Do Not Disturb      |

## 