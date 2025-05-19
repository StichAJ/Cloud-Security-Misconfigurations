# Cloud-Security-Misconfigurations
 Cloud Security Misconfigurations: What I See Too Often (and How to Avoid Them)
## ☁️ Common Cloud Security Misconfigurations and Fixes

As part of my role as a Cloud Engineer, I've observed several recurring misconfigurations that pose security risks in cloud environments. This list highlights common pitfalls and offers tips for hardening your cloud infrastructure.

### 🔸 1. Over-Permissive IAM Policies
**Problem:** Assigning wildcard permissions (`*:*`) or attaching admin roles too broadly.  
**Fix:** Follow the *Principle of Least Privilege*. Define scoped policies for each service, role, and user. Use IAM Access Analyzer or similar tools to review privileges.

### 🔸 2. Public Object Storage (S3, Blob, etc.)
**Problem:** Buckets or blobs accessible publicly due to misconfigured ACLs or policies.  
**Fix:** Disable public access at both the account and bucket levels. Use signed URLs or specific policies for temporary access.

### 🔸 3. Hardcoded Secrets in Code Repos
**Problem:** API keys, credentials, or secrets stored in plain text within source code.  
**Fix:** Use secrets managers (e.g., AWS Secrets Manager, Azure Key Vault). Audit your repos with tools like `truffleHog`, `Gitleaks`.

### 🔸 4. Insecure Default Configurations
**Problem:** Deploying services (e.g., databases, VMs) without configuring firewalls, encryption, or audit logging.  
**Fix:** Harden deployments using blueprints or secure IaC templates. Automate configuration baselines with `Terraform`, `Ansible`, or `Pulumi`.

---

**Recommended Tools:**
- `tfsec`, `Checkov` – scan Terraform for misconfigs
- `Gitleaks`, `TruffleHog` – detect secrets in source code
- CSPM tools – monitor security posture across your cloud accounts

> ⚠️ Security is not a one-time fix — it’s a continuous practice.
