# Summarizer Model

This is an API service for `ModelSummarizer` of `coeus`

## API Documentation
### `GET /heathcheck`
Request: `None`

Response: `'OK'` with HTTP Status `200`

### `POST /predict`
Request:
`"data"` is a string represents text to summarize.
```json
{
  "data": "Lorem ipsum dolor sit amet, consectetur adipiscing elit."
}
```
Response:
`"result"` is a string of summary.
```json
{
  "result": "Lorem ipsum"
}
```

## Run
1. Copy file `.env.example` into `.env` and fill in all necessary values
2. Make sure you have Docker installed on your system and running
3. Build Docker image with a name of your choice if you haven't
```shell
docker build --tag summarizer-api .
```
5. Spin up a server
```shell
docker run -d -p 5000:5000 --name summarizer-api summarizer-api
```
6. Try accessing [http://127.0.0.1:5000](http://127.0.0.1:5000) with a valid route