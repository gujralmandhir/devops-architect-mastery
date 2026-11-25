# 🚀 Multi-Cloud DevOps Architect Mastery

Hands-on, real-time lab repository for mastering **Git, Docker, CI/CD (Jenkins, GitLab CI, Azure DevOps), Kubernetes (Scratch On-Prem + EKS/AKS/GKE), Multi-Cloud (AWS, Azure, GCP), and Observability** using **Claude Code** as a Principal DevOps Architect mentor.

## 📁 Repository Structure

```text
devops-architect-mastery/
├── README.md              # Project overview & daily workflow guide
├── CLAUDE.md              # Claude Code tutor rules (Hinglish, Architecture-first, Token-optimized)
├── SYLLABUS.md            # Master checklist from Module 0 to Module 5
├── NOTES.md               # Root-cause & incident troubleshooting log
├── .claude/commands/      # Custom slash commands (/next, /break, /hint, /complete)
└── labs/                  # Hands-on labs, manifests, Jenkinsfiles, & cloud variants
```

## 🔄 Daily Learning Loop (Token-Optimized)

1. Open terminal in this repo and run:
   ```bash
   claude
   ```
2. **`/next`** — Claude reads `SYLLABUS.md`, draws an ASCII architecture diagram, compares On-Premises vs AWS vs Azure vs GCP in Hinglish, and builds a lab in `labs/`.
3. **Practice** — Run the lab on local Docker/Kind, GCP VMs, or AWS/Azure/GCP sandboxes.
4. **`/break`** — Claude silently injects a real-world production failure into your active lab. Diagnose and fix it using CLI tools and logs.
5. **`/hint`** — *(Optional)* Get a progressive debugging clue without revealing the answer.
6. **`/complete`** — Claude audits your fix, checks off `[x]` in `SYLLABUS.md`, and logs a 3-line summary in `NOTES.md`.
7. **Sync & Reset** — Push your progress to GitHub and clear Claude's context window:
   ```bash
   git add . && git commit -m "complete: <topic-name>" && git push
   ```
   Then inside Claude Code, run **`/clear`** before starting the next `/next` topic.

## ☁️ Cloud Credit & Cost-Control Rules
- **GCP VMs (On-Premises K8s Scratch Lab):** Always **STOP** VMs after practice to pause compute charges while preserving disk state.
- **Managed Clusters (EKS, AKS, GKE):** Spin up only during Module 4 labs and **DESTROY** immediately after completing the `/break` drill.
