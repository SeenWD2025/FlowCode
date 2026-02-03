# QUICKSTART.md

# Quickstart Guide

### Get Up and Running in 5-10 Minutes

This guide gets you from zero to ready-to-build as fast as possible.

---

## ✅ **Prerequisites Check**

Before starting, make sure you have:

- [ ]  **Node.js installed** (v16 or later) - [Download here](https://nodejs.org/)
- [ ]  **Git installed** - [Download here](https://git-scm.com/)
- [ ]  **An IDE** - We recommend [VS Code](https://code.visualstudio.com/)
- [ ]  **OpenRouter API key** (Optional, for pre-optimized model assignments) - [Get one here](https://openrouter.ai/)

**Check your installations:**

```bash
node --version  # Should show v16 or higher
git --version   # Should show git version
```

If either command fails, install the missing tool first.

---

## 🚀 **Setup (5 Minutes)**

### Step 1: Clone the Template

```bash
# Clone into a new project directory
git clone https://github.com/devn-noble/ai-dev-template.git my-project-name
cd my-project-name
```

---

### Step 2: Generate Project Map

```bash
# This creates root-mapfile.md with an overview of all directories
node dev-tools/update-root-mapfile.js
```

**Expected output:**

```
✓ Project map generated at root-mapfile.md
✓ Found 10 directories with mapfiles
```

---

### Step 3: Initialize Git

```bash
# Start version control
git init
git add .
git commit -m "Initial commit: AI dev template setup"
```

---

### Step 4: Update Project Name

Open [`README.md`](http://README.md) in your IDE and:

1. Replace `"AI-Assisted Development Template"` with your project name
2. Update the description under the title
3. Save the file

---

## 🎯 **What You Just Did**

You now have:

- ✅ A complete folder structure for organized development
- ✅ Documentation templates ready to fill in
- ✅ Mapfiles in every directory for tracking work
- ✅ Git initialized for version control

**No code has been written yet.** That's intentional. We plan first, then build.

---

## 📝 **Next Steps (Start Building)**

### 1. **Brainstorm Your Idea**

Open `/dev-and-design-guides/[brainstorm.md](http://brainstorm.md)` and fill it in with:

- What problem does your app solve?
- Who are your users?
- What are the core features?
- Any technical preferences? (React vs Vue, Supabase vs Firebase, etc.)

**Time: 10-15 minutes**

---

### 2. **Define Your Scope**

Use your IDE's AI agent (GitHub Copilot, Cursor, etc.) to generate a scope document:

**Prompt:**

```
Read /dev-and-design-guides/brainstorm.md and create a detailed scope document in /dev-and-design-guides/SCOPE.md.

Include:
- What's IN SCOPE (features we're building)
- What's OUT OF SCOPE (features we're NOT building in v1)
- Success criteria
- Technical constraints

Follow the structure in the existing SCOPE.md template.
```

**Time: 5 minutes**

---

### 3. **Prioritize Your MVP**

Now define your Minimum Viable Product:

**Prompt:**

```
Based on SCOPE.md and brainstorm.md, fill in /dev-and-design-guides/mvp-mandates.md with:
- The 3-5 MUST-HAVE features for v1
- The "nice to have" features for v2
- What defines a successful v1 launch

Prioritize ruthlessly—what's the smallest version that delivers value?
```

**Time: 5 minutes**

---

### 4. **Generate Technical Specs**

Now let AI create all your development docs:

**Prompt to Lead Architect Agent:**

```
You are a Senior Software Architect following Devn-Noble SOPs.

Read all files in /dev-and-design-guides/ and generate complete technical specifications:

1. /docs/API.md - All endpoints, request/response schemas
2. /docs/AUTH.md - Authentication flows and security
3. /docs/DATABASE.md - Schema design and relationships
4. /docs/SETUP.md - Development environment setup
5. /docs/DEPLOYMENT.md - Production deployment procedures
6. /dev-and-design-guides/ARCHITECTURE.md - System architecture and tech stack decisions
7. /dev-and-design-guides/DEVELOPMENT-GUIDE.md - Coding standards and conventions

Use schema-first design principles. Include TypeScript types where applicable.
```

**Time: 10-15 minutes** (AI generates, you review)

---

### 5. **Review and Refine**

Read through the generated docs and fix any errors or gaps:

**Prompt:**

```
Review all documents in /docs and /dev-and-design-guides.

Check for:
- Inconsistencies between documents
- Missing technical details
- Ambiguous requirements
- Anything that violates Devn-Noble SOPs (see DEVN-NOBLE-SOP.md)

Provide a summary of issues and recommendations.
```

**Time: 10 minutes**

---

## 🎬 **You're Ready to Build**

At this point, you have:

- ✅ Clear scope and MVP priorities
- ✅ Complete technical specifications
- ✅ Architecture decisions documented
- ✅ Development standards defined

**Total time invested: ~1 hour**

---

## 🛠️ **Next: Follow the Full Workflow**

Now you're ready for the actual development process:

📖 **Continue to [WORKFLOW-GUIDE.md](http://WORKFLOW-GUIDE.md)** for the complete agent orchestration process.

---

## 🆘 **Common Setup Issues**

### **Issue: `node dev-tools/update-root-mapfile.js` fails**

**Solution:**

```bash
# Make sure you're in the project root directory
pwd  # Should show /path/to/your-project

# Check that the file exists
ls dev-tools/update-root-mapfile.js

# If missing, you may not have cloned correctly—re-clone
```

---

### **Issue: Git commands fail**

**Solution:**

```bash
# Check if Git is installed
git --version

# If not installed, download from https://git-scm.com/
```

---

### **Issue: Don't have an IDE**

**Solution:**

Download [VS Code](https://code.visualstudio.com/) (free, widely used, great AI integrations available).

---

**Happy building!** 🚀