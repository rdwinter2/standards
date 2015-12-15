Top level resources should always accept filters for 'guid' and 'guids'

Consistent pagination:

  - limit
  - starting_after
  - ending_before

  copy model from stripe: https://stripe.com/docs/api#pagination


Order by is also an interesting use case:

  From http://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api

    GET /tickets?sort=-priority - Retrieves a list of tickets in descending order of priority

    GET /tickets?sort=-priority,lower:name,created_at - Retrieves a list of tickets in descending order of priority. Within a specific priority, older tickets are ordered first

    http://localhost:8000/?sort=-priority,-lower(name),created_at  

  "order by priority desc, lower(name), created_at"

