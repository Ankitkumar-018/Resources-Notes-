# Python Variables and Data Types


## PPT Link: [Session 5](https://coding-platform.s3.amazonaws.com/dev/lms/tickets/7fdde5a3-ee25-41ca-ab20-b99aa681441b/zXruHccpyPLVfbZg.pdf)


## Collab Practice Code: [Practice Code](https://coding-platform.s3.amazonaws.com/dev/lms/tickets/270db933-2d40-4082-a2ce-72fc092e4957/qemPHDeUFKC1nn1J.ipynb)


## 1. What You'll Learn in This Section

In this lesson, you'll learn to:

- Explain what a variable is and how Python stores data in memory
- Identify Python's four primitive data types and write values for each
- Apply arithmetic operators, compound assignment shortcuts, and type conversion functions in code
- Manipulate strings using indexing, slicing, built-in methods, and f-strings

## 2. Detailed Explanation

### Variables and the memory model

A **variable** is a name that refers to a memory location where data is stored. Think of computer memory as a long row of labelled containers — each container holds one value, and the variable name is the label on the outside.

**Why it matters**

Every program needs to remember values: a user's age, a product price, a running total. Variables give you a human-readable label for each memory slot so you can refer back to it later.

**Walkthrough**

Imagine a container labelled `a` that holds the value `4`, and another labelled `b` that holds `3`. A third container, `c`, holds the result of adding them.

```python
a = 4       # memory location labelled 'a' stores 4
b = 3       # memory location labelled 'b' stores 3
c = a + b   # result 7 stored in memory location labelled 'c'
```

The `=` sign here is the **assignment operator** — it stores a value into a variable. It does not mean "equal" in the mathematical sense.

Variables are also called **identifiers** — names used to hold and reference data.

**Common mistakes**

- Confusing `=` (assignment) with mathematical equality. `a = 5` means "store 5 in a", not "a equals 5".
- Using a variable before assigning it a value — Python cannot look up a memory slot that has not been created yet.

---

### Dynamic typing — Python infers the type automatically

Python is a **dynamically typed language**: it figures out the data type of a variable from the value you assign, without any declaration from you.

**Why it matters**

In languages like C, C++, and Java, a developer must write `int a;` or `float x;` before using a variable. Python removes this step entirely — you simply write the assignment and Python handles the rest.

**Walkthrough**

```python
a = 5        # Python sees a whole number → a is int
a = "hello"  # Python sees text → a is now str
```

The type of `a` changed automatically. No extra code was needed.

**Common mistakes**

- Assuming a variable's type stays fixed. Python is dynamically typed, so the same variable can hold a string on one line and an integer on the next.
- This flexibility can cause surprising bugs: always be aware of what type a variable currently holds.

---

### The four primitive data types

Python has four main **primitive data types** — the basic building blocks for all values.

**Why it matters**

Choosing the right type matters: storing a price as a string instead of a number prevents arithmetic; storing `True`/`False` as `1`/`0` loses clarity. Knowing which type fits which job keeps code correct.

**Walkthrough**

| Type | What it holds | Example values |
|------|---------------|----------------|
| `int` | Whole numbers, positive or negative, no decimal point | `5`, `7`, `-12`, `0` |
| `float` | Numbers with a decimal point — financial data, measurements | `1.0`, `12.3`, `-13.5` |
| `str` | A sequence of characters — names, labels, text | `"Python"`, `"data science"` |
| `bool` | A logical yes/no value — only `True` or `False` | `True`, `False` |

Quick decision rule:
- Number with no decimal → `int`
- Number with a decimal → `float`
- Text / characters → `str`
- Yes/no condition → `bool`

Python also supports **complex numbers** — numbers with a real part and an imaginary part. The imaginary unit is written as `j`.

```python
a = 2 + 5j   # real part = 2, imaginary part = 5
b = 3 - 2j
```

The key arithmetic rule: **j² = −1**. When adding complex numbers, real parts combine with real parts and imaginary parts combine with imaginary parts.

**Common mistakes**

- Writing `True` or `False` in lowercase (`true`, `false`) — Python treats them as undefined variable names, not booleans.
- Confusing `int` and `float`: `5` is an `int` but `5.0` is a `float`. They behave differently in division.

---

### Naming rules for variables

A **naming rule** is a syntax requirement Python enforces on every variable name. Breaking any rule causes a `SyntaxError`.

**Why it matters**

Invalid names stop the program from running at all. Good naming conventions also make code readable to anyone who opens the file later — including a junior developer joining the team months after you wrote it.

**Walkthrough**

Rules that must be followed:

1. Start with a letter or underscore — never a digit.
2. No spaces — use an underscore instead.
3. No special symbols — only letters, digits, and `_` are allowed.
4. Lowercase is conventional (not mandatory).
5. Use descriptive names that communicate what the variable holds.

```python
# Valid names
roll_number = 42
user_id = "U001"
employee_name = "analyst"
year = 2026

# Invalid names — all raise SyntaxError
# 1employee_name = "analyst"   → starts with digit
# employee name = "analyst"    → contains space
# $price = 5.5                 → contains special symbol
```

**Common mistakes**

- Starting a variable name with a digit (`1abc`) — the most common beginner slip.
- Using spaces in names (`first name`) — always replace with an underscore (`first_name`).

---

### Assignment, chained assignment, and multiple assignment

**Assignment** stores a value in a variable using `=`. Python supports two useful shorthand forms.

**Why it matters**

When initialising several variables at once, chained and multiple assignment reduce boilerplate and make intent clearer.

**Walkthrough**

Standard assignment:

```python
a = 5
b = 3
c = a + b   # evaluates to 8, stores in c
```

**Chained assignment** sets multiple variables to the same value in a single statement.

```python
x = y = z = 50   # all three variables are assigned the value 50
```

**Multiple assignment** maps each variable on the left to the matching value on the right.

```python
a, b, c = 5, 10, 50   # a=5, b=10, c=50
```

**Common mistakes**

- Mismatching the count of variables and values in multiple assignment. `a, b = 1, 2, 3` will cause an error because the numbers of names and values do not match.

---

### Arithmetic operators

Python provides seven **arithmetic operators** for numerical calculations.

**Why it matters**

From splitting a bill to calculating a discount, arithmetic is the backbone of almost every program. Knowing all seven operators — especially the less obvious ones — prevents off-by-one errors and guesswork.

**Walkthrough**

| Operator | Meaning | Example | Result |
|----------|---------|---------|--------|
| `+` | Addition | `10 + 5` | `15` |
| `-` | Subtraction | `20 - 5` | `15` |
| `*` | Multiplication | `4 * 3` | `12` |
| `/` | Division | `10 / 3` | `3.333…` |
| `%` | Modulo (remainder) | `10 % 3` | `1` |
| `**` | Exponentiation | `5 ** 2` | `25` |
| `//` | Floor division | `49 // 2` | `24` |

**Modulo** (`%`) gives the remainder after division. `10 % 3` → quotient is 3, remainder is `1`. `50 % 4` → remainder is `2`.

**Floor division** (`//`) returns the lower integer of the true result. `49 / 2 = 24.5`, and the floor of `24.5` is `24`, so `49 // 2 = 24`.

**Exponentiation** uses two asterisks: `5 ** 2 = 25`; `50 ** 2 = 2500`.

**Common mistakes**

- Using the wrong symbol for exponentiation. Python uses `**` (two asterisks), not any other symbol.

---

### Compound assignment operators

**Compound assignment operators** are shortcuts that combine an arithmetic operation with assignment in one step.

**Why it matters**

Updating a variable in place is extremely common — incrementing a counter, reducing a balance. Compound operators make this concise and readable.

**Walkthrough**

```python
a = 5
a += 4    # same as a = a + 4  → a is now 9

a = 5
a -= 4    # a = a - 4 → 1

a = 5
a *= 4    # a = a * 4 → 20

a = 5
a /= 4    # a = a / 4 → 1.25

a = 5
a %= 4    # a = a % 4 → 1

a = 50
a **= 2   # a = a ** 2 → 2500

a = 49
a //= 2   # a = a // 2 → 24
```

A subtle distinction: `a = -2` stores the value −2 in `a`. `a -= 2` means `a = a - 2`; if `a` was −2 before, the result is −4.

**Common mistakes**

- Confusing `a = -2` (storing a negative value) with `a -= 2` (subtracting 2 from whatever `a` currently holds).

---

### The `type()` function

The built-in **`type()` function** returns the data type (class) of any variable.

**Why it matters**

When debugging unexpected behaviour, the type is the first thing to check. It immediately reveals whether a value is stored as a string or as a numeric type.

**Walkthrough**

```python
a = 5
b = 3.14
c = "hello"
d = 4 + 3j

print(type(a))   # <class 'int'>
print(type(b))   # <class 'float'>
print(type(c))   # <class 'str'>
print(type(d))   # <class 'complex'>
```

This is like inspecting the material a container is made of — glass, ceramic, or plastic — rather than just its label.

**Common mistakes**

- Expecting `type()` to return a plain word like `"int"`. It returns a class object; the readable part is inside the angle brackets in the output.

---

### Type conversion

**Type conversion** is the process of explicitly changing a value from one data type to another using built-in functions.

**Why it matters**

Data often arrives as strings — from user input, files, or databases. Arithmetic on strings fails with a `TypeError`. Converting to a numeric type first is essential.

**Walkthrough**

The diagram below shows the three conversion directions most commonly used.

```mermaid
flowchart LR
    StringVal["String value\ne.g. '375'"] -->|int()| IntVal["Integer\n375"]
    StringVal -->|float()| FloatVal["Float\n375.0"]
    IntVal -->|float()| FloatVal
    IntVal -->|str()| StringVal2["String\n'5'"]
    FloatVal -->|int()| IntVal2["Integer\n(decimal dropped)\n2"]
```

Key behaviours:

| Function | What it does | Example |
|----------|-------------|---------|
| `int(x)` | Drops the decimal part | `int(2.8)` → `2` |
| `float(x)` | Adds a decimal point | `float(2)` → `2.0` |
| `str(x)` | Converts number to text | `str(10)` → `"10"` |

A practical example — a data analyst needs to calculate a discounted price where the original price is stored as a string:

```python
price = "5.5"    # string — arithmetic will fail
amount = "2"     # string

num_price = float(price)          # 5.5
num_amount = int(amount)          # 2
total = num_price - num_amount    # 3.5
```

Note: using `+` on two strings does not add numbers — it **concatenates** them. `"5.5" + "2"` → `"5.52"`, not `7.5`.

**Common mistakes**

- Trying to multiply or subtract strings without converting first. Python raises a `TypeError`. Always convert to a numeric type first.

---

### String indexing and slicing

A **string** in Python is an ordered sequence of characters. Each character has an integer **index** starting at `0`.

**Why it matters**

Real data often needs slicing. Pulling a first name out of a full name, or extracting initials, are typical data-cleaning tasks.

**Walkthrough**

```text
"Python."
 P  y  t  h  o  n  .
 0  1  2  3  4  5  6
```

**Slicing** uses the syntax `string[start:end]`. The start index is included; the end index is excluded.

```python
message = "Python."

message[0:4]   # indices 0, 1, 2, 3 → "Pyth"
message[2:5]   # indices 2, 3, 4   → "tho"
```

**Negative indices** count from the end of the string. `-1` is the last character, `-3` is third from the end.

```python
name = "pratheem"

name[-3:]   # last 3 characters → "eem"
name[-5:]   # last 5 characters → "theem"
```

Omitting the end index means "go to the end of the string".

**Common mistakes**

- Off-by-one with slicing: `message[0:4]` gives 4 characters (indices 0–3), not 5. The end index is always exclusive.
- Forgetting that string indices start at `0`, not `1`.

---

### String concatenation and f-strings

**String concatenation** joins two or more strings using the `+` operator. **F-strings** embed variable values directly inside a string at runtime.

**Why it matters**

Building dynamic output messages — "Welcome, [name], your balance is [amount]" — is something every program does. F-strings are the clearest, most readable way to achieve this.

**Walkthrough**

Concatenation with `+`:

```python
first = "data"
second = "science"

full = first + " " + second   # "data science"
# Without the space: first + second → "datascience"
```

An **f-string** starts with `f` before the opening quote. Anything inside `{}` is replaced by the variable's value at runtime.

```python
customer_role = "analyst"
roll_number = 50
balance = 5000.5

print(f"Customer role is {customer_role}, ID: {roll_number}, balance: {balance}")
# Output: Customer role is analyst, ID: 50, balance: 5000.5
```

Without the `f` prefix, `customer_role` prints as the literal text `customer_role`, not its value.

**Common mistakes**

- Forgetting the `f` prefix — the curly braces are printed as-is instead of being replaced by values.

---

### String methods

**String methods** are built-in functions called on a string using dot notation: `string.method()`. They return a modified copy — they do not change the original.

**Why it matters**

Real data is messy: names have extra spaces, capitalisation is inconsistent, parts need replacing. String methods are the primary tool for cleaning and standardising text data.

**Walkthrough**

| Method | What it does | Example |
|--------|-------------|---------|
| `strip()` | Removes whitespace from both ends | `"  hello  ".strip()` → `"hello"` |
| `lower()` | Converts all characters to lowercase | `"HELLO".lower()` → `"hello"` |
| `upper()` | Converts all characters to uppercase | `"hello".upper()` → `"HELLO"` |
| `replace(old, new)` | Replaces every occurrence of `old` with `new` | `"new daily".replace("daily", "york")` → `"new york"` |

`strip()` only removes whitespace at the beginning and end — it does not touch spaces in the middle.

**Method chaining** applies multiple methods in sequence, left to right:

```python
word = "  PRODUCT  "
processed = word.strip().lower()
# strip() removes spaces → "PRODUCT"
# lower() lowercases    → "product"
```

A backend engineer cleaning customer data might chain `strip()` and `lower()` together to normalise names before storing them in a database.

**Common mistakes**

- Expecting `strip()` to remove internal spaces. It only trims the edges — spaces in the middle of the string are not affected.
- Forgetting that these methods return a new string. Writing `name.strip()` without capturing the result leaves `name` unchanged.

---

### Running code in Google Colab

**Google Colab** (also called Google Notebook) is the tool used to run all the Python code in this lesson. It runs in your browser — no installation needed.

**Why it matters**

You need somewhere to write and execute Python. Google Colab gives you a free, ready-to-use environment.

**Walkthrough**

Three actions cover everything you need to get started:

1. Open a new notebook: go to Google Colab and click **New notebook**.
2. Add a code cell: click **+ Code**.
3. Run a cell: press **Shift+Enter** or click the run button next to the cell.

**Common mistakes**

- Forgetting to run a cell after writing code — the output only appears after you execute the cell.

---

### Putting it all together — a worked example

This section combines variables, string methods, type conversion, and arithmetic in a single realistic task.

**Why it matters**

Seeing how these concepts work together shows why each one exists. A real-world record often has messy text and mixed data types; you need every tool from this lesson to handle it cleanly.

**Walkthrough**

A data analyst receives a customer record. The name has extra whitespace, the case is inconsistent, and the price is stored as a string. They need to clean the name and calculate the discounted price.

```python
text = "  SR DATA ANALYST  "
price = "250"           # stored as a string
discount_rate = 0.15    # 15 percent

# Clean the name
name1 = text.strip()          # "SR DATA ANALYST"
name2 = name1.lower()         # "sr data analyst"

# Price calculation — convert string to number first
num_price = int(price)                        # 250
discount_amount = discount_rate * num_price   # 0.15 * 250 = 37.5
total_price = num_price - discount_amount     # 212.5
```

**Common mistakes**

- Skipping the `int(price)` conversion. Without it, `discount_rate * price` raises a `TypeError` because Python cannot multiply a float by a string.

## 3. Key Takeaways

- A variable is a labelled memory location. Python infers its type automatically from the assigned value — no explicit declaration needed.
- The four primitive types are `int`, `float`, `str`, and `bool`. Choose the type that matches the nature of the data (numeric, textual, or logical).
- All seven arithmetic operators (`+`, `-`, `*`, `/`, `%`, `**`, `//`) and all compound assignment shortcuts (`+=`, `-=`, etc.) let you compute and update values concisely.
- Use `type()` to inspect a variable's type and `int()`, `float()`, or `str()` to convert between types before performing arithmetic on string-held numbers.
- String tools — indexing (`[start:end]`), negative indices, `strip()`, `lower()`, `upper()`, `replace()`, method chaining, and f-strings — are the core toolkit for reading, cleaning, and formatting text data.

**Mental model:** Think of variables as labelled jars — each jar holds one value, the label is the variable name, and Python figures out the type by looking at the contents.