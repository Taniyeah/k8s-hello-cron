# ⏰ k8s-hello-cron

A tiny Kubernetes **CronJob** that prints **Hello DevOps** every minute. Great for a beginner-friendly DevOps portfolio repo.

---

## ✅ What you'll do (super simple)
1. Start a local Kubernetes cluster (Minikube/Kind).
2. Apply the CronJob manifest.
3. Confirm it creates Jobs every minute.
4. View the logs that say _Hello DevOps_.
5. Take 3 screenshots and drop them in `./screenshots/` so they render in this README.

---

## 🧰 Prereqs
- `kubectl` installed and pointing to a cluster (Minikube or Kind is perfect)
- Docker Desktop (or Docker Engine) if you’re using Minikube with the Docker driver

> Tip: If you already use Docker Desktop on macOS/Windows, **Kind** is often the quickest option.

---

## 🚀 Run it

Apply the CronJob:

```bash
kubectl apply -f cronjob.yaml
```

Check that it exists:

```bash
kubectl get cronjobs
```

Wait ~1 minute so a Job is created, then list Jobs:

```bash
kubectl get jobs
```

List Pods created by the most recent Job and show logs (pick the newest pod name shown by `get pods`):

```bash
kubectl get pods --sort-by=.metadata.creationTimestamp
# copy the newest pod's name, then:
kubectl logs <your-pod-name>
```

Expected log output:

```
Hello DevOps from Kubernetes CronJob!
```

---

## 📸 Add screenshots to this README

Take these 3 screenshots and save them into `./screenshots/` with the exact names below:

1. `kubectl-get-cronjob.png` — result of `kubectl get cronjobs`
2. `kubectl-get-job.png` — result of `kubectl get jobs`
3. `kubectl-logs.png` — the terminal showing `kubectl logs <pod>` printing _Hello DevOps_

Then they’ll render right here:

### CronJob Created
![kubectl-get-cronjob](./screenshots/kubectl-get-cronjob.png)

### Jobs Generated
![kubectl-get-job](./screenshots/kubectl-get-job.png)

### Logs Output
![kubectl-logs](./screenshots/kubectl-logs.png)

> Screenshot quick keys: **macOS** `Shift+Cmd+4`, **Windows** `Win+Shift+S`, **Ubuntu** `Shift+PrtSc`.

---

## 🧽 Clean up

```bash
kubectl delete -f cronjob.yaml
```

---

## 🧪 Optional tweaks
- Change the schedule (e.g. `"0 * * * *"` for every hour)
- Change the message text
- Add a `namespace` section and deploy to a non-default namespace

---

## 📦 Repo layout

```
k8s-hello-cron/
├─ cronjob.yaml
├─ README.md
└─ screenshots/
   └─ (put your PNGs here)
```

Happy shipping! 🔧🚀
