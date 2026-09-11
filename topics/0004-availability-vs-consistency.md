# Availability vs Consistency

## 📖 Simple English Explanation

**Availability** means the system **continues to respond to requests**, even when some parts of the system have problems.

**Consistency** means users see the **correct and up-to-date data** across the system.

In simple words:

> **Availability = System is reachable and responds.**
> **Consistency = Data is correct and synchronized.**

---

## 🤔 Why is it Needed?

In a distributed system, data may exist on multiple servers.

Sometimes, keeping all servers perfectly synchronized can make the system slower or temporarily unavailable.

So we need to decide:

```text
Should we always respond?
        OR
Should we always return the latest data?
```

---

## 🌊 Simple Flow

```text
                Database
               /        \
          Server A     Server B
             ↓            ↓
          Data X        Data X
```

Suppose Server A updates the data:

```text
Server A → Data Y
Server B → Data X
```

Now there is a temporary difference.

### Consistency-focused

```text
Wait for data to synchronize
        ↓
Return latest/correct data
```

### Availability-focused

```text
Return response immediately
        ↓
Data may temporarily be older
```

---

## 💻 Example

Imagine a social media application.

You change your profile name:

```text
Old name → John
New name → David
```

If the system prioritizes **consistency**:

```text
Wait until all relevant servers
have the updated name
        ↓
Return "David"
```

If the system prioritizes **availability**:

```text
Respond immediately
        ↓
One server may temporarily show "John"
while another shows "David"
```

The system remains available, but the data may be temporarily inconsistent.

---

## ⚖️ Availability vs Consistency

| Availability                         | Consistency                                  |
| ------------------------------------ | -------------------------------------------- |
| System continues responding          | Data stays synchronized                      |
| Focuses on system being reachable    | Focuses on correctness/current data          |
| May return older data                | May require waiting for synchronization      |
| Useful when availability is critical | Useful when accurate latest data is critical |

---

## 🔑 Important Idea

In distributed systems, **you often cannot maximize every property at the same time**.

You need to choose based on the application's requirements.

For example:

```text
Bank balance
→ Consistency is very important

Social media likes
→ Temporary inconsistency may be acceptable
```

---

## 🎯 Simple Understanding

```text
Availability
= "Can the system respond?"

Consistency
= "Does the system show the correct/latest data?"
```

> **Availability focuses on keeping the system working. Consistency focuses on keeping the data synchronized.**
