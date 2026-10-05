# service-multiplayer-fabric-generate-secrets

A shell script that fills the hosting stack's `.env` with random secrets before its first start and leaves keys already set untouched.

## What it is for

It writes each secret the stack's services read, such as passwords, signing keys and object-storage credentials, only when the key is absent, so a re-run never rotates a live secret. It also makes the short-lived self-signed certificate the zone server's transport needs when none exists.

## Run

```sh
./generate-secrets.sh
```

It writes `.env` and `certs/` next to the script, so the script lives in the hosting stack's directory.

## Licence

MIT; see `LICENSE`.
