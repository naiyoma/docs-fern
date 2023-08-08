Every Fern API has a special file called `api.yml`, which includes all the API-wide configuration.

```yaml
fern/
├─ fern.config.json
└─ api/
  ├─ generators.yml
  └─ definition/
    ├─ api.yml # <---
    └─ imdb.yml
```

## API name

This name is used to uniquely identify your API in your organization. If you
just have one API, then `api` is a sufficient name.

```yaml api.yml
name: api
```

## API docs

You can define top level API docs. These docs will come through in the
OpenAPI spec and Postman collection.

```yaml api.yml
name: api
docs: |
  ## Header
  This API provides access to...
```

## Authentication

You can specify the authentication scheme used by your API.

Out of the box, Fern supports `Bearer` and `Basic` authentication schemes.

```yaml api.yml
name: api
auth: bearer
```

```yaml api.yml
name: api
auth: basic
```

You can also create your own authentication schemes.

```yaml api.yml
name: api
auth: MyAuthScheme
auth-schemes:
  MyAuthScheme:
    header: X-API-Key
    type: string
```

## API-wide headers

You can specify headers that are meant to be included on every request:

```yaml api.yml
name: api
headers:
  X-App-Id: string
```

## Environments

You can specify the environments where your backend is deployed. These are useful
in most generated outputs, like SDKs and in Postman Collections.

```yaml api.yml
name: api
environments:
  Production: https://www.yoursite.com
  Staging:
    docs: This staging environment is helpful for testing!
    url: https://www.staging.yoursite.com
```

You can also provide a default environment:

```yaml api.yml
name: api
environments:
  Production: https://www.yoursite.com
    Staging:
      docs: This staging environment is helpful for testing!
      url: https://www.staging.yoursite.com
default-environment: Production
```

### Multiple URLs per environment

You can specify multiple URLs per environment. This is helpful if you have a
microservice architecture, and you want a single SDK to interact with multiple
servers.

```yaml api.yml
environments:
  Production:
    urls:
      Auth: https://auth.yoursite.com
      Plants: https://plants.yoursite.com
  Staging:
    urls:
      Auth: https://auth.staging.yoursite.com
      Plants: https://plants.staging.yoursite.com
```

If you choose to use this feature, you must specify a `url` for each service you define:

```yaml auth.yml
service:
  url: Auth
  base-path: /auth
  ...
```

## Error discrimination strategy

In order to generate SDKs idiomatically, Fern needs to know how to differentiate
between different errors when parsing an endpoint response.

### Discriminate by status code

You can specify Fern to discriminate by status code. This means on each
endpoint, every error that's listed must have a different HTTP status code.

```yaml api.yml
name: api
error-discrimination:
  strategy: status-code
```

### Discriminate by error name

You can specify Fern to discriminate by error name. If you select this strategy,
then Fern will assume that every error response has an extra property denoting
the error name.

If you use Fern to generate server-side code, then this option provides
the most flexibility. Otherwise, you'll probably want to use the status code
discrimination strategy.

```yaml api.yml
name: api
error-discrimination:
  strategy: property
  property-name: errorName
```

## API-wide errors

You can import and list errors that will be thrown by every endpoint.

```yaml api.yml
imports:
  commons: commons.yml

errors:
  - commons.NotFoundError
  - commons.BadRequestError
```
