# authentik

## Setup

Ref: <https://version-2024-12.goauthentik.io/docs/install-config/install/docker-compose>

```bash
echo "PG_PASS=$(openssl rand -base64 36 | tr -d '\n')" >> .env
echo "AUTHENTIK_SECRET_KEY=$(openssl rand -base64 60 | tr -d '\n')" >> .env

docker compose up -d
```

## Initial setup

Setup admin user via: <http://localhost:9000/if/flow/initial-setup/>. Don't forget to use the same email as your google account.

## Create oauth client

1. Click `Create new application`
2. Name: `Forgejo`
3. Click `Next`
4. Click `OAuth2/OpenID Provider`
5. For `Authorization flow`, set `default-provider-authorization-implicit-consent`
6. Set `Redirect URIs/Origins` (strict) to `http://localhost:3000/user/oauth2/authentik/callback`
7. Copy `Client ID` and `Client Secret`
8. Under `Advanced flow settings`, set `Authentication flow` to `default-authentication-flow`
9. Click `Next`
10. Click `Submit`
