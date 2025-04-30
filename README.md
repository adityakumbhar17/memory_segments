# memory_segments
🔍 Explore the Memory Map of a C Program!
# 🧠 Memory Segments in C Programming

When a C program is executed, memory is divided into several logical segments, each serving a specific purpose. Understanding these segments is crucial for memory management, efficiency, and debugging.

---

## 🔹 1. Text Segment (Code Segment)

**Purpose:**
- Stores executable instructions (machine code).
- Read-only to prevent modification at runtime.
- Shared among processes with the same code.

**Example:**
```c
int sum(int a, int b) {
    return a + b;
}
```

---

## 🔹 2. Initialized Data Segment

**Purpose:**
- Holds global and static variables initialized with non-zero values.
- Memory is allocated during program startup.

**Example:**
```c
int x = 5;          // Global initialized
static int y = 3;   // Static initialized
```

---

## 🔹 3. Uninitialized Data Segment (BSS Segment)

**Purpose:**
- Contains global and static variables that are declared but not initialized.
- Automatically initialized to zero.

**Example:**
```c
int a;             // Global uninitialized
static int b;      // Static uninitialized
```

---

## 🔹 4. Stack Segment 📚

**Purpose:**
- Stores local variables, function parameters, return addresses.
- Follows LIFO (Last In, First Out) principle.
- Grows downward in memory.

**Example:**
```c
void example() {
    int num = 10;   // Stored in stack
}
```

⚠️ **Note:** Stack overflow occurs if too much stack memory is used (e.g., deep recursion).

---

## 🔹 5. Heap Segment 🧺

**Purpose:**
- Used for dynamic memory allocation at runtime.
- Controlled by the programmer using `malloc()`, `calloc()`, `free()`.
- Grows upward in memory.

**Example:**
```c
int *ptr = malloc(5 * sizeof(int)); // Heap allocation
```

⚠️ **Note:** Not freeing heap memory may lead to memory leaks.

---

## 🧭 Memory Layout Diagram (Simplified)

```
        ____________________________
       |        Stack (Top)         |  ⬆️
       |----------------------------|
       |       Heap (grows up)      |
       |----------------------------|
       |  Uninitialized Data (BSS)  |
       |----------------------------|
       |  Initialized Data Segment  |
       |----------------------------|
       |        Text Segment        |  ⬇️
       |____________________________|
```

---

## 🧾 Summary Table

| Segment        | Scope             | Lifetime           | Writable | Purpose                         |
|----------------|-------------------|---------------------|----------|----------------------------------|
| Text           | Global (code)     | Entire program      | ❌       | Stores compiled instructions     |
| Data           | Global/static     | Entire program      | ✅       | Initialized static/global vars   |
| BSS            | Global/static     | Entire program      | ✅       | Uninitialized static/global vars |
| Stack          | Local (function)  | Until function ends | ✅       | Local vars, return addresses     |
| Heap           | Dynamic           | Until manually freed| ✅       | Dynamically allocated memory     |

---

## ✅ Final Notes

- Proper understanding helps prevent memory leaks, stack overflows, and undefined behavior.
- Especially important in embedded systems and systems-level programming.

Happy Coding! 💻✨

