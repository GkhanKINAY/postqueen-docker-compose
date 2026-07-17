
## Watch the Tutorial for docker-compose install:
[https://m.youtube.com/watch?v=A6CjAmJOWvA&t=5s](https://m.youtube.com/watch?v=A6CjAmJOWvA&t=5s)

## Warning
If you are upgrading from PostQueen old version, please make sure you update your docker compose, you can read more here:
https://docs.postqueen.ai/installation/migration

### Configuration uses environment variables

The docker containers for PostQueen are entirely configured with environment variables.

- **Option A** - environment variables in your `docker-compose.yml` file
- **Option B** - environment variables in a `postqueen.env` file mounted in `/config` for the PostQueen container only
- **Option C** - environment variables in a `.env` file next to your `docker-compose.yml` file (not recommended).

... or a mixture of the above options!

There is a [configuration reference](https://docs.postqueen.ai/configuration/reference) page with a list
of configuration settings.

Setup:
```
git clone https://github.com/GkhanKINAY/postqueen-docker-compose
```

Then run:
```
docker compose up
```

Wait for it to load:

Open your website on https://localhost:4007
