# WORKFLOW-GUIDE.md

# Complete Workflow Guide

### Vibe Coding: From Idea to Deployed App

This guide walks through the **complete Devn-Noble workflow** for building production-ready apps using AI agent orchestration.

---

## 📋 **Prerequisites**

Before starting this workflow, you should have completed:

- ✅ **Setup** - Followed [QUICKSTART.md](http://QUICKSTART.md)
- ✅ **Planning docs filled** - [brainstorm.md](http://brainstorm.md), [SCOPE.md](http://SCOPE.md), [mvp-mandates.md](http://mvp-mandates.md)
- ✅ **Tech specs generated** - All `/docs` files completed
- ✅ **Architecture reviewed** - [ARCHITECTURE.md](http://ARCHITECTURE.md) finalized

If you haven't done these, go back to [QUICKSTART.md](http://QUICKSTART.md) first.

---

## 🎯 **The Workflow (15 Steps)**

### **Phase 1: Architecture & Planning**

#### **Step 1: Create the Single Source of Truth (SSoT)**

**Agent:** Lead Architect  

**Mode:** Agent / Edit  

**Input:** All files in `/dev-and-design-guides/`

**Prompt:**

```
You are a Lead Architect following Devn-Noble SOPs.

Read all files in /dev-and-design-guides/ and create a Single Source of Truth (SSoT) document at /dev-and-design-guides/SSOT.md.

This document should:
- Consolidate all requirements, scope, and MVP priorities
- Define the complete system architecture
- Specify all data models and API contracts
- List all technical decisions and rationale
- Serve as the authoritative reference for all future development

Use schema-first design. Be specific and complete—no placeholders.
```

**Expected Output:** `/dev-and-design-guides/[SSOT.md](http://SSOT.md)` created

**Time:** 10 minutes

---

#### **Step 2: Generate Supporting Spec Docs**

**Agent:** Documentation Specialist  

**Mode:** Agent / Edit  

**Input:** `/dev-and-design-guides/[SSOT.md](http://SSOT.md)`

**Prompt:**

```
You are a Documentation Specialist.

Read /dev-and-design-guides/SSOT.md and generate complete, detailed specification documents:

1. /docs/API.md - Every endpoint with request/response examples
2. /docs/DATABASE.md - Full schema with types and relationships
3. /docs/AUTH.md - Complete authentication and authorization flows
4. /docs/SETUP.md - Step-by-step dev environment setup
5. /docs/DEPLOYMENT.md - Production deployment procedures
6. /dev-and-design-guides/TESTING-STRATEGY.md - Testing approach and coverage targets

Follow Devn-Noble SOPs: schema-first, strong typing, complete implementations only.
```

**Expected Output:** All spec docs in `/docs/` completed

**Time:** 15 minutes

---

#### **Step 3: Architect Reviews Generated Specs**

**Agent:** Senior Architect  

**Mode:** Ask / Chat  

**Input:** All `/docs/` files + SSOT

**Prompt:**

```
You are a Senior Architect reviewing technical specifications.

Read:
- /dev-and-design-guides/SSOT.md
- All files in /docs/

Check for:
- Inconsistencies between documents
- Missing technical requirements
- Security vulnerabilities in the design
- Performance bottlenecks
- Violations of Devn-Noble SOPs

Provide a detailed review with specific corrections needed.
```

**Expected Output:** List of corrections/improvements

**Action:** Apply architect's feedback by updating docs (use agent in Edit mode)

**Time:** 15 minutes

---

#### **Step 4: Final Architecture Review**

**Agent:** Senior Architect  

**Mode:** Ask / Chat  

**Prompt:**

```
Review the current project state:
- All docs in /dev-and-design-guides/
- All docs in /docs/

Provide a final assessment:
- **PROS:** What's well-designed?
- **CONS:** What are the risks or weak points?
- **RECOMMENDATIONS:** Any final changes before development starts?

Be honest—if something will cause problems later, flag it now.
```

**Expected Output:** Final recommendations

**Action:** Make any critical fixes before proceeding

**Time:** 10 minutes

---

### **Phase 2: Project Planning**

#### **Step 5: Generate Task List and Timeline**

**Agent:** Project Manager  

**Mode:** Agent / Edit  

**Input:** All `/docs/` + SSOT

**Prompt:**

```
You are a Project Manager creating a development plan.

Read all files in /docs/ and /dev-and-design-guides/.

Generate:
1. /dev-and-design-guides/TASK-LIST.md - Every feature broken into tasks with:
   - Task ID
   - Description
   - Dependencies (what must be done first)
   - Estimated time
   - Assigned agent role (Frontend Dev, Backend Dev, QA, etc.)

2. /dev-and-design-guides/TIMELINE.md - Sprint schedule with:
   - Sprint 1, 2, 3... (each sprint is 1-3 days)
   - Which tasks happen in which sprint
   - What can be parallelized
   - Testing checkpoints

Follow Devn-Noble SOP: Complete one feature fully before starting the next.
```

**Expected Output:** [TASK-LIST.md](http://TASK-LIST.md) and [TIMELINE.md](http://TIMELINE.md) created

**Time:** 10 minutes

---

#### **Step 6: Architect Reviews Task Plan**

**Agent:** Senior Architect  

**Mode:** Ask / Chat  

**Input:** [TASK-LIST.md](http://TASK-LIST.md), [TIMELINE.md](http://TIMELINE.md)

**Prompt:**

```
Review the task list and timeline at:
- /dev-and-design-guides/TASK-LIST.md
- /dev-and-design-guides/TIMELINE.md

Check for:
- Missing tasks
- Incorrect dependency ordering
- Tasks that should be split or combined
- Unrealistic time estimates
- Opportunities for better parallelization

Provide specific improvements.
```

**Expected Output:** Task plan revisions

**Action:** Update task plan based on feedback

**Time:** 10 minutes

---

#### **Step 7: Generate Testing Plan**

**Agent:** Lead QA Engineer  

**Mode:** Agent / Edit  

**Input:** All `/docs/` + [TASK-LIST.md](http://TASK-LIST.md)

**Prompt:**

```
You are a Lead QA Engineer creating a testing strategy.

Read all files in /docs/, TASK-LIST.md, and TIMELINE.md.

Generate /dev-and-design-guides/TESTING-PLAN.md with:
- **Unit tests:** What functions/modules need unit tests?
- **Integration tests:** What API endpoints and DB operations need testing?
- **System tests:** What end-to-end user flows need testing?
- **Acceptance tests:** What are the success criteria for each feature?

For each task in TASK-LIST.md, specify:
- What tests must pass before the task is considered complete
- Test file locations (e.g., /tests/unit/auth.test.ts)

Follow Devn-Noble SOP: No moving forward until tests pass.
```

**Expected Output:** [TESTING-PLAN.md](http://TESTING-PLAN.md) created

**Time:** 10 minutes

---

#### **Step 8: Architect Reviews Testing Plan**

**Agent:** Senior Architect  

**Mode:** Ask / Chat  

**Input:** [TESTING-PLAN.md](http://TESTING-PLAN.md)

**Prompt:**

```
Review /dev-and-design-guides/TESTING-PLAN.md.

Check for:
- Insufficient test coverage for critical features
- Missing edge cases
- Security tests (auth, input validation, etc.)
- Performance/load testing needs

Provide specific additions or improvements.
```

**Expected Output:** Testing plan revisions

**Action:** Update testing plan

**Time:** 5 minutes

---

### **Phase 3: Development**

#### **Step 9: Setup Development Environment**

**Agent:** Senior Developer  

**Mode:** Agent / Edit  

**Input:** /docs/[SETUP.md](http://SETUP.md), /docs/[ARCHITECTURE.md](http://ARCHITECTURE.md)

**Prompt:**

```
You are a Senior Developer setting up the development environment.

Based on /docs/SETUP.md and /docs/ARCHITECTURE.md:

1. Initialize the project:
   - Create package.json with all dependencies
   - Set up TypeScript/ESLint/Prettier configs
   - Create .env.example with required environment variables
   - Set up folder structure in /apps (frontend, backend, shared libs)

2. Install dependencies:
   - Run npm install
   - Verify all tools work (linting, type checking)

3. Create initial boilerplate:
   - Entry points (index.ts, App.tsx, etc.)
   - Basic server setup if backend
   - Basic routing if frontend

Follow Devn-Noble SOPs: Strong typing, linting must pass, zero vulnerabilities.
```

**Expected Output:**  

- package.json created
- Dependencies installed
- Boilerplate code in /apps
- .env.example created

**Time:** 20 minutes

---

#### **Step 10: Execute Sprint 1**

**Agent:** Development Coordinator  

**Mode:** Agent / Edit  

**Input:** [TASK-LIST.md](http://TASK-LIST.md) (Sprint 1 tasks)

**Prompt:**

```
You are a Development Coordinator orchestrating Sprint 1.

Read /dev-and-design-guides/TASK-LIST.md and identify all Sprint 1 tasks.

For each task:
1. Implement the feature following /docs/ specifications
2. Follow Devn-Noble SOPs (schema-first, strong typing, complete implementation)
3. Update the relevant mapfile in the directory you worked in
4. Log your work in the mapfile's work log section

Tasks to complete:
[List specific Sprint 1 tasks from TASK-LIST.md]

Work methodically. Complete each task fully before moving to the next.

When all Sprint 1 tasks are complete, report: "Sprint 1 complete. Ready for testing."
```

**Expected Output:**  

- All Sprint 1 features implemented
- Mapfiles updated with work logs
- Code passes linting and type checking

**Time:** Varies (1-4 hours depending on complexity)

---

#### **Step 11: Test Sprint 1**

**Agent:** QA Engineer  

**Mode:** Agent / Edit  

**Input:** [TESTING-PLAN.md](http://TESTING-PLAN.md) (Sprint 1 tests)

**Prompt:**

```
You are a QA Engineer testing Sprint 1 deliverables.

Read /dev-and-design-guides/TESTING-PLAN.md and identify all tests for Sprint 1 tasks.

For each test:
1. Write the test code in /tests/ (unit, integration, or system as specified)
2. Run the tests: npm test
3. If tests fail, report the failures with details
4. If tests pass, mark the task as validated

Do not proceed to Sprint 2 until all Sprint 1 tests pass.
```

**Expected Output:**  

- Test files created in /tests
- All tests passing
- Failures reported if any

**Action if tests fail:** Return to Step 10, fix issues, re-test

**Time:** 30 minutes - 1 hour

---

#### **Step 12: Iterate Through Remaining Sprints**

Repeat Steps 10-11 for Sprint 2, Sprint 3, etc. until all tasks in [TASK-LIST.md](http://TASK-LIST.md) are complete.

**After each sprint:**

- ✅ All features implemented
- ✅ All tests passing
- ✅ Mapfiles updated
- ✅ Regression tests run (full test suite, not just new tests)

**Time:** Varies based on project size

---

### **Phase 4: Finalization**

#### **Step 13: Generate Marketing & Legal Docs**

**Agent:** Marketing & Legal Specialist  

**Mode:** Agent / Edit  

**Input:** All `/docs/` + app features

**Prompt:**

```
You are a Marketing and Legal Specialist finalizing public-facing documents.

Based on the project in /docs/ and /dev-and-design-guides/, generate:

1. /docs/PRIVACY-POLICY.md - Complete privacy policy
2. /docs/TERMS-OF-SERVICE.md - Terms of service
3. /docs/USER-GUIDE.md - End-user documentation
4. /docs/FAQ.md - Frequently asked questions

Ensure legal docs are compliant with GDPR and other regulations.
```

**Expected Output:** Privacy policy, TOS, user docs created

**Time:** 15 minutes

---

#### **Step 14: Polish Documentation and Code Comments**

**Agent:** Documentation Specialist  

**Mode:** Agent / Edit  

**Input:** All code in /apps, all docs in /docs

**Prompt:**

```
You are a Documentation Specialist performing a final polish.

Review:
- All code in /apps for inline comments and function docs
- All files in /docs for clarity, completeness, and consistency
- All mapfiles for up-to-date work logs

Tasks:
1. Add/improve inline code comments where complex logic exists
2. Ensure every public function has a doc comment
3. Fix any typos or formatting issues in /docs
4. Update root README.md with final project description
5. Verify all links in docs are correct

Output: Summary of changes made.
```

**Expected Output:**  

- Improved code comments
- Polished documentation
- [README.md](http://README.md) finalized

**Time:** 20 minutes

---

#### **Step 15: Final Deployment Check**

**Agent:** DevOps Specialist  

**Mode:** Ask / Chat  

**Input:** /docs/[DEPLOYMENT.md](http://DEPLOYMENT.md)

**Prompt:**

```
Review /docs/DEPLOYMENT.md and the current project state.

Checklist:
- [ ] All environment variables documented in .env.example
- [ ] Deployment instructions are complete and accurate
- [ ] CI/CD pipeline configured (if applicable)
- [ ] Database migrations ready
- [ ] Monitoring/logging set up
- [ ] Security scan passed (npm audit)
- [ ] Performance testing done (if applicable)

Report: Is this project ready for production deployment? If not, what's missing?
```

**Expected Output:** Deployment readiness report

**Action:** Fix any gaps before deploying

**Time:** 15 minutes

---

## 🎉 **You're Done!**

### **What You've Built:**

- ✅ Fully documented app with specs, guides, and decision records
- ✅ Complete codebase passing linting, type checking, and tests
- ✅ Zero high/critical vulnerabilities
- ✅ Production-ready deployment configuration
- ✅ User-facing docs (privacy policy, TOS, user guide)
- ✅ Trackable work history in mapfiles

### **What Happens Next:**

1. **Deploy to staging** - Follow /docs/[DEPLOYMENT.md](http://DEPLOYMENT.md)
2. **User acceptance testing** - Get real users to try it
3. **Fix any issues** - Use the same iterative process
4. **Deploy to production** - Ship it!

---

## 📊 **Expected Time Investment**

| Phase | Time |
| --- | --- |
| Architecture & Planning | 1-1.5 hours |
| Project Planning | 45 minutes |
| Development (simple app) | 4-8 hours |
| Development (complex app) | 1-3 days |
| Finalization | 1 hour |

**Total for simple web app:** 1 day  

**Total for complex app:** 1 week

---

## 🛠️ **Tips for Success**

### **1. Trust the Process**

Don't skip planning steps to "start coding faster." The time you invest in specs saves hours of debugging later.

### **2. One Feature at a Time**

Resist the urge to work on multiple features in parallel until you're experienced with this workflow.

### **3. Test Early and Often**

Write tests as you build, not after. Bugs found early are exponentially cheaper to fix.

### **4. Update Mapfiles**

They feel tedious, but they're invaluable for resuming work or bringing in collaborators.

### **5. Use Regression Testing**

Every time you add a feature, run the FULL test suite to catch unintended side effects.