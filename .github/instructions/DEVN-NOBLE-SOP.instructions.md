# DEVN-NOBLE-SOP.md

# Devn-Noble Standard Operating Procedures (SOP)

### Quality-First AI-Assisted Development

This document codifies the **Devn-Noble Way**—a set of principles and practices that differentiate production-grade AI development from quick hacks.

---

## 🎯 **Philosophy**

### **The Problem with Typical AI Coding**

Most AI coding tools optimize for **speed**:

- "Just get something working"
- Placeholders and TODOs everywhere
- Patches on patches
- No security review
- No testing strategy
- Codebase bloat

**Result:** Apps that demo well but break in production.

### **The Devn-Noble Difference**

We optimize for **quality and sustainability**:

- Build it right the first time
- Complete implementations only
- Security as a requirement, not an afterthought
- Test-driven iteration
- Minimal, maintainable codebases

**Result:** Apps that ship to production and stay there.

---

## ⚖️ **Core Principles**

### 1. **Schema-First Design with Strong Contracts**

**What it means:**

- Define data structures, API contracts, and interfaces BEFORE writing implementation code
- Use TypeScript types, JSON schemas, OpenAPI specs, database schemas as your source of truth

**Why it matters:**

- AI agents work better with clear specifications
- Prevents integration bugs between components
- Makes testing and validation straightforward

**In practice:**

```tsx
// ✅ DO: Define types first
interface User {
  id: string;
  email: string;
  createdAt: Date;
}

// Then implement
async function getUser(id: string): Promise<User> { ... }

// ❌ DON'T: Write code with implicit types and hope for the best
async function getUser(id) { ... }
```

---

### 2. **Consistency in Naming Conventions and Documentation**

**What it means:**

- Pick a naming style (camelCase, snake_case, PascalCase) and stick to it
- Every function, class, and module has a purpose comment
- Complex logic has inline explanations

**Why it matters:**

- AI agents rely on naming patterns to understand intent
- Future you (and future AI sessions) won't have to reverse-engineer your code
- Easier onboarding for collaborators

**In practice:**

```tsx
// ✅ DO: Consistent naming + clear docs
/**
 * Validates user email format and checks against blocklist.
 * @param email - User-provided email string
 * @returns true if valid and not blocked, false otherwise
 */
function validateUserEmail(email: string): boolean { ... }

// ❌ DON'T: Inconsistent naming, no docs
function chkEmail(e) { ... }
```

---

### 3. **Strong Typing - Must Pass Linting and Type Checking**

**What it means:**

- Use TypeScript (or Flow, or strict mode in other languages)
- Configure ESLint/Prettier and enforce them
- Zero linting errors before committing code
- Zero type errors in production builds

**Why it matters:**

- Catches 80% of bugs before runtime
- AI-generated code is safer when constrained by types
- Refactoring becomes trivial with type safety

**In practice:**

```bash
# Run before every commit
npm run lint      # Must pass
npm run type-check # Must pass
npm run test       # Must pass
```

---

### 4. **Iterative Refinement and Testing Until Passed**

**What it means:**

- Write the feature → Write the test → Run the test → Fix until green → Move on
- NO "we'll test it later" mentality
- Each feature is tested in isolation before integration

**Why it matters:**

- Bugs found early are 10x cheaper to fix than bugs found in production
- Prevents technical debt accumulation
- Builds confidence in the codebase

**In practice:**

```bash
# Workflow for every feature
1. Implement feature in /apps
2. Write tests in /tests
3. Run: npm test
4. If red → Debug and fix
5. If green → Commit and move to next feature
```

---

### 5. **Zero High/Critical Vulnerabilities**

**What it means:**

- Run `npm audit` (or equivalent) regularly
- High and critical vulnerabilities MUST be resolved before deployment
- If a package has unfixable vulnerabilities, find an alternative

**Why it matters:**

- Security breaches destroy trust and can be legally catastrophic
- Many vulnerabilities are trivial to exploit
- Prevention is easier than incident response

**In practice:**

```bash
# Before deploying
npm audit --audit-level=high

# If vulnerabilities found:
# 1. Update packages: npm audit fix
# 2. If unfixable: Research alternative packages
# 3. Document decision in /logs/decisions/
```

---

### 6. **Build for Production, Not Vanity**

**What it means:**

- Optimize for performance, scalability, and maintainability
- No features just because they're trendy
- Every feature must serve a user need

**Why it matters:**

- Vanity features waste time and add complexity
- Production systems need to handle edge cases, errors, and scale
- Users care about reliability, not flashy demos

**In practice:**

- ✅ DO: Error handling, loading states, retry logic, graceful degradation
- ❌ DON'T: Animations, easter eggs, experimental APIs before core features work

---

### 7. **Inform Stakeholders of Placeholders and Gaps**

**What it means:**

- If you can't implement something fully (missing API keys, unclear requirements), document it explicitly
- Don't hide incomplete work in the code—surface it immediately

**Why it matters:**

- Surprises late in development are expensive
- Stakeholders can prioritize getting you what you need
- Prevents "90% done" projects that never ship

**In practice:**

```tsx
// ✅ DO: Make incompleteness visible
throw new Error("Payment integration requires Stripe API key - see docs/SETUP.md");

// ❌ DON'T: Hide it with a TODO
// TODO: Add payment processing
```

---

### 8. **Quality Over Speed**

**What it means:**

- A stable app that ships next week beats a buggy app that ships today
- Rushed code creates tech debt that slows future development
- Users forgive late launches, not broken experiences

**Why it matters:**

- Reputational damage from buggy launches is hard to recover from
- Debugging production issues is 10x more stressful than building it right
- Quality compounds—good foundations enable fast future iteration

**In practice:**

- ✅ Ship when tests pass and docs are complete
- ❌ Ship to "hit a deadline" with known critical bugs

---

### 9. **Build Real Tools for Users, Not Out of Greed**

**What it means:**

- Solve genuine problems
- Respect user privacy and data
- Monetization is ethical and transparent
- No dark patterns, no exploitative tactics

**Why it matters:**

- Users can tell when you care vs. when you're extracting value
- Long-term success requires trust
- Ethical business outcompetes extractive systems (it just takes patience)

**In practice:**

- ✅ Transparent pricing, clear privacy policy, user control over data
- ❌ Hidden fees, selling user data, engagement manipulation

---

## 🚫 **Anti-Patterns We Prevent**

### **1. No Placeholders, Stubs, or Hidden TODOs**

**The Problem:**

```tsx
function processPayment(amount: number) {
  // TODO: Implement payment processing
  console.log("Payment processed:", amount);
}
```

This looks done but doesn't work. When discovered late, it's a crisis.

**The Devn-Noble Way:**

- If it's not done, the function should throw an error or the feature should be marked as "not implemented" in the UI
- Document incomplete features in `/docs` and the relevant mapfile

---

### **2. No Patches During Initial Development**

**The Problem:**

You write a feature, it's buggy, so you add a "quick fix" patch... then another patch... then the code is unmaintainable.

**The Devn-Noble Way:**

- If something doesn't work, refactor it properly BEFORE moving on
- Patches are only acceptable in production hotfixes (and should be replaced with proper fixes ASAP)

---

### **3. Do Not Build Off Assumptions—Gain Clarity**

**The Problem:**

"I think the API returns JSON, so I'll write code assuming that." (Spoiler: It returns XML.)

**The Devn-Noble Way:**

- Read the docs
- Test your assumptions with actual API calls
- Ask the product owner / stakeholder / user when requirements are unclear
- Document decisions in `/logs/decisions/`

---

### **4. Do Not Bloat the Codebase**

**The Problem:**

Adding 10 libraries to do something that could be done in 20 lines of native code.

**The Devn-Noble Way:**

- Prefer standard library solutions
- Only add dependencies when they save significant time or provide well-tested complexity (e.g., authentication, payments)
- Regularly audit and remove unused dependencies

---

## 🔄 **Non-Negotiable Best Practices**

### **Prioritize Planning and Documentation**

**Before writing code:**

1. Fill in `/dev-and-design-guides/[brainstorm.md](http://brainstorm.md)` with your idea
2. Use AI to draft `/dev-and-design-guides/[SCOPE.md](http://SCOPE.md)` (what's in, what's out)
3. Define MVP in `/dev-and-design-guides/[mvp-mandates.md](http://mvp-mandates.md)`
4. Have AI generate full specs in `/docs`

**Why:** 1 hour of planning saves 10 hours of debugging.

---

### **Complete One Feature at a Time**

**Workflow:**

1. Pick ONE feature from the task list
2. Implement it fully
3. Write tests
4. Run tests until they pass
5. Commit
6. Move to next feature

**Why:** Partial features create integration hell. Finish what you start.

---

### **Perform Regression Testing**

**What it means:**

When you add a new feature, test that you didn't break existing features.

**In practice:**

- Run the full test suite after every change (not just new tests)
- Manually test critical user flows if you don't have automated coverage yet

---

## 🤝 **How Devn-Noble SOP Changes AI Behavior**

### **Typical AI Coding:**

- AI optimizes for "looks done"
- Generates code fast, doesn't validate it
- Adds placeholders liberally
- Doesn't consider security, testing, or maintainability unless explicitly prompted

### **Devn-Noble AI Coding:**

- AI is instructed to act as a **PM and junior architect** monitoring its own work
- Quality, security, and efficiency are part of every prompt
- AI is forced to think: "What's the best way to implement this?" not "What's the fastest way?"
- AI must justify decisions and flag gaps

### **Prompt Pattern Example:**

```
You are a Senior TypeScript Developer following Devn-Noble SOPs.

Your task: Implement user authentication with JWT tokens.

Requirements:
- Schema-first: Define User and Token types first
- Strong typing: No `any` types
- Security: Hash passwords with bcrypt, validate JWTs
- Testing: Write unit tests for login, token validation, and logout
- Documentation: Add inline comments for complex logic
- Quality: No placeholders—implement fully or throw errors with clear messages

Before writing code, outline your approach and ask for clarification on any ambiguous requirements.
```

---

## 📊 **Success Criteria**

You're following Devn-Noble SOPs when:

- ✅ Your codebase passes linting and type checking with zero errors
- ✅ Your test suite runs and passes for all implemented features
- ✅ `npm audit` shows zero high or critical vulnerabilities
- ✅ A new developer (or AI agent) can read your docs and understand the system
- ✅ You can deploy to production without "one more quick fix"
- ✅ Your mapfiles are up to date and accurately reflect project state

---

**Quality isn't slow. Rework is slow. Build it right the first time.**