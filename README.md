# Boilerplate for nginx with Let’s Encrypt on docker-compose

> This repository is accompanied by a [step-by-step guide on how to
set up nginx and Let’s Encrypt with Docker](https://medium.com/@pentacent/nginx-and-lets-encrypt-with-docker-in-less-than-5-minutes-b4b8a60d3a71).

`init-letsencrypt.sh` fetches and ensures the renewal of a Let’s
Encrypt certificate for one or multiple domains in a docker-compose
setup with nginx.
This is useful when you need to set up nginx as a reverse proxy for an
application.

## Installation

1. [Install docker-compose](https://docs.docker.com/compose/install/#install-compose).

2. Clone this repository: `git clone git@github.com:iZemil/ssl.git .`

- Or add as a submodule: `git submodule add git@github.com:iZemil/ssl.git`

3. Modify configuration:

- Add domains and email addresses to init-letsencrypt.sh
- Replace all occurrences of `9las.com` with primary domain (the first one you added to init-letsencrypt.sh) in data/nginx/app.conf

4. Run the init script:

```bash
./init-letsencrypt.sh
```

5. Run the server:

```bash
docker compose up
```

6. Check ssl certificate: https://www.ssllabs.com/ssltest/analyze.html
