# Hands-on: Deploy on OpenChoreo

Materials for the Kubernetes Sri Lanka June Meetup 2026 hands-on session. You deploy a web
app through the OpenChoreo portal and promote it to production — no YAML, no CLI, no
container build.

## Start here

1. **Sign in** (below).
2. Do **[react-starter](./01-react-starter/)** — the main lab (~20 min): create an app, deploy
   it, promote development → staging → production.
3. If you finish early, do **[doclet](./02-doclet/)** — deploy a real multi-service app yourself:
   managed Postgres + NATS and three components wired together.

## Sign in

1. Open the portal URL shown on screen (locally: `http://openchoreo.localhost:8080`).
2. Click **Sign In** and log in with the credentials on screen.
3. Everything you create goes into **your namespace**, provisioned for you ahead of time.
   In these guides the namespace is `kube-sl-handson`; yours will have your name on it.

## Layout

- `01-react-starter/` — the main lab guide
- `02-doclet/` — the stretch guide: deploy a multi-service app with self-service infra
- `setup/` — namespace provisioning for organizers (see `setup/README.md`)
