---
swagger: "2.0"
x-collection-name: api.video
x-complete: 1
info:
  title: api.video
  description: the-simplest-way-to-put-video-on-the-web
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
    get:
      summary: Get Players
      description: Get players.
      operationId: getPlayers
      x-api-path-slug: playersid-get
      responses:
        200:
          description: Successful response
      tags:
      - Players
  /players:
    get:
      summary: Get Players
      description: Get players.
      operationId: getPlayers
      x-api-path-slug: players-get
      responses:
        200:
          description: Successful response
      tags:
      - Players
    post:
      summary: Post Players
      description: Post players.
      operationId: postPlayers
      x-api-path-slug: players-post
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
---