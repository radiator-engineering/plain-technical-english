Write a how-to guide: "How to rotate a GCP service-account key used by a Kubernetes workload."

Answers to the standard clarifying questions, so you can proceed directly to the final document:
- Document type: How-to guide (problem-oriented recipe, per Diátaxis).
- Target audience: experienced platform engineers who know kubectl and gcloud but have not done this specific rotation.
- User's goal: replace an existing SA key with a new one, with zero workload downtime, and revoke the old key.
- Scope: include key creation, secret update, rollout, verification, and old-key deletion. Exclude Workload Identity migration (mention it in one sentence as the better long-term option), exclude Terraform, exclude CI automation.

Skip outline approval — produce the complete final document in Markdown now. Return only the document, no commentary or questions.
