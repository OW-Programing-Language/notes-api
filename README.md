# Notes API (Ow)

A tiny REST API + built-in database, written in **[Ow](https://github.com/OW-Programing-Language/ow-lang)** on the
**[Night](https://github.com/OW-Programing-Language/night)** web stack — no SQL, no ORM, no server config.

A `model` is a table; `route`/`serve` is the server. Data persists to `ow-data.json`.

## Endpoints

| Method | Path | Does |
|---|---|---|
| GET | `/notes` | list all notes (JSON) |
| GET | `/notes/:id` | one note (404 if missing) |
| POST | `/notes` | create — JSON body `{title, body}` |
| DELETE | `/notes/:id` | delete |

## Run it

Install Ow (see [ow-lang releases](https://github.com/OW-Programing-Language/ow-lang/releases)), then:

```sh
ow run src/main.ow
```

The server starts on http://localhost:8080 and opens your browser. Try:

```sh
curl -X POST localhost:8080/notes -d '{"title":"First","body":"hello"}'
curl localhost:8080/notes
```

## Native app

A self-contained `.exe`/installer (bundled runtime, no Java needed) is on the
[Releases](../../releases) page — it starts the server and opens the browser.

## License

[MIT](LICENSE).
