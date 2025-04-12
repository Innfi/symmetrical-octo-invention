#DNS #Mail 

Mail eXchange Record

Example of an MX record:

|example.com|record type:|priority:|value:|TTL|
|---|---|---|---|---|
|@|MX|10|mailhost1.example.com|45000|
|@|MX|20|mailhost2.example.com|45000|

The 'priority' numbers before the [domains](https://www.cloudflare.com/learning/dns/glossary/what-is-a-domain-name/) for these MX records indicate preference; the lower 'priority' value is preferred. The server will always try mailhost1 first because 10 is lower than 20. In the result of a message send failure, the server will default to mailhost2.