---
swagger: "2.0"
x-collection-name: api.video
x-complete: 0
info:
  title: API.Video Patch Players
  description: It may take up to 10min before the new player configuration is available
    from our CDN.
  version: 1.0.0
host: ws.api.video
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /players/{id}:
    parameters:
      summary: Parameters Players
      description: Parameters players.
      operationId: parametersPlayers
      x-api-path-slug: playersid-parameters
      responses:
        200:
          description: Successful response
      tags:
      - Parameters
      - Players
    patch:
      summary: Patch Players
      description: It may take up to 10min before the new player configuration is
        available from our CDN.
      operationId: patchPlayers
      x-api-path-slug: playersid-patch
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: Successful response
      tags:
      - Players
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