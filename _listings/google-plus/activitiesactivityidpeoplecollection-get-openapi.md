---
swagger: "2.0"
x-collection-name: Google Plus
x-complete: 0
info:
  title: Google Plus Get People In Collection
  version: 1.0.0
  description: List all of the people in the specified collection for a particular
    activity.
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /activities/{activityId}/people/{collection}:
    get:
      summary: Get People In Collection
      description: List all of the people in the specified collection for a particular
        activity.
      operationId: plusDomains.people.listByActivity
      x-api-path-slug: activitiesactivityidpeoplecollection-get
      parameters:
      - in: path
        name: activityId
        description: The ID of the activity to get the list of people for
      - in: path
        name: collection
        description: The collection of people to list
      - in: query
        name: maxResults
        description: The maximum number of people to include in the response, which
          is used for paging
      - in: query
        name: pageToken
        description: The continuation token, which is used to page through large result
          sets
      responses:
        200:
          description: OK
      tags:
      - Person
  /people:
    get:
      summary: Get People
      description: Search all public profiles.
      operationId: plus.people.search
      x-api-path-slug: people-get
      parameters:
      - in: query
        name: language
        description: Specify the preferred language to search with
      - in: query
        name: maxResults
        description: The maximum number of people to include in the response, which
          is used for paging
      - in: query
        name: pageToken
        description: The continuation token, which is used to page through large result
          sets
      - in: query
        name: query
        description: Specify a query string for full text search of public text in
          all profiles
      responses:
        200:
          description: OK
      tags:
      - Person
  /people/{userId}:
    get:
      summary: Get Person
      description: Get a person's profile. If your app uses scope https://www.googleapis.com/auth/plus.login,
        this method is guaranteed to return ageRange and language.
      operationId: plus.people.get
      x-api-path-slug: peopleuserid-get
      parameters:
      - in: path
        name: userId
        description: The ID of the person to get the profile for
      responses:
        200:
          description: OK
      tags:
      - Person
  /people/{userId}/people/{collection}:
    get:
      summary: Get Collection of People
      description: List all of the people in the specified collection.
      operationId: plus.people.list
      x-api-path-slug: peopleuseridpeoplecollection-get
      parameters:
      - in: path
        name: collection
        description: The collection of people to list
      - in: query
        name: maxResults
        description: The maximum number of people to include in the response, which
          is used for paging
      - in: query
        name: orderBy
        description: The order to return people in
      - in: query
        name: pageToken
        description: The continuation token, which is used to page through large result
          sets
      - in: path
        name: userId
        description: Get the collection of people for the person identified
      responses:
        200:
          description: OK
      tags:
      - Person
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