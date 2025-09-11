---
title: "Linear Algebra: Vectors and Vector Spaces"
---
# Vectors and Vector Spaces

## 1. Vectors

### Definition
A **vector** is a mathematical object that has both magnitude and direction. Vectors are often represented as ordered lists of numbers, called components, in a coordinate system.

For example, a vector in $\mathbb{R}^2$ (2-dimensional space) is written as:
$$
\mathbf{v} = \begin{bmatrix} v_1 \\ v_2 \end{bmatrix}
$$
and in $\mathbb{R}^3$ (3-dimensional space) as:
$$
\mathbf{v} = \begin{bmatrix} v_1 \\ v_2 \\ v_3 \end{bmatrix}.
$$

### Vector Notation
- **Column vector**: $\mathbf{v} = \begin{bmatrix} v_1 \\ v_2 \\ \cdots \\ v_n \end{bmatrix}$
- **Row vector**: $\mathbf{v} = \begin{bmatrix} v_1 & v_2 & \cdots & v_n \end{bmatrix}$

### Operations on Vectors
1. **Addition**: If $\mathbf{u} = \begin{bmatrix} u_1 \\ u_2 \end{bmatrix}$ and $\mathbf{v} = \begin{bmatrix} v_1 \\ v_2 \end{bmatrix}$, then:
   $$
   \mathbf{u} + \mathbf{v} = \begin{bmatrix} u_1 + v_1 \\ u_2 + v_2 \end{bmatrix}.
   $$

2. **Scalar Multiplication**: If $c$ is a scalar and $\mathbf{v} = \begin{bmatrix} v_1 \\ v_2 \end{bmatrix}$, then:
   $$
   c\mathbf{v} = \begin{bmatrix} c v_1 \\ c v_2 \end{bmatrix}.
   $$

3. **Dot Product**: The dot product of two vectors $\mathbf{u} = \begin{bmatrix} u_1 \\ u_2 \end{bmatrix}$ and $\mathbf{v} = \begin{bmatrix} v_1 \\ v_2 \end{bmatrix}$ is:
   $$
   \mathbf{u} \cdot \mathbf{v} = u_1 v_1 + u_2 v_2.
   $$

4. **Norm (Magnitude)**: The norm of a vector $\mathbf{v} = \begin{bmatrix} v_1 \\ v_2 \end{bmatrix}$ is:
   $$
   \|\mathbf{v}\| = \sqrt{v_1^2 + v_2^2}.
   $$

---

## 2. Vector Spaces

### Definition
A **vector space** is a set of vectors, along with two operations (vector addition and scalar multiplication), that satisfies the following **axioms**.

### Axioms of Vector Spaces
Let $\mathbf{u}, \mathbf{v}, \mathbf{w}$ be vectors in a vector space $V$, and let $c, d$ be scalars. The following properties must hold:

1. **Closure under Addition**: $\mathbf{u} + \mathbf{v} \in V$.
2. **Commutativity of Addition**: $\mathbf{u} + \mathbf{v} = \mathbf{v} + \mathbf{u}$.
3. **Associativity of Addition**: $(\mathbf{u} + \mathbf{v}) + \mathbf{w} = \mathbf{u} + (\mathbf{v} + \mathbf{w})$.
4. **Existence of Zero Vector**: There exists a vector $\mathbf{0} \in V$ such that $\mathbf{u} + \mathbf{0} = \mathbf{u}$.
5. **Existence of Additive Inverses**: For every $\mathbf{u} \in V$, there exists $-\mathbf{u} \in V$ such that $\mathbf{u} + (-\mathbf{u}) = \mathbf{0}$.
6. **Closure under Scalar Multiplication**: $c\mathbf{u} \in V$.
7. **Distributive Property (Scalars)**: $c(\mathbf{u} + \mathbf{v}) = c\mathbf{u} + c\mathbf{v}$.
8. **Distributive Property (Vectors)**: $(c + d)\mathbf{u} = c\mathbf{u} + d\mathbf{u}$.
9. **Associativity of Scalar Multiplication**: $c(d\mathbf{u}) = (cd)\mathbf{u}$.
10. **Multiplicative Identity**: $1\mathbf{u} = \mathbf{u}$.

### Examples of Vector Spaces
1. $\mathbb{R}^n$: The set of all $n$-dimensional vectors with real components.
2. The set of all $m \times n$ matrices.
3. The set of all polynomials of degree $\leq n$.
4. The set of all continuous functions.

---

## 3. Subspaces

### Definition
A **subspace** is a subset $W$ of a vector space $V$ that is itself a vector space under the same operations of addition and scalar multiplication.

### Conditions for a Subspace
A subset $W \subseteq V$ is a subspace if:
1. $\mathbf{0} \in W$ (contains the zero vector),
2. $W$ is closed under addition: $\mathbf{u}, \mathbf{v} \in W \implies \mathbf{u} + \mathbf{v} \in W$,
3. $W$ is closed under scalar multiplication: $c\mathbf{u} \in W$ for all $c \in \mathbb{R}$ and $\mathbf{u} \in W$.

### Examples of Subspaces
1. The set of all vectors in $\mathbb{R}^3$ lying on a plane through the origin.
2. The set of all solutions to a homogeneous system of linear equations.

---

## 4. Span and Linear Independence

### Span
The **span** of a set of vectors $\{\mathbf{v}_1, \mathbf{v}_2, \dots, \mathbf{v}_k\}$ is the set of all linear combinations of these vectors:
$$
\text{Span}(\{\mathbf{v}_1, \mathbf{v}_2, \dots, \mathbf{v}_k\}) = \{c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_k\mathbf{v}_k \mid c_1, c_2, \dots, c_k \in \mathbb{R}\}.
$$

### Linear Independence
A set of vectors $\{\mathbf{v}_1, \mathbf{v}_2, \dots, \mathbf{v}_k\}$ is **linearly independent** if the only solution to:
$$
c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_k\mathbf{v}_k = \mathbf{0}
$$
is $c_1 = c_2 = \cdots = c_k = 0$.

If there exists a non-trivial solution (i.e., not all $c_i$ are zero), the vectors are **linearly dependent**.

---

## 5. Basis and Dimension

### Basis
A **basis** of a vector space $V$ is a set of vectors $\{\mathbf{v}_1, \mathbf{v}_2, \dots, \mathbf{v}_n\}$ that:
1. Are linearly independent.
2. Span the entire vector space $V$.

### Dimension
The **dimension** of a vector space $V$ is the number of vectors in a basis for $V$.

For example:
- The dimension of $\mathbb{R}^2$ is $2$.
- The dimension of $\mathbb{R}^3$ is $3$.
