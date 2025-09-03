# CLI Approach with ArgoCD (Apache Example)

In this approach, we will deploy an application using the **ArgoCD CLI**.  
We’ll use a simple **Apache HTTPD Deployment + Service** to understand how ArgoCD can be controlled from the terminal.

---

## Theory

- In the **CLI approach**, we use the `argocd app create` command to define applications.  
- This command creates an `Application` resource (CRD) inside the cluster on our behalf.  
- The app definition lives **only in the cluster**, not in Git.  
- It’s fast and powerful for admins, but still **not true GitOps**, because changes are not version-controlled.  

> ✅ Best practice: Use the **Declarative approach (CRDs in Git)** for production.  
> ❌ The CLI method is best for operators or quick testing.  

---

## Prerequisites

Before you begin, ensure you have:  
1. A **Kind cluster** running  
2. **ArgoCD installed & running** (via Helm or manifests)  
3. **ArgoCD CLI installed and logged in**  
4. `kubectl` installed to interact with your cluster  

> Follow this guide to get above things ready: [ArgoCD Setup & Installation](../../../03_setup_installation/README.md)

---

## Steps to Deploy Apache using ArgoCD CLI

### 1. Fork and Clone the Repo

```bash
git clone https://github.com/Amitabh-DevOps/argocd-demos.git
cd argocd-demos/cli_approach/apache
````

---

### 📂 Directory Structure

```
cli_approach/apache
├── apache_deployment.yml
└── apache_svc.yml
```

---

### 2. Connect Your Git Repository (Optional)

If your repo is private, connect it to ArgoCD:

```bash
argocd repo add https://github.com/<your-username>/argocd-demos.git --username <user> --password <token>
```

For a public repo, this step is optional.

---

### 3. Create Application via CLI

Run this command to create an ArgoCD application:

```bash
argocd app create apache-app \
  --repo https://github.com/<your-username>/argocd-demos.git \
  --path cli_approach/apache \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace default \
  --sync-policy automated \
  --self-heal \
  --auto-prune
```

Explanation of flags:

* `--repo` → Git repository URL.
* `--path` → Path inside repo containing manifests.
* `--dest-server` → Target cluster (here, the in-cluster API).
* `--dest-namespace` → Namespace to deploy (`default`).
* `--sync-policy automated` → Enable auto-sync.
* `--self-heal` → Auto-heal drift if someone changes/deletes resources.
* `--auto-prune` → Remove resources if deleted from Git.

---

### 4. Verify Application

Check app details:

```bash
argocd app get apache-app
```

Expected output: Shows repo, path, destination, sync status, and health.

![argocd-app-get](../output_images/image-11.png)

---

### 5. Sync the Application

If the app shows **OutOfSync**, run:

```bash
argocd app sync apache-app
```

![argocd-sync](../output_images/image-12.png)

---

### 6. Verify Deployment in Kubernetes

From CLI:

```bash
kubectl get pods -n default
kubectl get svc -n default
```

You should see:

* Apache pods running (`apache-deployment-xxxx`).
* `apache-service` of type ClusterIP exposing port 80.

---

### 7. Access Apache via Browser

1. Port-forward the Apache service:

```bash
kubectl port-forward svc/apache-service 8082:80 --address=0.0.0.0 &
```

2. Open inbound rule for port `8082` on your EC2 instance.

3. Access the Apache app at:

```bash
http://<EC2-Public-IP>:8082
```

You should see the default **Apache HTTPD test page**.

---

## Testing

### Make a Change in Git

1. Open `apache_deployment.yml`.
2. Change the replicas, e.g., `2 → 4`:

```yaml
spec:
  replicas: 4
```

3. Commit & push:

```bash
git add apache_deployment.yml
git commit -m "Scale Apache replicas to 4"
git push origin main
```

### Observe in ArgoCD

```bash
argocd app get apache-app
```

* You’ll see the app go **OutOfSync**, then ArgoCD will sync automatically (because of `--sync-policy automated`).
* Verify in Kubernetes:

```bash
kubectl get pods -n default
```

Now 4 Apache pods should be running.

---

## Wrap-Up

* You successfully deployed an app via **ArgoCD CLI**.
* Key takeaway:

  * CLI is powerful for admins/operators.
  * It’s still **imperative** → app definition exists only in cluster.
  * Real GitOps requires **declarative Application CRDs in Git** (covered in the next approach).

Happy Learning!

```


