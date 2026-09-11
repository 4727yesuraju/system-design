# CAP Theorem

## 📖 Simple English Explanation

**CAP Theorem** says that a distributed system cannot guarantee all three of these properties at the same time when a **network partition** occurs:

* **C — Consistency**
* **A — Availability**
* **P — Partition Tolerance**

In simple words:

> **When network communication between servers breaks, you must choose between Consistency and Availability.**

---

## 🤔 Why is it Needed?

In a distributed system, we usually have multiple servers:

```text
Server A  ←→  Server B
```

But the network can fail:

```text
Server A    X    Server B
          Network
          failure
```

Now Server A and Server B cannot communicate.

The system must decide:

```text
Return the latest correct data?
        OR
Keep responding even if data may be outdated?
```

CAP helps us understand this trade-off.

---

## 🌊 Simple Flow

Normally:

```text
              Database
             /        \
        Server A ←→ Server B
```

Network partition happens:

```text
        Server A    X    Server B
                     ↑
               Network failure
```

Now:

```text
Consistency
→ Both servers should return the same/latest data

Availability
→ Both servers should continue responding

Partition Tolerance
→ System continues working despite network failure
```

During the partition:

```text
        P is required
           ↓
    Choose C OR A
```

---

## 💻 Example

Imagine two database servers:

```text
Server A → Balance = ₹1000
Server B → Balance = ₹1000
```

User withdraws ₹500 through Server A:

```text
Server A → Balance = ₹500
Server B → Balance = ₹1000
```

But the network between them fails.

### Choose Consistency

Server B may refuse to process the request until it can synchronize.

```text
Network failure
      ↓
Wait / Reject request
      ↓
Keep data consistent
```

**Consistency ↑**
**Availability ↓**

### Choose Availability

Server B continues accepting requests using its current data.

```text
Network failure
      ↓
Continue responding
      ↓
Data may temporarily differ
```

**Availability ↑**
**Consistency ↓**

---

## ⚖️ CAP Components

### C — Consistency

Every successful read gets the **same/latest data** according to the system's consistency guarantee.

```text
Write → Data updated
          ↓
Read from another node
          ↓
See the required latest value
```

### A — Availability

Every request to a healthy/reachable node receives a response, even if that response may not contain the latest data.

```text
Request
   ↓
Response
```

### P — Partition Tolerance

The system continues operating even when communication between nodes is disrupted.

```text
Server A    X    Server B
```

---

## 🔑 Important Idea

The most important part of CAP is:

> **The trade-off happens when a network partition occurs.**

It is **not** simply:

> "Choose any two of C, A, and P."

In a distributed system, network partitions are considered possible, so **P is generally required**.

Therefore, during a partition, the practical choice is:

```text
CP → Consistency + Partition Tolerance

OR

AP → Availability + Partition Tolerance
```

---

## 💻 Simple Examples

### CP System

```text
Network partition
      ↓
Prefer correct/consistent data
      ↓
Some requests may fail or wait
```

Useful when **stale data is dangerous**.

Example:

```text
Banking / financial transactions
```

### AP System

```text
Network partition
      ↓
Continue responding
      ↓
Some data may temporarily be stale
      ↓
Synchronize later
```

Useful when **being available is more important than immediate consistency**.

Example:

```text
Social media likes / counters
```

---

## 🎯 Simple Understanding

Remember:

```text
C = Same / consistent data
A = Always respond
P = Survive network partition
```

When a partition happens:

```text
             Network Partition
                    ↓
             ┌──────┴──────┐
             ↓             ↓
            CP            AP
             ↓             ↓
       Prefer C        Prefer A
       + P             + P
```

> **CAP Theorem = During a network partition, a distributed system must choose between Consistency and Availability.**
