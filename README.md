# Oathkeeper

Steps to reproduce a bug with x-forwarded headers

1. Run the docker-compose.yml
2. Perform this command:
```
curl -v -H "X-Forwarded-Host: dev.pp" -H "X-Forwarded-Proto: http" -H "x-forwarded-port: 4455"  http://localhost:4455/header
```

Actual result:
404 Not Found

Expected result:
200 OK

{
  "args": {},
  "data": "",
  "files": {},
  "form": {},
  "headers": {
    "Accept": "*/*",
    "Accept-Encoding": "gzip",
    "Host": "dev.pp",
    "User-Agent": "curl/7.68.0",
    "X-Amzn-Trace-Id": "Root=1-654d02aa-1ed22ecf2a4623d66ae70ac3"
  },
  "json": null,
  "method": "GET",
  "origin": "91.215.139.68",
  "url": "https://dev.pp/anything/header"
}

