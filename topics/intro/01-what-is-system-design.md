# What is System Design?

## 📖 Simple English Explanation

**System Design** is the process of planning **how different parts of a software system work together**.

It decides things like:

* How users send requests
* How servers handle requests
* How data is stored
* How systems handle millions of users
* How the system stays fast and available

In simple words:

> **System Design = Planning how to build a software system that can handle real-world users and traffic.**

---

## 🤔 Why is it Needed?

A simple application may work for 100 users.

But when it grows to **millions of users**, we need to think about:

* ⚡ Performance
* 📈 Scalability
* 🟢 Availability
* 💾 Data storage
* 🔒 Security
* ❌ Failures

System Design helps us solve these problems.

---

## 🌊 Simple Flow

```text
User
  ↓
Request
  ↓
Load Balancer
  ↓
Application Servers
  ↓
Cache / Database / Other Services
  ↓
Response
  ↓
User
```

---

## 💻 Example

Suppose we are designing **YouTube**.

We need to think about:

```text
User
 ↓
Upload / Watch Video
 ↓
Application Server
 ↓
Video Storage
 ↓
Database
 ↓
CDN
 ↓
User
```

We must design the system so that **millions of users can watch videos at the same time**.

---

## ⚖️ Important Things in System Design

```text
Performance
Scalability
Availability
Reliability
Consistency
Security
Cost
```

These often involve **trade-offs**.

For example:

> More servers → Better scalability → Higher cost

---

## 🔑 Important Idea

System Design is not about finding **one perfect architecture**.

It is about choosing the **right architecture for the requirements**.

---

## 🎯 Simple Understanding

> **System Design is about deciding what components a system needs, how they communicate, how data flows, and how the system handles growth and failures.**
