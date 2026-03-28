# Family Relationships in Prolog

## 📌 Project Overview

This project demonstrates how to represent and query family relationships using **Prolog**, a logic programming language. It defines basic family facts (like parent-child relationships) and builds more complex relationships such as siblings, grandparents, ancestors, and descendants using logical rules.

The program showcases how knowledge representation and inference work in Prolog.

---

## 👤 Author Details

* **Name:** Shivam Thenua
* **Registration No.:** (25BAI10319)

---

## 📂 Project Structure

The project consists of a single Prolog file containing:

* **Facts** → Basic relationships and gender definitions
* **Rules** → Logical definitions to derive new relationships

---

## 📊 Defined Facts

The following base facts are included:

### Parent Relationships

* Tom is the parent of Bob and Liz
* Bob is the parent of Ann and Pat
* Pat is the parent of Jim

### Gender Information

* Males: Tom, Bob, Pat, Jim
* Females: Liz, Ann

---

## ⚙️ Rules Implemented

### 1. Father

Defines a father as a male parent.

```prolog
father(X, Y) :- parent(X, Y), male(X).
```

### 2. Mother

Defines a mother as a female parent.

```prolog
mother(X, Y) :- parent(X, Y), female(X).
```

### 3. Grandparent

Defines a grandparent through an intermediate parent.

```prolog
grandparent(X, Y) :- parent(X, Z), parent(Z, Y).
```

### 4. Sibling

Defines siblings as individuals sharing the same parent.

```prolog
sibling(X, Y) :- parent(Z, X), parent(Z, Y), X \= Y.
```

### 5. Ancestor

Defines ancestors recursively.

```prolog
ancestor(X, Y) :- parent(X, Y).
ancestor(X, Y) :- parent(X, Z), ancestor(Z, Y).
```

### 6. Descendant

Defines descendants using the ancestor relationship.

```prolog
descendant(X, Y) :- ancestor(Y, X).
```

---

## ▶️ Sample Queries

You can run the following queries in a Prolog interpreter:

* Find Bob’s children:

```prolog
?- parent(bob, X).
```

* Find Tom’s grandchildren:

```prolog
?- grandparent(tom, X).
```

* Find siblings of Ann:

```prolog
?- sibling(ann, X).
```

* Check if Tom is an ancestor of Jim:

```prolog
?- ancestor(tom, jim).
```

* Find descendants of Bob:

```prolog
?- descendant(X, bob).
```

---

## 🎯 Learning Outcomes

* Understanding of **logic programming concepts**
* Use of **facts and rules in Prolog**
* Implementation of **recursive relationships**
* Querying knowledge bases effectively

---

## 🔗 Tools Required

* Prolog Interpreter (e.g., SWI-Prolog)

---

## 📌 Conclusion

This project provides a simple yet powerful demonstration of how family relationships can be modeled using logical rules. It highlights the strength of Prolog in handling relational data and recursive queries.

---
