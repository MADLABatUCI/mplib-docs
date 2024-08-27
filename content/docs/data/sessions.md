---
title: Sessions
weight: 1
---
<!-- Page Specific Styling -->
<style>
  a {
    text-decoration: none !important;
  }

  a mark {
    font-size: 1.25em;
    color: white;
  }
  
  .prose :where(blockquote p):not(:where([class~=not-prose],[class~=not-prose] *)) {
    font-style: normal;
    font-weight: normal;
  }

  .prose :where(blockquote p:first-of-type):not(:where([class~=not-prose],[class~=not-prose] *)):before {
    content: unset;
  }

  .prose :where(blockquote p:last-of-type):not(:where([class~=not-prose],[class~=not-prose] *)):after {
    content: unset;
  }
</style>

<!-- Page Content -->
Session data is stored under the `sessions` key in firebase. Each session will have a unique key
value associated to it (in the example, the session key is `-O4bhX9wmx0cFlNK6ZZQ`). The data
collected for each session has information about two major components of experiments:
- [Metadata](#metadata)
- [Players](#players)

## Example

Session data recorded to Firebase will look as follows:

```yaml
🞃 sessions: {
      # Unique session ID
    🞃 -O4bhX9wmx0cFlNK6ZZQ: {
        🞃 allPlayersEver: {
              🞃 _5iftyunyo: {
                    arrivalIndex: 1,
                    finishStatus: "na",
                    leftGameAt: 0,
                    numBlurred: 0,
                    sessionStartedAt: 1724021887840,
                    status: "focus",
                    timeElapsedToWaitingRoom: 1939,
                    waitingRoomStartedAt: 1724021875444
              },
              🞂 _7xsy2b05n: {}
          },
          numPlayersEverJoined: 2,
          playerControl: "_5iftyunyo",
        🞃 players: {
              🞂 _5iftyunyo: {},
              🞃 _7xsy2b05n: {
                    arrivalIndex: 2,
                    finishStatus: "na",
                    leftGameAt: 0,
                    numBlurred: 1,
                    sessionStartedAt: 1724021887840,
                    status: "blur",
                    timeElapsedToWaitingRoom: 8881,
                    waitingRoomStartedAt: 1724021887840
              },
          },
          sessionIndex: 1,
          sessionStartedAt: 1724021887840,
          status: "active",
          timeElapsedToWaitingRoom: 1939,
          waitingRoomStartedAt: 1724021875444
    }
}
```

<!-- Metadata information collected for each session -->
## Metadata

#### allPlayersEver
> Player information for all players that have joined the session


#### numPlayersEverJoined
> Total number of players that have joined the session

#### playerControl
> TODO

#### players
> Player information about all of the current (active) players in the session

#### sessionIndex
> Session index value (relevant for when there are multiple simultanious sessions)

#### sessionStartedAt
> Timestamp for when the session was started

#### status
> The current status of the session (active, ...)

#### timeElapsedToWaitingRoom
> Total amount of time there was a waiting room for the session

#### waitingRoomStartedAt
> Timestamp for when the waiting room was initiated


<!-- Information about player data -->
## Players

Player information can be found under the `allPlayersEver` key or the `players` key (for active
players). Each player is assigned a unique key value (in the example below, there are two players
with the values `_5iftyunyo` and `_7xsy2b05n`). All players have the following data collected:

#### arrivalIndex
> Player index value (saved according to the order each player was added to firebase)

#### finishStatus
> TODO

#### leftGameAt
> Timestamp associated with the time a player left the session

#### numBlurred
> TODO

#### sessionStartedAt
> Timestamp for when the session was started

#### status
> TODO

#### timeElapsedToWaitingRoom
> Total amount of time there was a waiting room for the session

#### waitingRoomStartedAt
> Timestamp for when the waiting room was initiated


<!-- Links to other sections -->
## Other Sections

{{< cards >}}
  {{< card
    url="../states/"
    title="States"
    icon="cube"
    subtitle="Experiment specific data"
    >}}

  {{< card
    url="../recorded-data/"
    title="Recorded Data"
    icon="server"
    subtitle="Saved data for analysis"
    >}}
{{< /cards >}}
