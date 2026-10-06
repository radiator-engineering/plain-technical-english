Draft an email from an engineering team to external API customers announcing a breaking change:

Facts: On September 30, the `/v1/detections` endpoint will stop accepting API-key query parameters (`?api_key=`). Callers must switch to the `Authorization: Bearer` header. Keys themselves are unchanged. Requests using the query parameter will return 401 after that date. A migration guide is at https://docs.example.com/auth-migration. Support contact: api-support@example.com. The reason: query-parameter keys leak into server logs and referrer headers.

Constraints: professional and courteous, honest about the reason, under 200 words of body text. Return only the email (subject + body), no commentary.
