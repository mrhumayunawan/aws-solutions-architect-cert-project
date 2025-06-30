# 🧔 Identity and Access Management (IAM)

This section provides a foundational overview of **Identity and Access Management (IAM)** for the **AWS Certified Solutions Architect – Associate (SAA-C03)** certification.

---

## 🎯 Objective

Gain a clear understanding of how AWS handles identity, access control, and authorization through IAM components such as **users**, **groups**, **roles**, and **policies**.

---

## 🔐 What is IAM?

**Identity and Access Management (IAM)** is a **global AWS service** that allows you to securely manage **identities (users, groups, roles)** and control access to AWS services and resources.

IAM operates at no cost and provides fine-grained permissions using **JSON-based policies**.

---

## 👤 IAM Account Structure

* **Root User**

  * Created by default when an AWS account is initialized.
  * Has **unrestricted access** and **cannot** be limited via policies.
  * Should be secured using **Multi-Factor Authentication (MFA)** and **used sparingly**.

* **IAM User**

  * Represents individual people or applications.
  * Assigned long-term credentials (username/password, access keys).
  * By default, users have **no permissions**.

* **IAM Group**

  * A logical collection of IAM users.
  * Policies attached to groups apply to **all member users**.
  * Useful for managing permissions in bulk (e.g., Dev, HR, Admin teams).

* **IAM Role**

  * An identity **assumed temporarily** by trusted entities such as AWS services, users, or external identities.
  * Does **not have credentials** like users.
  * Roles are ideal for **cross-account access** or assigning **temporary permissions**.

---

## 🧾 IAM Policies

* Policies are JSON documents that **allow or deny** access to AWS services.
* They are attached to IAM **users**, **groups**, or **roles**.
* Types of policies:

  * **Identity-based policies** (attached to users/groups/roles)
  * **Resource-based policies** (attached to resources like S3 buckets)

### Policy Evaluation Logic

1. **Explicit Deny** (always overrides)
2. **Explicit Allow**
3. **Implicit Deny** (default)

---

## ✅ IAM Core Responsibilities

IAM is responsible for:

1. **Managing Identities**

   * Create, modify, delete users, groups, and roles.

2. **Authentication**

   * Verify that a user/service is who they claim to be (e.g., via passwords, access keys, MFA).

3. **Authorization**

   * Enforce what actions a principal can or cannot perform based on attached policies.

---

## 🌍 IAM is Global

* IAM is a **global** service.
* IAM resources (users, roles, policies) are not bound to any specific AWS region.
* Each AWS account has its own dedicated IAM instance.

---

## 🔑 Access Keys (for Programmatic Access)

* **Access Keys** are used to access AWS via CLI, SDKs, or APIs.
* Each access key includes:

  * **Access Key ID** (public)
  * **Secret Access Key** (private; shown only once)

### Key Management Guidelines

* A user can have **up to two access keys**.
* If leaked, the keys must be **revoked and regenerated**.
* Use access keys **only when necessary** — prefer IAM roles for AWS service access.
* Rotate keys periodically for security.

> ⚠️ Never share or commit access keys in version control systems (e.g., GitHub).

---

## 🧳 Identity Federation & MFA

* IAM supports **federation** with external identity providers (e.g., Facebook, Google, SAML).
* **MFA (Multi-Factor Authentication)** is strongly recommended for all privileged identities.

---

## 📌 Example Access Key Format (Do Not Use in Production)

```bash
Access Key ID:     ABABABABABABABA
Secret Access Key: oierWRhoefWORIOF/DFLWAnljef
```

--- 

## 🖼️ IAM Overview Diagram

![IAM Architecture](./IAM.png)

