# action-repo

This repository is designed to trigger GitHub webhook events for actions like `push`, `pull_request`, and `merge`.

It serves as the *source repo* for webhook testing with another repo (`webhook-repo`) that receives these events and stores them in MongoDB.

---

## 📌 Features

* Triggers GitHub events:

  * Push
  * Pull Request
  * Merge
* Used in conjunction with a webhook endpoint

---

## 🔗 Webhook Setup

1. Go to `Settings` → `Webhooks`
2. Add a webhook with:

   * **Payload URL**: `http://<your-public-url>/webhook`
   * **Content type**: `application/json`
   * **Events**: `Just the push`, `pull_request`, and optionally `Merge` (on PR merge)

---

## 🛠️ How to Test

1. Clone this repo
2. Make a commit and push to trigger a push event
3. Open a PR to trigger `pull_request`
4. Merge the PR to simulate a merge event

---

## 🧑‍🤝‍🧑 Pair Repository

[webhook-repo](https://github.com/your-username/webhook-repo)

---

## 📁 Example Events

```json
{
  "action": "opened",
  "pull_request": { ... },
  "repository": { "name": "action-repo" },
  "sender": { "login": "Travis" }
}
```
