---
swagger: "2.0"
x-collection-name: Google Play
x-complete: 0
info:
  title: Google Play Get Player Categories
  version: 1.0.0
  description: List play data aggregated per category for the player corresponding
    to playerId.
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /players/me/players/{collection}:
    get:
      summary: Get PLayers
      description: Get the collection of players for the currently authenticated user.
      operationId: games.players.list
      x-api-path-slug: playersmeplayerscollection-get
      parameters:
      - in: path
        name: collection
        description: Collection of players being retrieved
      - in: query
        name: consistencyToken
        description: The last-seen mutation timestamp
      - in: query
        name: language
        description: The preferred language to use for strings returned by this method
      - in: query
        name: maxResults
        description: The maximum number of player resources to return in the response,
          used for paging
      - in: query
        name: pageToken
        description: The token returned by the previous request
      responses:
        200:
          description: OK
      tags:
      - Player
  /players/{playerId}:
    get:
      summary: Get Player
      description: Retrieves the Player resource with the given ID. To retrieve the
        player for the currently authenticated user, set playerId to me.
      operationId: games.players.get
      x-api-path-slug: playersplayerid-get
      parameters:
      - in: query
        name: consistencyToken
        description: The last-seen mutation timestamp
      - in: query
        name: language
        description: The preferred language to use for strings returned by this method
      - in: path
        name: playerId
        description: A player ID
      responses:
        200:
          description: OK
      tags:
      - Player
  /players/{playerId}/achievements:
    get:
      summary: Get Player Achievements
      description: Lists the progress for all your application's achievements for
        the currently authenticated player.
      operationId: games.achievements.list
      x-api-path-slug: playersplayeridachievements-get
      parameters:
      - in: query
        name: consistencyToken
        description: The last-seen mutation timestamp
      - in: query
        name: language
        description: The preferred language to use for strings returned by this method
      - in: query
        name: maxResults
        description: The maximum number of achievement resources to return in the
          response, used for paging
      - in: query
        name: pageToken
        description: The token returned by the previous request
      - in: path
        name: playerId
        description: A player ID
      - in: query
        name: state
        description: Tells the server to return only achievements with the specified
          state
      responses:
        200:
          description: OK
      tags:
      - Player
  /players/{playerId}/categories/{collection}:
    get:
      summary: Get Player Categories
      description: List play data aggregated per category for the player corresponding
        to playerId.
      operationId: games.metagame.listCategoriesByPlayer
      x-api-path-slug: playersplayeridcategoriescollection-get
      parameters:
      - in: path
        name: collection
        description: The collection of categories for which data will be returned
      - in: query
        name: consistencyToken
        description: The last-seen mutation timestamp
      - in: query
        name: language
        description: The preferred language to use for strings returned by this method
      - in: query
        name: maxResults
        description: The maximum number of category resources to return in the response,
          used for paging
      - in: query
        name: pageToken
        description: The token returned by the previous request
      - in: path
        name: playerId
        description: A player ID
      responses:
        200:
          description: OK
      tags:
      - Player
  /players/{playerId}/leaderboards/{leaderboardId}/scores/{timeSpan}:
    get:
      summary: Get Player Leaderboard Scores
      description: |-
        Get high scores, and optionally ranks, in leaderboards for the currently authenticated player. For a specific time span, leaderboardId can be set to ALL to retrieve data for all leaderboards in a given time span.
        NOTE: You cannot ask for 'ALL' leaderboards and 'ALL' timeSpans in the same request; only one parameter may be set to 'ALL'.
      operationId: games.scores.get
      x-api-path-slug: playersplayeridleaderboardsleaderboardidscorestimespan-get
      parameters:
      - in: query
        name: consistencyToken
        description: The last-seen mutation timestamp
      - in: query
        name: includeRankType
        description: The types of ranks to return
      - in: query
        name: language
        description: The preferred language to use for strings returned by this method
      - in: path
        name: leaderboardId
        description: The ID of the leaderboard
      - in: query
        name: maxResults
        description: The maximum number of leaderboard scores to return in the response
      - in: query
        name: pageToken
        description: The token returned by the previous request
      - in: path
        name: playerId
        description: A player ID
      - in: path
        name: timeSpan
        description: The time span for the scores and ranks youre requesting
      responses:
        200:
          description: OK
      tags:
      - Player
  /players/{playerId}/snapshots:
    get:
      summary: Get Player Snapshots
      description: Retrieves a list of snapshots created by your application for the
        player corresponding to the player ID.
      operationId: games.snapshots.list
      x-api-path-slug: playersplayeridsnapshots-get
      parameters:
      - in: query
        name: consistencyToken
        description: The last-seen mutation timestamp
      - in: query
        name: language
        description: The preferred language to use for strings returned by this method
      - in: query
        name: maxResults
        description: The maximum number of snapshot resources to return in the response,
          used for paging
      - in: query
        name: pageToken
        description: The token returned by the previous request
      - in: path
        name: playerId
        description: A player ID
      responses:
        200:
          description: OK
      tags:
      - Player
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---