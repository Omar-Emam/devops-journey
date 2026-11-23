# Past Labs — Upload & Improve

Labs done before this repo: Docker, Ansible, Kubernetes. During the Git stage they get uploaded here and the items below get fixed. Each fix is a commit.

## Habits to fix everywhere
- [ ] **Prove the behaviour, not just creation.** Run twice and show `changed=0`; watch a rollout happen; test the service port, not `ping`.
- [ ] **No plain-text secrets.** Use SSH keys, `ansible-vault`, Kubernetes Secrets kept out of git, `.env` files ignored by git.
- [ ] **Production defaults.** Pinned image tags, non-root containers, gunicorn instead of the Flask dev server, health probes.

## Docker
- [ ] Rewrite the "production-ready" Flask Dockerfile: pinned `python:3.12-slim`, `WORKDIR`, `requirements.txt` + `--no-cache-dir`, `.dockerignore`, non-root user, `gunicorn`. Show the image size before vs after.
- [ ] Fix the "Iâ€™m" encoding bug (`<meta charset="utf-8">` or `charset utf-8;` in Nginx).
- [ ] Networking: reach containers by name (`curl nginx-container`), not by IP.
- [ ] Apache → MySQL: prove it with the real port (`nc -zv db 3306` or a mysql client), not ping.
- [ ] Compose Task 02: add the missing web app next to MySQL.
- [ ] Remove the obsolete `version:` key from Compose files.

## Ansible
- [ ] Idempotency: show a second run with `changed=0`.
- [ ] `changed_when: false` on read-only `command` tasks.
- [ ] Handlers: watch a real Nginx config (`/etc/nginx/conf.d/…`); show one run where the handler fires and one where it doesn't.
- [ ] Role: use `defaults/`, `templates/` and `handlers/`, not just `tasks/`.
- [ ] Flask: replace `nohup` with a systemd unit (deployed with `template`, managed with `service`), installed in a virtualenv.
- [ ] Move `ansible_password` out of the inventory → SSH keys; DB passwords → `ansible-vault`.
- [ ] MySQL: add the secure-installation steps (remove anonymous users and the test DB).

## Kubernetes
- [ ] Rollouts: 3+ replicas, change the image, record `kubectl get pods -w` for Recreate vs RollingUpdate, then `kubectl rollout undo`.
- [ ] MySQL: get it actually Running (Secret for the root password); use a StatefulSet + PVC instead of a scaled Deployment.
- [ ] Fix the ConfigMap name mismatch (`cfg` vs `my-cfg`).
- [ ] Go app: add `readinessProbe`/`livenessProbe` on `/health`; multi-stage Dockerfile (show the size drop).
- [ ] Add resource requests/limits to the deployments.
