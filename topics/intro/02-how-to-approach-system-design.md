# How to Approach System Design?

## 📖 Simple English Explanation

When solving a System Design problem, don't immediately start drawing components.

First understand the **requirements**, then estimate the **scale**, identify the important **components**, and finally design the system step by step.

A simple approach is:

> **Requirements → Scale → APIs → High-Level Design → Data → Deep Dive → Trade-offs**

---

## 🤔 Why is it Needed?

A System Design problem can be very large.

A step-by-step approach helps us:

* Understand what needs to be built
* Avoid unnecessary components
* Identify bottlenecks
* Think about scalability and reliability
* Explain our design clearly

---

## 🌊 Simple Flow

```text
1. Understand Requirements
          ↓
2. Estimate Scale
          ↓
3. Define APIs
          ↓
4. Design High-Level Architecture
          ↓
5. Design Database / Storage
          ↓
6. Add Cache / Queue / CDN if needed
          ↓
7. Think About Scalability & Failures
          ↓
8. Discuss Trade-offs
```

---

## 💻 Example

Suppose the interviewer asks:

> **Design a URL Shortener**

### Step 1 — Requirements

```text
User gives a long URL
        ↓
System generates short URL
        ↓
User opens short URL
        ↓
System redirects to original URL
```

### Step 2 — Scale

Ask:

```text
How many users?
How many requests?
How much data?
Read-heavy or write-heavy?
```

### Step 3 — APIs

```text
POST /shorten
GET /{shortCode}
```

### Step 4 — High-Level Design

```text
User
 ↓
Load Balancer
 ↓
Application Servers
 ↓
Cache
 ↓
Database
```

### Step 5 — Think About Problems

```text
High traffic?
→ Add more servers

Database becomes slow?
→ Add cache / replicas

Server fails?
→ Use multiple servers

Traffic increases?
→ Scale horizontally
```

### Step 6 — Trade-offs

```text
More replicas
→ Better read scalability
→ More infrastructure cost

More caching
→ Faster responses
→ Possible stale data
```

---

## 🔑 Important Idea

Don't start with:

> "Should I use Redis?"

Start with:

> **"What problem do I need to solve?"**

Then choose the technology or architecture that solves that problem.

---

## 🎯 Simple Understanding

> **Understand the requirements first, then design the simplest system that satisfies them, and finally improve it for scale, reliability, and performance.**
