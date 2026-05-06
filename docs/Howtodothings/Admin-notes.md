# Admin Workflow

This document explains the workflow for maintaining and publishing the Community Ground Knowledge Base using:

- Obsidian
- MkDocs
- GitHub
- GitHub Pages

---

# System Overview

The system works like this:

```text
Obsidian → Markdown Files → GitHub → MkDocs → Public Website
```

All content is stored as standard markdown (`.md`) files.

These files are:
- edited locally in Obsidian
- backed up in GitHub
- automatically published as a website using MkDocs

---

# Folder Structure

Project folder:

```text
community-ground/
├── docs/
├── mkdocs.yml
```

The `docs/` folder contains all website content.

This same folder is also opened as the Obsidian vault.

Example structure:

```text
docs/
├── index.md
├── admin-workflow.md
├── recipes/
├── stories/
├── maintenance/
├── events/
├── photos/
```

---

# Opening the Vault in Obsidian

Open Obsidian and choose:

```text
Open folder as vault
```

Select:

```text
C:\Users\Jacob\community-ground\docs
```

Do NOT select the entire `community-ground` folder.

Only select the `docs` folder.

---

# Running the Website Locally

Open PowerShell:

```powershell
cd C:\Users\Jacob\community-ground
python -m mkdocs serve
```

Then open:

```text
http://127.0.0.1:8000
```

This creates a live preview of the website.

Any changes saved in Obsidian will automatically appear in the local website preview.

---

# Creating New Pages

Inside Obsidian:
- create a new note
- place it in the correct folder
- save normally

Example:

```text
recipes/damper.md
```

---

# Recommended Markdown Style

Example page:

```markdown
# Damper Recipe

## Ingredients
- Flour
- Water
- Salt

## Method
Mix ingredients and cook over fire.
```

---

# Internal Linking

Use Obsidian wiki-links:

```markdown
[[Damper Recipe]]
[[Kitchen Procedures]]
```

This allows notes to connect together like a wiki.

---

# Images

Store images inside a folder such as:

```text
docs/photos/
```

Example markdown image:

```markdown
![Kitchen Setup](photos/kitchen.jpg)
```

---

# Website Navigation

Website navigation is controlled by:

```text
mkdocs.yml
```

If a new page is added, it should also be added to navigation.

Example:

```yaml
nav:
  - Home: index.md

  - Recipes:
      - Damper Recipe: recipes/damper.md

  - Stories:
      - Community History: stories/history.md

  - Admin:
      - Workflow: admin-workflow.md
```

---

# Publishing Changes

After making changes in Obsidian:

Open PowerShell:

```powershell
cd C:\Users\Jacob\community-ground
```

Then run:

```powershell
git add .
git commit -m "Updated content"
git push
python -m mkdocs gh-deploy
```

This:
1. saves changes into Git history
2. uploads changes to GitHub
3. republishes the website

---

# Website URL

Published website:

```text
https://YOURUSERNAME.github.io/community-ground/
```

Replace `YOURUSERNAME` with the GitHub username.

---

# Daily Workflow

Typical workflow:

1. Open Obsidian
2. Edit or create notes
3. Preview locally using MkDocs
4. Commit changes to GitHub
5. Deploy website

---

# Important Rules

## Always work inside the project folder

Before using Git commands:

```powershell
cd C:\Users\Jacob\community-ground
```

---

## Keep filenames simple

Good:

```text
damper-recipe.md
```

Avoid:
- spaces
- special characters
- very long names

---

## Use folders early

Keeping content organised early prevents future mess.

Recommended categories:
- recipes
- stories
- maintenance
- events
- admin
- photos

---

# Recommended Future Improvements

Possible future additions:

- Search improvements
- Tags/categories
- User contribution guides
- Custom domain
- Photo galleries
- Comments
- Automated deployment
- Obsidian Git integration

---

# Backup Safety

GitHub acts as:
- backup
- version history
- change tracking

If something breaks:
- previous versions can be restored

---

# Philosophy

The goal of this system is:

- simple
- free
- future-proof
- easy to edit
- community-owned
- portable

All content remains as plain markdown files that can be moved anywhere in the future.
