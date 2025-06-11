# google

## Pre-reqs

1. Create gcp project via the web console.
2. Go to `API & Services > Credentials`
3. Setup `OAuth consent screen`
4. `Create credentials > OAuth Client ID`
5. Application type: `Web Application`
6. Name: `Forgejo`
7. Authorized redirect URIs: `http://localhost:3000/user/oauth2/google/callback`
8. Click `Create`. Don't forget to download the credentials.
