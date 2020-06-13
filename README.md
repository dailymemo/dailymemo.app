<div align="center">
  <h1>Giki</h1>
  <strong>A simple, secure and powful journal app</strong>
  <img src="https://giki.app/images/feature_pic_light.png" width="80%" alt="Screenshot">
</div>

## Home

→ [**giki.app**](https://giki.app)

## Download

* → [Mac, PC, Linux Desktop Apps](https://github.com/gikiapp/giki.app/releases)
* → [Chrome Extension](https://chrome.google.com/webstore/detail/hcjaennlplpppgfolnagejnpcmbhdjba)
* → [Firefox Add-on](https://addons.mozilla.org/en-US/firefox/addon/giki)

## API

**叽喳・Giki** provides varierty of APIs for developers to build extensions, all kinds of extensions (Vim plugin, Emacs pluggin, CLI, etc) are welcome.

**Notes**: We use `giki` to represent an item of your writing. You can get your **token** from your profile setting page, **token** is optional for all the `GET` endpoints, but required for `POST` endpoints.


### Users

**user fetch**

```
https://giki.app/api/users/query
```

- fetch by name

```shell
curl 'https://giki.app/api/users/query?name=<your name>' \
  -H 'authorization: Basic <your token>'
```

- fetch by domain

```shell
curl 'https://giki.app/api/users/query?domain=<your domain>' \
  -H 'authorization: Basic <your token>'
```

**user update**

```shell
curl -X POST 'https://giki.app/api/users/update' \
  -H 'authority: giki.app' \
  -H 'authorization: Basic eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFiMmRmZWMwLWE4NWUtNDRiZS04ZmYwLTZiNDkxNWFmMDEyNyIsIm5hbWUiOiJpIiwicHJvdmlkZXIiOiJ3ZWlibyIsInByb3ZpZGVyVXNlcklkIjoyMTY1NzE0NTA3LCJpYXQiOjE1OTE5NjE1MTYsImV4cCI6MTU5NDU1MzUxNn0.i0U501e382hsbGmFgk0fuxrofCtEU6PuTY7q4jLqswY' \
  -H 'content-type: application/json' \
  --data-binary '{"avatar":<your name>, "name": <your name>, "introduction": <your introduction>}' \
```

### Gikis

**giki create**

```
https://giki.app/api/talks/create
```

```shell

curl -X POST 'https://giki.app/api/talks/create' \
  -H 'authority: giki.app' \
  -H 'authorization: Basic <your token>' \
  -H 'content-type: application/json' \
  --data-binary '{"text":"hello world ","actions":["weibo"],"tags":["private"],"image":[]}'
```

**giki list**

```
https://giki.app/api/talks/query
```

- list by domain

```shell
curl 'https://giki.app/api/talks/query?domain=iiiii.li' \
  -H 'authority: giki.app' \
  -H 'authorization: Basic <your token>'
```

- list by name

```shell
curl 'https://giki.app/api/talks/query?name=i' \
  -H 'authority: giki.app' \
  -H 'authorization: Basic <your token>'
```

**giki query**

```
https://giki.app/api/talks/query
```

```
  curl 'https://giki.app/api/talks/query?id=<giki id>' \
  -H 'authorization: Basic <your token>'
```

**giki tags list**

```
https://giki.app/api/talks/query
```

you can list tags by a domain or a name of a user, with `list_tag=true` in query
string

- list by domain

```
curl 'https://giki.app/api/talks/query?domain=iiiii.li&list_tag=true' \
  -H 'authorization: Basic <your token>'
```

- list by name

```
curl 'https://giki.app/api/talks/query?name=i&list_tag=true' \
  -H 'authorization: Basic <your token>'
```
