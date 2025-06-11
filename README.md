# OAuth Demo

Use google / authentik as oauth provider for logging into Forgejo (a git platform).

!!Important: make sure you use the same email for your google account and forgejo's account, because forgejo allows identity linking between native and oauth provider.

## Usage

### Forgejo

1. Spin up forgejo: `cd forgejo && docker compose up -d`
2. Access forgejo via <http://localhost:3000>
   - Under `Administrator account settings`, create admin user. Make sure you use the same email as your google account
   - Click `Install Forgejo` at the bottom of the screen

### Google OAuth

1. Follow how to create google oauth client ![here](./oauth-providers/google/README.md)
2. In forgejo, at the top-right there would be a drop-down, click `Site administration`
3. `Identity & access > Authentication sources` and click `Add authentication source`
4. Authentication type: `OAuth2`
5. Authentication name: `google`
6. OAuth2 provider: `Google`
7. Paste `Client ID` and `Client Secret` from the obtained google oauth credentials
8. Under `Additional scopes` paste following text: `email profile`
9. Click `Add authentication source`
10. Go to `http://localhost:3000/user/login` and try logging in with google
11. Since you use the same forgejo email as your google account, supply your forgejo native credentials to link the accounts
