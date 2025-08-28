#  k8s-hello-cron

A tiny Kubernetes cron job that prints Hello every minute. G
---

1. Start a local Kubernetes cluster (Minikube/Kind).
2. Apply the CronJob manifest.
3. Confirm it creates Jobs every minute.
4. View the logs that say Hello.

---

## Prereqs
- `kubectl` installed and pointing to a cluster (Minikube is perfect)
- Docker Desktop (or Docker Engine) if you’re using Minikube with the Docker driver


---


