---
description: Create a GitHub repository and deploy to Vercel in one step
---

This workflow automates the process of initializing a Git repository, creating a remote repo on GitHub, and deploying the project to Vercel.

1. Initialize Git if not already present
// turbo
```bash
if [ ! -d .git ]; then
  git init
  git branch -m main
fi
```

2. Commit changes (if any)
// turbo
```bash
git add .
if git rev-parse --verify HEAD >/dev/null 2>&1; then
  if ! git diff-index --quiet HEAD --; then
    git commit -m "update: ship project"
  fi
else
  # First commit
  git commit -m "initial commit: ship project" || echo "Nothing to commit yet"
fi
```


3. Create GitHub repository (if not already exists) and push
// turbo
```bash
PROJECT_NAME=$(basename "$PWD" | tr '[:upper:]' '[:lower:]' | tr ' ' '-')
if ! gh repo view "$PROJECT_NAME" >/dev/null 2>&1; then
  gh repo create "$PROJECT_NAME" --public --source=. --remote=origin --push
else
  git push -u origin main
fi
```

4. Deploy to Vercel
// turbo
```bash
PROJECT_NAME=$(basename "$PWD" | tr '[:upper:]' '[:lower:]' | tr ' ' '-')
export PATH=$HOME/node_portable/bin:$PATH
vercel deploy --prod --yes --name "$PROJECT_NAME"
```

5. Link Vercel URL to GitHub
// turbo
```bash
PROJECT_NAME=$(basename "$PWD" | tr '[:upper:]' '[:lower:]' | tr ' ' '-')
VERCEL_URL=$(export PATH=$HOME/node_portable/bin:$PATH && vercel ls "$PROJECT_NAME" --json | grep -oP '"url":\s*"\K[^"]+' | head -n 1)
if [ ! -z "$VERCEL_URL" ]; then
  gh repo edit --homepage "https://$VERCEL_URL"
fi
```


