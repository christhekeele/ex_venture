Commands
========

> ***Commands used in the development and deployment of our app***

<details>
    <summary>git clone -b start --depth=1 git@github.com:christhekeele/ex_venture.git</summary>

```
Cloning into 'ex_venture'...
remote: Enumerating objects: 425, done.
remote: Counting objects: 100% (425/425), done.
remote: Compressing objects: 100% (389/389), done.
remote: Total 425 (delta 36), reused 288 (delta 19), pack-reused 0
Receiving objects: 100% (425/425), 753.38 KiB | 1.64 MiB/s, done.
Resolving deltas: 100% (36/36), done.
```

</details>

<details>
    <summary>cd ex_venture</summary>
</details>

<details>
    <summary>flyctl init</summary>

```
? App Name (leave blank to use an auto-generated name) ex-venture

Automatically selected personal organization

? Select builder: Dockerfile
    (Do not set a builder and use the existing Dockerfile)
? Select Internal Port: 4000
New app created
Name         = ex-venture
Organization = personal
Version      = 0
Status       =
Hostname     = <empty>

App will initially deploy to sea (Seattle, Washington (US)) region

Wrote config file fly.toml
```

</details>

<details>
    <summary>flyctl deploy</summary>

    Without environment vars configured:
  
  ```
   Application ex_venture exited: ExVenture.Application.start(:normal, []) returned an error: shutdown: failed to start child: ExVenture.Repo
   ENV vars not set: DATABASE_URL, POOL_SIZE
    ** (Vapor.LoadError) There were errors loading configuration:
        (vapor 0.10.0) lib/vapor.ex:42: Vapor.load!/1

  ***v0 failed - Failed due to unhealthy allocations - no stable job version to auto revert to
  ```

</details>

<details>
    <summary>flyctl postgres create</summary>

```
  ? App name: ex-venture-db
  Automatically selected personal organization
  ? Select region: sea (Seattle, Washington (US))
  ? Select VM size: shared-cpu-1x - 256
  ? Volume size (GB): 10
  Creating postgres cluster ex-venture-db in organization personal
  Postgres cluster ex-venture-db created
    Username:    postgres
    Password:    ********
    Hostname:    ex-venture-db.internal
    Proxy Port:  5432
    PG Port: 5433
  Save your credentials in a secure place, you won't be able to see them again!

  Monitoring Deployment
  You can detach the terminal anytime without stopping the deployment

  2 desired, 2 placed, 2 healthy, 0 unhealthy [health checks: 6 total, 6 passing]
  --> v0 deployed successfully

  Connect to postgres
  Any app within the personal organization can connect to postgres using the above credentials and the hostname "ex-venture-db.internal."
  For example: postgres://postgres:********@ex-venture-db.internal:5432
  ```

</details>
