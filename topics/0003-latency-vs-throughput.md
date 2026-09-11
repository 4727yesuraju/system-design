# Latency vs Throughput

## 📖 Simple English Explanation

**Latency** is the time taken to complete **one request**.

**Throughput** is the number of requests a system can handle **in a given amount of time**.

In simple words:

> **Latency = How fast is one request?**
> **Throughput = How many requests can we handle?**

---

## 🤔 Why is it Needed?

When designing a system, we need to know both:

```text
Latency
→ Is the system responding quickly?

Throughput
→ Can the system handle many requests?
```

A system can have **low latency** but still have **low throughput**.

---

## 🌊 Simple Flow

### Latency

```text
Request
   ↓
Processing
   ↓
Response

100 ms
↑
Latency
```

### Throughput

```text
Requests
 ↓ ↓ ↓ ↓ ↓
[   Server   ]
 ↓ ↓ ↓ ↓ ↓

1,000 requests / second
↑
Throughput
```

---

## 💻 Example

Suppose an API takes **100 ms** to respond to a request.

```text
Latency = 100 ms
```

If the server can process **1,000 requests every second**:

```text
Throughput = 1,000 requests/second
```

So:

```text
Latency
→ Time for one request

Throughput
→ Requests handled per second
```

---

## ⚖️ Latency vs Throughput

| Latency                  | Throughput                 |
| ------------------------ | -------------------------- |
| Time taken by a request  | Number of requests handled |
| Measured in ms / seconds | Measured in requests/sec   |
| Focuses on speed         | Focuses on capacity        |
| Lower is usually better  | Higher is usually better   |

---

## 🔑 Important Idea

Think about a **restaurant**:

```text
Latency
→ How long does one customer wait for food?

Throughput
→ How many customers can the restaurant serve per hour?
```

---

## 🎯 Simple Understanding

```text
Latency
= Time taken for ONE request (communication delay)

Throughput
= Number of requests handled in a period of time
```

> **Latency measures speed. Throughput measures capacity.**
