You have several options for setting the configuration values in the SDK:

### Option 1: Configuration file

Create a YAML file named `okta.yaml` in one of the following three available directories:

* Current user's home directory.
  * **Unix/Linux**:    `~/.okta/okta.yaml`
  * **Windows**:       `%userprofile%\.okta\okta.yaml`

* Application or project root directory

Add your configuration values to the file, using the following format:

```yaml
okta:
idx:
  issuer: "https://{yourOktaDomain}/oauth2/default"
  clientId: "{clientId}"
  clientSecret: "{clientSecret}"
  scopes:
  - "{scope1}"
  - "{scope2}"
  redirectUri: "{redirectUri}"
```

### Option 2: Environment variables

Add the values as environment variables with the following naming conventions:

* `OKTA_IDX_ISSUER`
* `OKTA_IDX_CLIENTID`
* `OKTA_IDX_CLIENTSECRET`
* `OKTA_IDX_REDIRECTURI`
* `OKTA_IDX_SCOPES`

### Option 3: Add parameter to the SDK's client constructor

Add the values as parameters to the constructor for the `IdxClient`:

```go
idx, err := idx.NewClient(
        idx.WithClientID(c.Okta.IDX.ClientID),
        idx.WithClientSecret(c.Okta.IDX.ClientSecret),
        idx.WithIssuer(c.Okta.IDX.Issuer),
        idx.WithScopes(c.Okta.IDX.Scopes),
        idx.WithRedirectURI(c.Okta.IDX.RedirectURI))
```
