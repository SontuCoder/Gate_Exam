````md
# 🔢 Boolean Algebra & Logic Gates

---

# 🔵 Bubble Logic

## NAND Gate

> [!NOTE]
> A **NAND gate** can be represented as a **pre-bubbled OR gate** using bubble logic and De Morgan's theorem.

```text
NAND = Pre-bubbled + OR
```

\[
(A \cdot B)' = A' + B'
\]

---

## NOR Gate

> [!NOTE]
> A **NOR gate** can be represented as a **pre-bubbled AND gate** using bubble logic and De Morgan's theorem.

```text
NOR = Pre-bubbled + AND
```

\[
(A + B)' = A'B'
\]

---

# 📌 Canonical Form

> [!IMPORTANT]
> In a **Canonical Form**, each term of the Boolean expression contains **all input variables**, either in **true or complemented form**.

### Example

\[
F(A,B,C)=A'B'C'+A'BC+ABC
\]

Each term contains all three variables:

```text
A, B, C
```

### Canonical Forms

- **Canonical SOP** → Sum of Minterms
- **Canonical POS** → Product of Maxterms

---

# 📌 Standard Form

> [!NOTE]
> A Boolean expression is in **Standard Form** when **at least one term may not contain all variables**.

### Example

\[
F(A,B,C)=A'+A'C+ABC
\]

Here:

```text
A'      → Missing B and C
A'C     → Missing B
ABC     → Contains all variables
```

Therefore, this is a **Standard SOP form**, but **not a Canonical SOP form**.

---

# 📚 Boolean Laws

---

## 1️⃣ Distributive Law

\[
\boxed{(A+B)(A+C)=A+BC}
\]

Also:

\[
\boxed{A+BC=(A+B)(A+C)}
\]

---

## 2️⃣ Consensus Theorem (Redundancy)

### SOP Form

\[
\boxed{AB+A'C+BC=AB+A'C}
\]

Here:

```text
BC = Consensus Term
```

So, `BC` is redundant and can be removed.

### POS Form

\[
\boxed{(A+B)(A'+C)(B+C)=(A+B)(A'+C)}
\]

Here:

```text
(B + C) = Redundant / Consensus Term
```

---

## 3️⃣ Absorption Law

\[
\boxed{A+AB=A}
\]

\[
\boxed{A(A+B)=A}
\]

### Memory Trick

```text
A + AB = A

A(A + B) = A
```

> [!TIP]
> The simpler variable `A` **absorbs** the larger expression containing `A`.

---

## 4️⃣ De Morgan's Laws

### Complement of OR

\[
\boxed{(A+B+C)'=A'B'C'}
\]

### Complement of AND

\[
\boxed{(ABC)'=A'+B'+C'}
\]

### Easy Rule

```text
Complement everything
+
Change OR ↔ AND
```

---

# 🔄 Duality Principle

> [!IMPORTANT]
> **Duality** is often used for the **indirect proof of Boolean expressions**.

To obtain the **dual** of an expression:

```text
AND (·)  ↔ OR (+)
0        ↔ 1
```

### Important

> **Variables and their complements remain unchanged.**

### Example

\[
F=AB+CD
\]

Its dual:

\[
\boxed{F_d=(A+B)(C+D)}
\]

---

# 🔄 Complement of a Boolean Expression

To find the complement:

```text
AND ↔ OR
0 ↔ 1
```

and replace each variable with its complement.

### Example

\[
F=AB+CD
\]

Then:

\[
F'=(AB+CD)'
\]

Using De Morgan's Law:

\[
\boxed{F'=(A'+B')(C'+D')}
\]

---

# 🧠 Duality vs Complementation

| Operation | AND ↔ OR | 0 ↔ 1 | Variables Complemented? |
|---|:---:|:---:|:---:|
| **Dual** | ✅ | ✅ | ❌ |
| **Complement** | ✅ | ✅ | ✅ |

### Example

\[
F=AB+CD
\]

```text
Dual:
Fd = (A+B)(C+D)

Complement:
F' = (A'+B')(C'+D')
```

---

# 🔁 Dual Effect

| Original | Dual |
|---|---|
| `1` | `0` |
| `0` | `1` |
| `+ve` | `-ve` |
| `-ve` | `+ve` |
| `·` | `+` |
| `+` | `·` |
| AND | OR |
| OR | AND |
| NAND | NOR |
| NOR | NAND |
| XOR | XNOR |
| XNOR | XOR |
| NOT | NOT |
| Buffer | Buffer |

> [!NOTE]
> For **Duality**, inversion/complement symbols on variables remain unchanged.

---

# ⭐ Self-Dual Function

> [!IMPORTANT]
> A Boolean function is called **Self-Dual** if:

\[
\boxed{F=F_d}
\]

That means the function is equal to its own dual.

---

## 📌 Properties of Self-Dual Functions

### 1. Equal Number of Minterms and Maxterms

For a Boolean function with `n` variables:

```text
Number of input combinations = 2ⁿ
```

For a self-dual function:

\[
\boxed{\text{No. of Minterms}=\text{No. of Maxterms}=2^{n-1}}
\]

---

### 2. Total Number of Self-Dual Boolean Functions

For `n` variables:

\[
\boxed{2^{2^{n-1}}}
\]

### Comparison

| Variables | Total Boolean Functions | Self-Dual Functions |
|:---:|:---:|:---:|
| 1 | \(2^{2^1}=4\) | \(2^{2^0}=2\) |
| 2 | \(2^{2^2}=16\) | \(2^{2^1}=4\) |
| 3 | \(2^{2^3}=256\) | \(2^{2^2}=16\) |

---

# 🔢 Number of Boolean Functions with r Minterms

For `n` variables:

```text
Total possible input combinations = 2ⁿ
```

If the function contains exactly `r` minterms:

\[
\boxed{
{2^n \choose r}
=
\frac{(2^n)!}{r!\left((2^n-r)!\right)}
}
\]

### Meaning

We select `r` output combinations from the total `2ⁿ` possible input combinations.

---

# 🎯 GATE CSE Quick Revision

> [!SUCCESS]
>
> ### Canonical Form
> - Every term contains **all variables**
> - SOP → Minterms
> - POS → Maxterms
>
> ### Standard Form
> - Terms may **not contain all variables**
>
> ### Consensus Theorem
>
> \[
> AB+A'C+BC=AB+A'C
> \]
>
> ### Absorption
>
> \[
> A+AB=A
> \]
>
> \[
> A(A+B)=A
> \]
>
> ### De Morgan's Law
>
> \[
> (A+B)'=A'B'
> \]
>
> \[
> (AB)'=A'+B'
> \]
>
> ### Duality
>
> ```text
> AND ↔ OR
> 0   ↔ 1
> ```
>
> ### Self-Dual Function
>
> \[
> F=F_d
> \]
>
> \[
> \text{Total Self-Dual Functions}=2^{2^{n-1}}
> \]
>
> ### Boolean Functions with r Minterms
>
> \[
> {2^n \choose r}
> \]
````
