---
{"publish":true,"title":"chapter 2","description":"一句话概述内容，方便 SEO 和分享预览","created":"2026-04-15","modified":"2026-04-15T20:33:49.997+08:00","cssclasses":""}
---



# Chapter 2

# Convex sets

# 2.1 Affine and convex sets

# 2.1.1 Lines and line segments

Suppose $x _ { 1 } \neq x _ { 2 }$ are two points in $\mathbf { R } ^ { n }$ . Points of the form

$$
y = \theta x _ {1} + (1 - \theta) x _ {2},
$$

where $\theta \in \mathbf { R }$ , form the line passing through $x _ { 1 }$ and $x _ { 2 }$ . The parameter value $\theta = 0$ corresponds to $y = x _ { 2 }$ , and the parameter value $\theta = 1$ corresponds to $y = x _ { 1 }$ . Values of the parameter $\theta$ between 0 and 1 correspond to the (closed) line segment between $x _ { 1 }$ and $x _ { 2 }$ .

Expressing $y$ in the form

$$
y = x _ {2} + \theta \left(x _ {1} - x _ {2}\right)
$$

gives another interpretation: $y$ is the sum of the base point $x _ { 2 }$ (corresponding to $\theta = 0$ ) and the direction $x _ { 1 } - x _ { 2 }$ (which points from $x _ { 2 }$ to $x _ { 1 }$ ) scaled by the parameter $\theta$ . Thus, $\theta$ gives the fraction of the way from $x _ { 2 }$ to $x _ { 1 }$ where $y$ lies. As $\theta$ increases from 0 to 1, the point $y$ moves from $x _ { 2 }$ to $x _ { 1 }$ ; for $\theta > 1$ , the point $y$ lies on the line beyond $x _ { 1 }$ . This is illustrated in figure 2.1.

# 2.1.2 Affine sets

A set $C \subseteq \mathbf { R } ^ { n }$ is affine if the line through any two distinct points in $C$ lies in $C$ , i.e., if for any $x _ { 1 } , x _ { 2 } \in C$ and $\theta \in \mathbf { R }$ , we have $\theta x _ { 1 } + ( 1 - \theta ) x _ { 2 } \in C$ . In other words, $C$ contains the linear combination of any two points in $C$ , provided the coefficients in the linear combination sum to one.

This idea can be generalized to more than two points. We refer to a point of the form $\theta _ { 1 } x _ { 1 } + \cdot \cdot \cdot + \theta _ { k } x _ { k }$ , where $\theta _ { 1 } + \cdot \cdot \cdot + \theta _ { k } = 1$ , as an affine combination of the points $x _ { 1 }$ , . . . , $x _ { k }$ . Using induction from the definition of affine set (i.e., that it contains every affine combination of two points in it), it can be shown that

![](数学书/凸优化/images/00a5ff06617b4fc5cf57e13b3123b2736b853ba4e38f65283cb7e1a7c52491dc.jpg)  
Figure 2.1 The line passing through $x _ { 1 }$ and $x _ { 2 }$ is described parametrically by $\theta x _ { 1 } + ( 1 - \theta ) x _ { 2 }$ , where $\theta$ varies over $\mathbf { R }$ . The line segment between $x _ { 1 }$ and $x _ { 2 }$ , which corresponds to $\theta$ between 0 and 1, is shown darker.

an affine set contains every affine combination of its points: If $C$ is an affine set, $x _ { 1 } , \ldots , x _ { k } \in C$ , and $\theta _ { 1 } + \cdot \cdot \cdot + \theta _ { k } = 1$ , then the point $\theta _ { 1 } x _ { 1 } + \cdot \cdot \cdot + \theta _ { k } x _ { k }$ also belongs to $C$ .

If $C$ is an affine set and $x _ { 0 } \in C$ , then the set

$$
V = C - x _ {0} = \{x - x _ {0} \mid x \in C \}
$$

is a subspace, i.e., closed under sums and scalar multiplication. To see this, suppose $v _ { 1 } , \ v _ { 2 } \in V$ and $\alpha , ~ \beta \in \mathbf { R }$ . Then we have $v _ { 1 } + x _ { 0 } \in C$ and $v _ { 2 } + x _ { 0 } \in C$ , and so

$$
\alpha v _ {1} + \beta v _ {2} + x _ {0} = \alpha \left(v _ {1} + x _ {0}\right) + \beta \left(v _ {2} + x _ {0}\right) + (1 - \alpha - \beta) x _ {0} \in C,
$$

since $C$ is affine, and $\alpha + \beta + ( 1 - \alpha - \beta ) = 1$ . We conclude that $\alpha v _ { 1 } + \beta v _ { 2 } \in V$ , since $\alpha v _ { 1 } + \beta v _ { 2 } + x _ { 0 } \in C$ .

Thus, the affine set $C$ can be expressed as

$$
C = V + x _ {0} = \{v + x _ {0} \mid v \in V \},
$$

i.e., as a subspace plus an offset. The subspace $V$ associated with the affine set $C$ does not depend on the choice of $x _ { 0 }$ , so $x _ { 0 }$ can be chosen as any point in $C$ . We define the dimension of an affine set $C$ as the dimension of the subspace $V = C - x _ { 0 }$ , where $x _ { 0 }$ is any element of $C$ .

Example 2.1 Solution set of linear equations. The solution set of a system of linear equations, $C = \{ x \mid A x = b \}$ , where $A \in \mathbf { R } ^ { m \times n }$ and $b \in \mathbf { R } ^ { \prime \prime \iota }$ , is an affine set. To show this, suppose $x _ { 1 } , \ x _ { 2 } \in C$ , i.e., $A x _ { 1 } = b$ , $A x _ { 2 } = b$ . Then for any $\theta$ , we have

$$
\begin{array}{l} A \left(\theta x _ {1} + (1 - \theta) x _ {2}\right) = \theta A x _ {1} + (1 - \theta) A x _ {2} \\ = \theta b + (1 - \theta) b \\ = b, \\ \end{array}
$$

which shows that the affine combination $\theta x _ { 1 } + ( 1 - \theta ) x _ { 2 }$ is also in $C$ . The subspace associated with the affine set $C$ is the nullspace of $A$ .

We also have a converse: every affine set can be expressed as the solution set of a system of linear equations.

The set of all affine combinations of points in some set $C \subseteq \mathbf { R } ^ { n }$ is called the affine hull of $C$ , and denoted aff $C$ :

$$
\mathbf {a f f} C = \left\{\theta_ {1} x _ {1} + \dots + \theta_ {k} x _ {k} \mid x _ {1}, \dots , x _ {k} \in C, \theta_ {1} + \dots + \theta_ {k} = 1 \right\}.
$$

The affine hull is the smallest affine set that contains $C$ , in the following sense: if $S$ is any affine set with $C \subseteq S$ , then aff $C \subseteq S$ .

# 2.1.3 Affine dimension and relative interior

We define the affine dimension of a set $C$ as the dimension of its affine hull. Affine dimension is useful in the context of convex analysis and optimization, but is not always consistent with other definitions of dimension. As an example consider the unit circle in $\mathbf { R } ^ { 2 }$ , i.e., $\{ x \in \mathbf { R } ^ { \ Q } \mid x _ { 1 } ^ { 2 } + x _ { 2 } ^ { 2 } = 1 \}$ . Its affine hull is all of $\mathbf { R } ^ { 2 }$ , so its affine dimension is two. By most definitions of dimension, however, the unit circle in $\mathbf { R } ^ { 2 }$ has dimension one.

If the affine dimension of a set $C \subseteq \mathbf { R } ^ { n }$ is less than $n$ , then the set lies in the affine set aff $C \neq \mathbf { R } ^ { n }$ . We define the relative interior of the set $C$ , denoted relint $C$ , as its interior relative to aff $C$ :

$$
\operatorname {r e l i n t} C = \{x \in C \mid B (x, r) \cap \operatorname {a f f} C \subseteq C \text {f o r s o m e} r > 0 \},
$$

where $B ( x , r ) = \{ y \mid \| y - x \| \leq r \}$ , the ball of radius $r$ and center $x$ in the norm $\| \cdot \|$ . (Here $\| \cdot \|$ is any norm; all norms define the same relative interior.) We can then define the relative boundary of a set $C$ as $\mathbf { c l } C \ \backslash \ \mathbf { r e l i n t } C$ , where $\mathbf { c l } { \boldsymbol { C } }$ is the closure of $C$ .

Example 2.2 Consider a square in the $( x _ { 1 } , x _ { 2 } )$ -plane in $\mathbf { R } ^ { 3 }$ , defined as

$$
C = \{x \in \mathbf {R} ^ {3} \mid - 1 \leq x _ {1} \leq 1, - 1 \leq x _ {2} \leq 1, x _ {3} = 0 \}.
$$

Its affine hull is the $( x _ { 1 } , x _ { 2 } )$ -plane, i.e., aff $C = \{ x \in \mathbf { R } ^ { 3 } \mid x _ { 3 } = 0 \}$ . The interior of $C$ is empty, but the relative interior is

$$
\operatorname {r e l i n t} C = \left\{x \in \mathbf {R} ^ {3} \mid - 1 <   x _ {1} <   1, - 1 <   x _ {2} <   1, x _ {3} = 0 \right\}.
$$

Its boundary (in $\mathbf { R } ^ { 3 }$ ) is itself; its relative boundary is the wire-frame outline,

$$
\{x \in \mathbf {R} ^ {3} \mid \max  \{| x _ {1} |, | x _ {2} | \} = 1, x _ {3} = 0 \}.
$$

# 2.1.4 Convex sets

A set $C$ is convex if the line segment between any two points in $C$ lies in $C$ , i.e., if for any $x _ { 1 } , x _ { 2 } \in C$ and any $\theta$ with $0 \leq \theta \leq 1$ , we have

$$
\theta x _ {1} + (1 - \theta) x _ {2} \in C.
$$

![](数学书/凸优化/images/a89c60fbaa31fc1b6538edce57e1d5b17bc26bf582ea91d579cdd42694d798c8.jpg)

![](数学书/凸优化/images/5a779a4f8fbcbfebb880d07784f63e534ca4a854b3f3c52b346c73e9a8680d8d.jpg)  
Figure 2.2 Some simple convex and nonconvex sets. Left. The hexagon, which includes its boundary (shown darker), is convex. Middle. The kidney shaped set is not convex, since the line segment between the two points in the set shown as dots is not contained in the set. Right. The square contains some boundary points but not others, and is not convex.   
Figure 2.3 The convex hulls of two sets in $\mathbf { R } ^ { 2 }$ . Left. The convex hull of a set of fifteen points (shown as dots) is the pentagon (shown shaded). Right. The convex hull of the kidney shaped set in figure 2.2 is the shaded set.

Roughly speaking, a set is convex if every point in the set can be seen by every other point, along an unobstructed straight path between them, where unobstructed means lying in the set. Every affine set is also convex, since it contains the entire line between any two distinct points in it, and therefore also the line segment between the points. Figure 2.2 illustrates some simple convex and nonconvex sets in $\mathbf { R } ^ { 2 }$ .

We call a point of the form $\theta _ { 1 } x _ { 1 } + \cdot \cdot \cdot + \theta _ { k } x _ { k }$ , where $\theta _ { 1 } + \cdot \cdot \cdot + \theta _ { k } = 1$ and $\theta _ { i } \geq 0$ , $i = 1 , \ldots , k$ , a convex combination of the points $x _ { 1 }$ , . . . , $x _ { k }$ . As with affine sets, it can be shown that a set is convex if and only if it contains every convex combination of its points. A convex combination of points can be thought of as a mixture or weighted average of the points, with $\theta _ { i }$ the fraction of $x _ { i }$ in the mixture.

The convex hull of a set $C$ , denoted conv $C$ , is the set of all convex combinations of points in $C$ :

$$
\mathbf {c o n v} C = \left\{\theta_ {1} x _ {1} + \dots + \theta_ {k} x _ {k} \mid x _ {i} \in C, \theta_ {i} \geq 0, i = 1, \dots , k, \theta_ {1} + \dots + \theta_ {k} = 1 \right\}.
$$

As the name suggests, the convex hull conv $C$ is always convex. It is the smallest convex set that contains $C$ : If $B$ is any convex set that contains $C$ , then conv $C \subseteq$ $B$ . Figure 2.3 illustrates the definition of convex hull.

The idea of a convex combination can be generalized to include infinite sums, integrals, and, in the most general form, probability distributions. Suppose $\theta _ { 1 } , \theta _ { 2 } , \ldots$

satisfy

$$
\theta_ {i} \geq 0, \quad i = 1, 2, \dots , \quad \sum_ {i = 1} ^ {\infty} \theta_ {i} = 1,
$$

and $x _ { 1 } , x _ { 2 } , \dotsc \in C$ , where $C \subseteq \mathbf { R } ^ { n }$ is convex. Then

$$
\sum_ {i = 1} ^ {\infty} \theta_ {i} x _ {i} \in C,
$$

if the series converges. More generally, suppose $p : \mathbf { R } ^ { \pi }  \mathbf { R }$ satisfies $p ( x ) \geq 0$ for all $x \in C$ and $\int _ { C } p ( x )$ dx = 1, where $C \subseteq \mathbf { R } ^ { n }$ is convex. Then

$$
\int_ {C} p (x) x d x \in C,
$$

if the integral exists.

In the most general form, suppose $C \subseteq \mathbf { R } ^ { n }$ is convex and $x$ is a random vector with $x \in C$ with probability one. Then $\mathbf { E } x \in C$ . Indeed, this form includes all the others as special cases. For example, suppose the random variable $x$ only takes on the two values $x _ { 1 }$ and $x _ { 2 }$ , with $\mathbf { p r o b } ( x = x _ { 1 } ) = \theta$ and $\mathbf { p r o b } ( x = x _ { 2 } ) = 1 - \theta$ , where $0 \leq \theta \leq 1$ . Then $\mathbf { E } x = \theta x _ { 1 } + ( 1 - \theta ) x _ { 2 }$ , and we are back to a simple convex combination of two points.

# 2.1.5 Cones

A set $C$ is called a cone, or nonnegative homogeneous, if for every $x \in C$ and $\theta \geq 0$ we have $\theta x \in C$ . A set $C$ is a convex cone if it is convex and a cone, which means that for any $x _ { 1 } , x _ { 2 } \in C$ and $\theta _ { 1 } , \ \theta _ { 2 } \geq 0$ , we have

$$
\theta_ {1} x _ {1} + \theta_ {2} x _ {2} \in C.
$$

Points of this form can be described geometrically as forming the two-dimensional pie slice with apex 0 and edges passing through $x _ { 1 }$ and $x _ { 2 }$ . (See figure 2.4.)

A point of the form $\theta _ { 1 } x _ { 1 } + \cdot \cdot \cdot + \theta _ { k } x _ { k }$ with $\theta _ { 1 } , \ldots , \theta _ { k } \ \geq \ 0$ is called a conic combination (or a nonnegative linear combination) of $x _ { 1 } , \ldots , x _ { k }$ . If $x _ { i }$ are in a convex cone $C$ , then every conic combination of $x _ { i }$ is in $C$ . Conversely, a set $C$ is a convex cone if and only if it contains all conic combinations of its elements. Like convex (or affine) combinations, the idea of conic combination can be generalized to infinite sums and integrals.

The conic hull of a set $C$ is the set of all conic combinations of points in $C$ , i.e.,

$$
\left\{\theta_ {1} x _ {1} + \dots + \theta_ {k} x _ {k} \mid x _ {i} \in C, \theta_ {i} \geq 0, i = 1, \dots , k \right\},
$$

which is also the smallest convex cone that contains $C$ (see figure 2.5).

![](数学书/凸优化/images/643db35a8da2f4e06fe05ee3ac09758796262ed1fb663d3b717f1cfdfa32a016.jpg)  
Figure 2.4 The pie slice shows all points of the form $\theta _ { 1 } x _ { 1 } + \theta _ { 2 } x _ { 2 }$ , where $\theta _ { 1 } , \ \theta _ { 2 } \geq 0$ . The apex of the slice (which corresponds to $\theta _ { 1 } = \theta _ { 2 } = 0$ ) is at $_ 0$ ; its edges (which correspond to $\theta _ { 1 } = 0$ or $\theta _ { 2 } = 0$ ) pass through the points $x _ { 1 }$ and $x _ { 2 }$ .

![](数学书/凸优化/images/efe70d12bc16893829c82f6149afca63f0b34da3a1f77adfd3a76df50472ab67.jpg)

![](数学书/凸优化/images/015bdb258e6a51c4b28e3cc20682e0a3dfa97e54d787f039fc68fd9d2c33f2fb.jpg)  
Figure 2.5 The conic hulls (shown shaded) of the two sets of figure 2.3.

# 2.2 Some important examples

In this section we describe some important examples of convex sets which we will encounter throughout the rest of the book. We start with some simple examples.

• The empty set $\varnothing$ , any single point (i.e., singleton) $\{ x _ { 0 } \}$ , and the whole space $\mathbf { R } ^ { \pi }$ are affine (hence, convex) subsets of $\mathbf { R } ^ { \pi }$ .   
• Any line is affine. If it passes through zero, it is a subspace, hence also a convex cone.   
• A line segment is convex, but not affine (unless it reduces to a point).   
• A ray, which has the form $\{ x _ { 0 } + \theta v \mid \theta \geq 0 \}$ , where $v \neq 0$ , is convex, but not affine. It is a convex cone if its base $x _ { 0 }$ is $0$ .   
• Any subspace is affine, and a convex cone (hence convex).

# 2.2.1 Hyperplanes and halfspaces

A hyperplane is a set of the form

$$
\{x \mid a ^ {T} x = b \},
$$

where $a \in \mathbf { R } ^ { n }$ , $a \neq 0$ , and $b \in \mathbf { R }$ . Analytically it is the solution set of a nontrivial linear equation among the components of $x$ (and hence an affine set). Geometrically, the hyperplane $\{ x \mid a ^ { \prime } x = b \}$ can be interpreted as the set of points with a constant inner product to a given vector $a$ , or as a hyperplane with normal vector $a$ ; the constant $b \in \mathbf { R }$ determines the offset of the hyperplane from the origin. This geometric interpretation can be understood by expressing the hyperplane in the form

$$
\{x \mid a ^ {T} (x - x _ {0}) = 0 \},
$$

where $x _ { 0 }$ is any point in the hyperplane (i.e., any point that satisfies $a ^ { T } x _ { 0 } = b$ ). This representation can in turn be expressed as

$$
\{x \mid a ^ {T} (x - x _ {0}) = 0 \} = x _ {0} + a ^ {\perp},
$$

where $a ^ { \perp }$ denotes the orthogonal complement of $a$ , i.e., the set of all vectors orthogonal to it:

$$
a ^ {\perp} = \left\{v \mid a ^ {T} v = 0 \right\}.
$$

This shows that the hyperplane consists of an offset $x _ { 0 }$ , plus all vectors orthogonal to the (normal) vector $a$ . These geometric interpretations are illustrated in figure 2.6.

A hyperplane divides $\mathbf { R } ^ { n }$ into two halfspaces. A (closed) halfspace is a set of the form

$$
\{x \mid a ^ {T} x \leq b \}, \tag {2.1}
$$

where $a \neq 0$ , i.e., the solution set of one (nontrivial) linear inequality. Halfspaces are convex, but not affine. This is illustrated in figure 2.7.

![](数学书/凸优化/images/9972cc908a9e7fb67b6834d650c6a0174afb76cc756aa72b7d3b579b90a161ef.jpg)  
Figure 2.6 Hyperplane in $\mathbf { R } ^ { 2 }$ , with normal vector $a$ and a point $x _ { 0 }$ in the hyperplane. For any point $_ { x }$ in the hyperplane, $x - x _ { 0 }$ (shown as the darker arrow) is orthogonal to $^ { a }$ .

![](数学书/凸优化/images/86126f40eeca5c17f494a4d742e4aa98c04dc07ea34f67eb0a845dbbf58a5e47.jpg)  
Figure 2.7 A hyperplane defined by $a ^ { x } x = b$ in $\mathbf { R } ^ { 2 }$ determines two halfspaces. The halfspace determined by $a ^ { x } x \geq b$ (not shaded) is the halfspace extending in the direction $a$ . The halfspace determined by $a ^ { x } x \leq b$ (which is shown shaded) extends in the direction $- a$ . The vector $a$ is the outward normal of this halfspace.

![](数学书/凸优化/images/7ccf1ed3c829012d7ca4cb433bbea169c2e2338a967b13674b1e31a004063df0.jpg)  
Figure 2.8 The shaded set is the halfspace determined by $a ^ { \prime } ( x - x _ { 0 } ) \leq 0$ . The vector $x _ { 1 } - x _ { 0 }$ makes an acute angle with $a$ , so $x _ { 1 }$ is not in the halfspace. The vector $x _ { 2 } - x _ { 0 }$ makes an obtuse angle with $a$ , and so is in the halfspace.

The halfspace (2.1) can also be expressed as

$$
\{x \mid a ^ {T} (x - x _ {0}) \leq 0 \}, \tag {2.2}
$$

where $x _ { 0 }$ is any point on the associated hyperplane, i.e., satisfies $a ^ { \mathrm { { ' } } } x _ { 0 } = b$ . The representation (2.2) suggests a simple geometric interpretation: the halfspace consists of $x _ { 0 }$ plus any vector that makes an obtuse (or right) angle with the (outward normal) vector $a$ . This is illustrated in figure 2.8.

The boundary of the halfspace (2.1) is the hyperplane $\{ x \mid a ^ { \prime } x = b \}$ . The set $\{ x \mid a ^ { T } x < b \}$ , which is the interior of the halfspace $\{ x \mid a ^ { T } x \leq b \}$ , is called an open halfspace.

# 2.2.2 Euclidean balls and ellipsoids

A (Euclidean) ball (or just ball) in $\mathbf { R } ^ { n }$ has the form

$$
B \left(x _ {c}, r\right) = \left\{x \mid \| x - x _ {c} \| _ {2} \leq r \right\} = \left\{x \mid \left(x - x _ {c}\right) ^ {T} \left(x - x _ {c}\right) \leq r ^ {2} \right\},
$$

where $r > 0$ , and $\| \cdot \| _ { 2 }$ denotes the Euclidean norm, i.e., $\| u \| _ { 2 } = ( u ^ { T } u ) ^ { 1 / 2 }$ . The vector $x _ { c }$ is the center of the ball and the scalar $r$ is its radius; $\boldsymbol { B } ( \boldsymbol { x } _ { c } , \boldsymbol { r } )$ consists of all points within a distance $r$ of the center $x _ { c }$ . Another common representation for the Euclidean ball is

$$
B \left(x _ {c}, r\right) = \left\{x _ {c} + r u \mid \| u \| _ {2} \leq 1 \right\}.
$$

![](数学书/凸优化/images/0079f16831776421994779e63dd61fa9d471503c82bc1461f7019b19ef5c3e65.jpg)  
Figure 2.9 An ellipsoid in $\mathbf { R } ^ { 2 }$ , shown shaded. The center $x _ { c }$ is shown as a dot, and the two semi-axes are shown as line segments.

A Euclidean ball is a convex set: if $\| x _ { 1 } - x _ { c } \| _ { 2 } \ \leq \ r$ , $\| x _ { 2 } - x _ { c } \| _ { 2 } \ \leq \ r$ , and $0 \leq \theta \leq 1$ , then

$$
\begin{array}{l} \left\| \theta x _ {1} + (1 - \theta) x _ {2} - x _ {c} \right\| _ {2} = \left\| \theta \left(x _ {1} - x _ {c}\right) + (1 - \theta) \left(x _ {2} - x _ {c}\right) \right\| _ {2} \\ \leq \theta \| x _ {1} - x _ {c} \| _ {2} + (1 - \theta) \| x _ {2} - x _ {c} \| _ {2} \\ \leq r. \\ \end{array}
$$

(Here we use the homogeneity property and triangle inequality for $\lVert \cdot \rVert _ { 2 }$ ; see §A.1.2.)

A related family of convex sets is the ellipsoids, which have the form

$$
\mathcal {E} = \left\{x \mid \left(x - x _ {c}\right) ^ {T} P ^ {- 1} \left(x - x _ {c}\right) \leq 1 \right\}, \tag {2.3}
$$

where $P = P ^ { T } \succ 0$ , i.e., $P$ is symmetric and positive definite. The vector $x _ { c } \in \mathbf { R } ^ { \pi }$ is the center of the ellipsoid. The matrix $P$ determines how far the ellipsoid extends in every direction from $x _ { c }$ ; the lengths of the semi-axes of $\varepsilon$ are given by $\sqrt { \lambda _ { i } }$ , where $\lambda _ { i }$ are the eigenvalues of $P$ . A ball is an ellipsoid with $P = r ^ { 2 } I$ . Figure 2.9 shows an ellipsoid in $\mathbf { R } ^ { 2 }$ .

Another common representation of an ellipsoid is

$$
\mathcal {E} = \left\{x _ {c} + A u \mid \| u \| _ {2} \leq 1 \right\}, \tag {2.4}
$$

where $A$ is square and nonsingular. In this representation we can assume without loss of generality that $A$ is symmetric and positive definite. By taking $A = P ^ { 1 / 2 }$ , this representation gives the ellipsoid defined in (2.3). When the matrix $A$ in (2.4) is symmetric positive semidefinite but singular, the set in (2.4) is called a degenerate ellipsoid; its affine dimension is equal to the rank of $A$ . Degenerate ellipsoids are also convex.

# 2.2.3 Norm balls and norm cones

Suppose $\left\| \cdot \right\|$ is any norm on $\mathbf { R } ^ { n }$ (see §A.1.2). From the general properties of norms it can be shown that a norm ball of radius $r$ and center $x _ { c }$ , given by $\{ x \mid \| x - x _ { c } \| \leq r \}$ , is convex. The norm cone associated with the norm $\| \cdot \|$ is the set

$$
C = \{(x, t) \mid \| x \| \leq t \} \subseteq \mathbf {R} ^ {n + 1}.
$$

![](数学书/凸优化/images/0f5c7d4944e39c93d282af2ff684ffe548ef91110c7d68fe700a4f4d96cd1188.jpg)  
Figure 2.10 Boundary of second-order cone in $\mathbf { R } ^ { 3 }$ , $\begin{array} { r } { \{ ( x _ { 1 } , x _ { 2 } , t ) \mid ( x _ { 1 } ^ { 2 } + x _ { 2 } ^ { 2 } ) ^ { 1 / 2 } \leq } \end{array}$ $t \}$ .

It is (as the name suggests) a convex cone.

Example 2.3 The second-order cone is the norm cone for the Euclidean norm, i.e.,

$$
\begin{array}{l} C = \{(x, t) \in \mathbf {R} ^ {n + 1} \mid \| x \| _ {2} \leq t \} \\ = \left\{\left[ \begin{array}{c} x \\ t \end{array} \right] \Bigg | \left[ \begin{array}{c} x \\ t \end{array} \right] ^ {T} \left[ \begin{array}{c c} I & 0 \\ 0 & - 1 \end{array} \right] \left[ \begin{array}{c} x \\ t \end{array} \right] \leq 0, t \geq 0 \right\}. \\ \end{array}
$$

The second-order cone is also known by several other names. It is called the quadratic cone, since it is defined by a quadratic inequality. It is also called the Lorentz cone or ice-cream cone. Figure 2.10 shows the second-order cone in $\mathbf { R } ^ { 3 }$ .

# 2.2.4 Polyhedra

A polyhedron is defined as the solution set of a finite number of linear equalities and inequalities:

$$
\mathcal {P} = \{x \mid a _ {j} ^ {T} x \leq b _ {j}, j = 1, \dots , m, c _ {j} ^ {T} x = d _ {j}, j = 1, \dots , p \}. \tag {2.5}
$$

A polyhedron is thus the intersection of a finite number of halfspaces and hyperplanes. Affine sets (e.g., subspaces, hyperplanes, lines), rays, line segments, and halfspaces are all polyhedra. It is easily shown that polyhedra are convex sets. A bounded polyhedron is sometimes called a polytope, but some authors use the opposite convention (i.e., polytope for any set of the form (2.5), and polyhedron

![](数学书/凸优化/images/81bd7bb0c6d63039c601cfb434e905b8b94084dba6db6a88e6b0dcd2ac8346a1.jpg)  
Figure 2.11 The polyhedron $\mathcal { P }$ (shown shaded) is the intersection of five halfspaces, with outward normal vectors $a _ { 1 } , \ldots , a _ { 5 }$ .

when it is bounded). Figure 2.11 shows an example of a polyhedron defined as the intersection of five halfspaces.

It will be convenient to use the compact notation

$$
\mathcal {P} = \{x \mid A x \preceq b, C x = d \} \tag {2.6}
$$

for (2.5), where

$$
A = \left[ \begin{array}{c} a _ {1} ^ {T} \\ \vdots \\ a _ {m} ^ {T} \end{array} \right], \qquad C = \left[ \begin{array}{c} c _ {1} ^ {T} \\ \vdots \\ c _ {p} ^ {T} \end{array} \right],
$$

and the symbol $\preceq$ denotes vector inequality or componentwise inequality in $\mathbf { R } ^ { m }$ : $u \preceq v$ means $u _ { i } \leq v _ { i }$ for $i = 1 , \ldots , m$ .

Example 2.4 The nonnegative orthant is the set of points with nonnegative components, i.e.,

$$
\mathbf {R} _ {+} ^ {n} = \{x \in \mathbf {R} ^ {n} \mid x _ {i} \geq 0, i = 1, \dots , n \} = \{x \in \mathbf {R} ^ {n} \mid x \succeq 0 \}.
$$

(Here $\mathbf { R } _ { + }$ denotes the set of nonnegative numbers: $\mathbf { R } _ { + } = \{ x \in \mathbf { R } \mid x \geq 0 \}$ .) The nonnegative orthant is a polyhedron and a cone (and therefore called a polyhedral cone).

# Simplexes

Simplexes are another important family of polyhedra. Suppose the $k + 1$ points $v _ { 0 } , \ldots , v _ { k } \ \in \ \mathbf { R } ^ { n }$ are affinely independent, which means $v _ { 1 } - v _ { 0 } , \ldots , v _ { k } - v _ { 0 }$ are linearly independent. The simplex determined by them is given by

$$
C = \operatorname {c o n v} \left\{v _ {0}, \dots , v _ {k} \right\} = \left\{\theta_ {0} v _ {0} + \dots + \theta_ {k} v _ {k} \mid \theta \succeq 0, \mathbf {1} ^ {T} \theta = 1 \right\}, \tag {2.7}
$$

where 1 denotes the vector with all entries one. The affine dimension of this simplex is $k$ , so it is sometimes referred to as a $k$ -dimensional simplex in $\mathbf { R } ^ { n }$ .

Example 2.5 Some common simplexes. A 1-dimensional simplex is a line segment; a 2-dimensional simplex is a triangle (including its interior); and a 3-dimensional simplex is a tetrahedron.

The unit simplex is the $n$ -dimensional simplex determined by the zero vector and the unit vectors, i.e., 0, $e _ { 1 } , \ldots , e _ { n } \in \mathbf { R } ^ { n }$ . It can be expressed as the set of vectors that satisfy

$$
x \succeq 0, \quad \mathbf {1} ^ {T} x \leq 1.
$$

The probability simplex is the $( n - 1 )$ -dimensional simplex determined by the unit vectors $e _ { 1 } , \ldots , e _ { n } \in \mathbf { R } ^ { n }$ . It is the set of vectors that satisfy

$$
x \succeq 0, \quad \mathbf {1} ^ {T} x = 1.
$$

Vectors in the probability simplex correspond to probability distributions on a set with $n$ elements, with $x _ { i }$ interpreted as the probability of the ith element.

To describe the simplex (2.7) as a polyhedron, i.e., in the form (2.6), we proceed as follows. By definition, $x \in C$ if and only if $x = \theta _ { 0 } v _ { 0 } + \theta _ { 1 } v _ { 1 } + \cdot \cdot \cdot + \theta _ { k } v _ { k }$ for some $\theta \succeq 0$ with $\mathbf { 1 } ^ { T } \theta = 1$ . Equivalently, if we define $y = ( \theta _ { 1 } , \ldots , \theta _ { k } )$ and

$$
B = \left[ \begin{array}{c c c} v _ {1} - v _ {0} & \dots & v _ {k} - v _ {0} \end{array} \right] \in \mathbf {R} ^ {n \times k},
$$

we can say that $x \in C$ if and only if

$$
x = v _ {0} + B y \tag {2.8}
$$

for some $y \succeq 0$ with $\mathbf { 1 } ^ { T } y \le 1$ . Now we note that affine independence of the points $v _ { 0 } , \ldots , v _ { k }$ implies that the matrix $B$ has rank $k$ . Therefore there exists a nonsingular matrix $A = ( A _ { 1 } , A _ { 2 } ) \in \mathbf { R } ^ { n \times n }$ such that

$$
A B = \left[ \begin{array}{c} A _ {1} \\ A _ {2} \end{array} \right] B = \left[ \begin{array}{c} I \\ 0 \end{array} \right].
$$

Multiplying (2.8) on the left with $A$ , we obtain

$$
A _ {1} x = A _ {1} v _ {0} + y, \quad A _ {2} x = A _ {2} v _ {0}.
$$

From this we see that $x \in C$ if and only if $A _ { 2 } x \ = \ A _ { 2 } v _ { 0 }$ , and the vector $y =$ $A _ { 1 } x - A _ { 1 } v _ { 0 }$ satisfies $y \succeq 0$ and $\mathbf { 1 } ^ { T } y \leq 1$ . In other words we have $x \in C$ if and only if

$$
A _ {2} x = A _ {2} v _ {0}, \quad A _ {1} x \succeq A _ {1} v _ {0}, \quad \mathbf {1} ^ {T} A _ {1} x \leq 1 + \mathbf {1} ^ {T} A _ {1} v _ {0},
$$

which is a set of linear equalities and inequalities in $x$ , and so describes a polyhedron.

# Convex hull description of polyhedra

The convex hull of the finite set $\{ v _ { 1 } , \ldots , v _ { k } \}$ i s

$$
\mathbf {c o n v} \{v _ {1}, \dots , v _ {k} \} = \left\{\theta_ {1} v _ {1} + \dots + \theta_ {k} v _ {k} \mid \theta \succeq 0, \mathbf {1} ^ {T} \theta = 1 \right\}.
$$

This set is a polyhedron, and bounded, but (except in special cases, e.g., a simplex) it is not simple to express it in the form (2.5), i.e., by a set of linear equalities and inequalities.

A generalization of this convex hull description is

$$
\left\{\theta_ {1} v _ {1} + \dots + \theta_ {k} v _ {k} \mid \theta_ {1} + \dots + \theta_ {m} = 1, \theta_ {i} \geq 0, i = 1, \dots , k \right\}, \tag {2.9}
$$

where $m \leq k$ . Here we consider nonnegative linear combinations of $v _ { i }$ , but only the first $m$ coefficients are required to sum to one. Alternatively, we can interpret (2.9) as the convex hull of the points $v _ { 1 } , \ldots , v _ { m }$ , plus the conic hull of the points $v _ { m + 1 } , \ldots , v _ { k }$ . The set (2.9) defines a polyhedron, and conversely, every polyhedron can be represented in this form (although we will not show this).

The question of how a polyhedron is represented is subtle, and has very important practical consequences. As a simple example consider the unit ball in the $\ell _ { \infty }$ -norm in $\mathbf { R } ^ { n }$ ,

$$
C = \{x \mid | x _ {i} | \leq 1, i = 1, \dots , n \}.
$$

The set $C$ can be described in the form (2.5) with $2 n$ linear inequalities $\pm e _ { i } ^ { { \cal T } } x \le 1$ , where $e _ { i }$ is the $i$ th unit vector. To describe it in the convex hull form (2.9) requires at least $2 ^ { n }$ points:

$$
C = \operatorname {c o n v} \left\{v _ {1}, \dots , v _ {2 ^ {n}} \right\},
$$

where $v _ { 1 } , \ldots , v _ { 2 ^ { n } }$ are the $2 ^ { n }$ vectors all of whose components are 1 or $^ { - 1 }$ . Thus the size of the two descriptions differs greatly, for large $n$ .

# 2.2.5 The positive semidefinite cone

We use the notation $\mathbf { S } ^ { n }$ to denote the set of symmetric $n \times n$ matrices,

$$
\mathbf {S} ^ {n} = \left\{X \in \mathbf {R} ^ {n \times n} \mid X = X ^ {T} \right\},
$$

which is a vector space with dimension $n ( n + 1 ) / 2$ . We use the notation $\mathbf { S } _ { + } ^ { n }$ to denote the set of symmetric positive semidefinite matrices:

$$
\mathbf {S} _ {+} ^ {n} = \{X \in \mathbf {S} ^ {n} \mid X \succeq 0 \},
$$

and the notation $\mathbf { S } _ { + + } ^ { n }$ to denote the set of symmetric positive definite matrices:

$$
\mathbf {S} _ {+ n} ^ {+} = \{X \in \mathbf {S} ^ {n} \mid X \succ 0 \}.
$$

(This notation is meant to be analogous to $\mathbf { R } _ { + }$ , which denotes the nonnegative reals, and $\mathbf { R } _ { + + }$ , which denotes the positive reals.)

![](数学书/凸优化/images/c6bb50d1ee1470ca26f5dae5ce30f8083d9425bd3a4ae0c68f94ddce954b1ead.jpg)  
Figure 2.12 Boundary of positive semidefinite cone in $\mathbf { S } ^ { 2 }$ .

The set $\mathbf { S } _ { + } ^ { n }$ is a convex cone: if $\theta _ { 1 } , \theta _ { 2 } \geq 0$ and $A$ , $B \in { \mathbf S } _ { + } ^ { n }$ , then $\theta _ { 1 } A + \theta _ { 2 } B \in \mathbf { S } _ { + } ^ { n }$ . This can be seen directly from the definition of positive semidefiniteness: for any $\boldsymbol { x } \in \mathbf { R } ^ { \pi }$ , we have

$$
x ^ {T} (\theta_ {1} A + \theta_ {2} B) x = \theta_ {1} x ^ {T} A x + \theta_ {2} x ^ {T} B x \geq 0,
$$

if $A \succeq 0$ , $B \succeq 0$ and $\theta _ { 1 }$ , $\theta _ { 2 } \geq 0$ .

Example 2.6 Positive semidefinite cone in $\mathbf { S } ^ { 2 }$ . We have

$$
X = \left[ \begin{array}{c c} x & y \\ y & z \end{array} \right] \in \mathbf {S} _ {+} ^ {2} \quad \Longleftrightarrow \quad x \geq 0, \quad z \geq 0, \quad x z \geq y ^ {2}.
$$

The boundary of this cone is shown in figure 2.12, plotted in $\mathbf { R } ^ { 3 }$ as $( x , y , z )$ .

# 2.3 Operations that preserve convexity

In this section we describe some operations that preserve convexity of sets, or allow us to construct convex sets from others. These operations, together with the simple examples described in §2.2, form a calculus of convex sets that is useful for determining or establishing convexity of sets.

# 2.3.1 Intersection

Convexity is preserved under intersection: if $S _ { 1 }$ and $S _ { 2 }$ are convex, then $S _ { 1 } \cap S _ { 2 }$ is convex. This property extends to the intersection of an infinite number of sets: if $S _ { \alpha }$ is convex for every $\alpha \in { \mathcal { A } }$ , then $\textstyle \bigcap _ { \alpha \in A } S _ { \alpha }$ is convex. (Subspaces, affine sets, and convex cones are also closed under arbitrary intersections.) As a simple example, a polyhedron is the intersection of halfspaces and hyperplanes (which are convex), and therefore is convex.

Example 2.7 The positive semidefinite cone ${ \bf S } _ { + } ^ { n }$ can be expressed as

$$
\bigcap_ {z \neq 0} \{X \in \mathbf {S} ^ {n} \mid z ^ {T} X z \geq 0 \}.
$$

For each $z \neq 0$ , $z ^ { T } X z$ is a (not identically zero) linear function of $X$ , so the sets

$$
\{X \in \mathbf {S} ^ {n} \mid z ^ {T} X z \geq 0 \}
$$

are, in fact, halfspaces in $\mathbf { S } ^ { n }$ . Thus the positive semidefinite cone is the intersection of an infinite number of halfspaces, and so is convex.

Example 2.8 We consider the set

$$
S = \left\{x \in \mathbf {R} ^ {m} \mid | p (t) | \leq 1 \text {f o r} | t | \leq \pi / 3 \right\}, \tag {2.10}
$$

where $\begin{array} { r } { p ( t ) = \sum _ { k = 1 } ^ { m } x _ { k } \cos k t } \end{array}$ . The set $S$ can be expressed as the intersection of an infinite number of slabs: $\begin{array} { r } { S = \int \rceil _ { | t | \leq \pi / 3 } S _ { t } } \end{array}$ , where

$$
S _ {t} = \left\{x \mid - 1 \leq (\cos t, \dots , \cos m t) ^ {T} x \leq 1 \right\},
$$

and so is convex. The definition and the set are illustrated in figures 2.13 and 2.14, for $m = 2$ .

In the examples above we establish convexity of a set by expressing it as a (possibly infinite) intersection of halfspaces. We will see in §2.5.1 that a converse holds: every closed convex set $S$ is a (usually infinite) intersection of halfspaces. In fact, a closed convex set $S$ is the intersection of all halfspaces that contain it:

$$
S = \bigcap \{\mathcal {H} \mid \mathcal {H} \text {h a l f s p a c e}, S \subseteq \mathcal {H} \}.
$$

# 2.3.2 Affine functions

Recall that a function $f : \mathbf { R } ^ { n }  \mathbf { R } ^ { m }$ is affine if it is a sum of a linear function and a constant, i.e., if it has the form $f ( x ) = A x + b$ , where $A \in \mathbf { R } ^ { m \times n }$ and $b \in \mathbf { R } ^ { m }$ . Suppose $S \subseteq \mathbf { R } ^ { \pi }$ is convex and $f : \mathbf { R } ^ { n }  \mathbf { R } ^ { \prime \prime \iota }$ is an affine function. Then the image of $S$ under $f$ ,

$$
f (S) = \{f (x) \mid x \in S \},
$$

![](数学书/凸优化/images/ac912070f370203de27f5f4a92d73988dd15a01ff827e811a5a9e71c6d9f239e.jpg)  
Figure 2.13 Three trigonometric polynomials associated with points in the set $S$ defined in (2.10), for $m = 2$ . The trigonometric polynomial plotted with dashed line type is the average of the other two.

![](数学书/凸优化/images/62b6536ea3fc7b3bbfd92befe82907d64f3f229c12dac6e92fd5fe09b6ff9ef0.jpg)  
Figure 2.14 The set $S$ defined in (2.10), for $m = 2$ , is shown as the white area in the middle of the plot. The set is the intersection of an infinite number of slabs (20 of which are shown), hence convex.

is convex. Similarly, if $f : \mathbf { R } ^ { k }  \mathbf { R } ^ { n }$ is an affine function, the inverse image of $S$ under $f$ ,

$$
f ^ {- 1} (S) = \{x \mid f (x) \in S \},
$$

is convex.

Two simple examples are scaling and translation. If $S \subseteq \mathbf { R } ^ { \pi }$ is convex, $\alpha \in \mathbf { R }$ , and $a \in \mathbf { R } ^ { \pi }$ , then the sets $\alpha S$ and $S + a$ are convex, where

$$
\alpha S = \{\alpha x \mid x \in S \}, \qquad S + a = \{x + a \mid x \in S \}.
$$

The projection of a convex set onto some of its coordinates is convex: if $S \subseteq$ $\mathbf { R } ^ { \prime \prime \iota } \times \mathbf { R } ^ { \prime \iota }$ is convex, then

$$
T = \left\{x _ {1} \in \mathbf {R} ^ {m} \mid (x _ {1}, x _ {2}) \in S \text {f o r s o m e} x _ {2} \in \mathbf {R} ^ {n} \right\}
$$

is convex.

The sum of two sets is defined as

$$
S _ {1} + S _ {2} = \{x + y \mid x \in S _ {1}, y \in S _ {2} \}.
$$

If $S _ { 1 }$ and $S _ { 2 }$ are convex, then $S _ { 1 } + S _ { 2 }$ is convex. To see this, if $S _ { 1 }$ and $S _ { 2 }$ are convex, then so is the direct or Cartesian product

$$
S _ {1} \times S _ {2} = \left\{\left(x _ {1}, x _ {2}\right) \mid x _ {1} \in S _ {1}, x _ {2} \in S _ {2} \right\}.
$$

The image of this set under the linear function $f ( x _ { 1 } , x _ { 2 } ) = x _ { 1 } + x _ { 2 }$ is the sum $S _ { 1 } + S _ { 2 }$ .

We can also consider the partial sum of $S _ { 1 } , \ S _ { 2 } \in \mathbf { R } ^ { n } \times \mathbf { R } ^ { m }$ , defined as

$$
S = \left\{\left(x, y _ {1} + y _ {2}\right) \mid \left(x, y _ {1}\right) \in S _ {1}, \left(x, y _ {2}\right) \in S _ {2} \right\},
$$

where $\boldsymbol { x } \in \mathbf { R } ^ { n }$ and $y _ { i } \in \mathbf { R } ^ { m }$ . For $m = 0$ , the partial sum gives the intersection of $S _ { 1 }$ and $S _ { 2 }$ ; for $n = 0$ , it is set addition. Partial sums of convex sets are convex (see exercise 2.16).

Example 2.9 Polyhedron. The polyhedron $\{ x \mid A x \preceq b , C x = d \}$ can be expressed as the inverse image of the Cartesian product of the nonnegative orthant and the origin under the affine function $f ( x ) = ( b - A x , d - C x )$ :

$$
\{x \mid A x \preceq b, C x = d \} = \{x \mid f (x) \in \mathbf {R} _ {+} ^ {m} \times \{0 \} \}.
$$

Example 2.10 Solution set of linear matrix inequality. The condition

$$
A (x) = x _ {1} A _ {1} + \dots + x _ {n} A _ {n} \preceq B, \tag {2.11}
$$

where $B$ , $A _ { i } \in { \bf S } ^ { m }$ , is called a linear matrix inequality (LMI) in $x$ . (Note the similarity to an ordinary linear inequality,

$$
a ^ {T} x = x _ {1} a _ {1} + \dots + x _ {n} a _ {n} \leq b,
$$

with $b , \ a _ { i } \in \mathbf { R }$ .)

The solution set of a linear matrix inequality, $\{ x \mid A ( x ) \preceq B \}$ , is convex. Indeed, it is the inverse image of the positive semidefinite cone under the affine function $f : \mathbf { R } ^ { n }  \mathbf { S } ^ { m }$ given by $f ( x ) = B - A ( x )$ .

Example 2.11 Hyperbolic cone. The set

$$
\{x \mid x ^ {T} P x \leq (c ^ {T} x) ^ {2}, c ^ {T} x \geq 0 \}
$$

where $P \in \mathbf { S } _ { + } ^ { n }$ and $c \in \mathbf { R } ^ { n }$ , is convex, since it is the inverse image of the second-order cone,

$$
\{(z, t) \mid z ^ {T} z \leq t ^ {2}, t \geq 0 \},
$$

under the affine function $f ( x ) = ( P ^ { 1 / 2 } x , c ^ { T } x )$ .

Example 2.12 Ellipsoid. The ellipsoid

$$
\mathcal {E} = \{x \mid (x - x _ {c}) ^ {T} P ^ {- 1} (x - x _ {c}) \leq 1 \},
$$

where $P \in \mathbf { S } _ { + + } ^ { n }$ , is the image of the unit Euclidean ball $\{ u \mid \| u \| _ { 2 } \leq 1 \}$ under the affine mapping $f ( u ) = P ^ { 1 / 2 } u + x _ { c }$ . (It is also the inverse image of the unit ball under the affine mapping $g ( x ) = P ^ { - 1 / 2 } ( x - x _ { c } )$ .)

# 2.3.3 Linear-fractional and perspective functions

In this section we explore a class of functions, called linear-fractional, that is more general than affine but still preserves convexity.

# The perspective function

We define the perspective function $P : \mathbf { R } ^ { n + 1 }  \mathbf { R } ^ { n }$ , with domain dom $P = \mathbf { R } ^ { n } \times$ $\mathbf { R } _ { + + }$ , as $P ( z , t ) = z / t$ . (Here $\mathbf { R } _ { + + }$ denotes the set of positive numbers: $\mathbf { R } _ { + + } =$ $\{ x \in \mathbf { R } \mid x > 0 \}$ .) The perspective function scales or normalizes vectors so the last component is one, and then drops the last component.

Remark 2.1 We can interpret the perspective function as the action of a pin-hole camera. A pin-hole camera (in $\mathbf { R } ^ { 3 }$ ) consists of an opaque horizontal plane $x _ { 3 } = 0$ , with a single pin-hole at the origin, through which light can pass, and a horizontal image plane $x _ { 3 } = - 1$ . An object at $x$ , above the camera (i.e., with $x _ { 3 } > 0$ ), forms an image at the point $- ( x _ { 1 } / x _ { 3 } , x _ { 2 } / x _ { 3 } , 1 )$ on the image plane. Dropping the last component of the image point (since it is always $^ { - 1 }$ ), the image of a point at $x$ appears at $y = - ( x _ { 1 } / x _ { 3 } , x _ { 2 } / x _ { 3 } ) = - P ( x )$ on the image plane. This is illustrated in figure 2.15.

If $C \subseteq \mathbf { d o m } P$ is convex, then its image

$$
P (C) = \{P (x) \mid x \in C \}
$$

is convex. This result is certainly intuitive: a convex object, viewed through a pin-hole camera, yields a convex image. To establish this fact we show that line segments are mapped to line segments under the perspective function. (This too

![](数学书/凸优化/images/929a04e367815282540b879e92805ba8c711f002af04d7a7cfb87f0755c0bc55.jpg)  
Figure 2.15 Pin-hole camera interpretation of perspective function. The dark horizontal line represents the plane $x _ { 3 } = 0$ in $\mathbf { R } ^ { 3 }$ , which is opaque, except for a pin-hole at the origin. Objects or light sources above the plane appear on the image plane $x _ { 3 } = - 1$ , which is shown as the lighter horizontal line. The mapping of the position of a source to the position of its image is related to the perspective function.

makes sense: a line segment, viewed through a pin-hole camera, yields a line segment image.) Suppose that $x = ( \tilde { x } , x _ { n + 1 } ) , \ y = ( \tilde { y } , y _ { n + 1 } ) \in \mathbf { R } ^ { n + 1 }$ with $x _ { n + 1 } > 0$ , $y _ { n + 1 } > 0$ . Then for $0 \leq \theta \leq 1$ ,

$$
P (\theta x + (1 - \theta) y) = \frac {\theta \tilde {x} + (1 - \theta) \tilde {y}}{\theta x _ {n + 1} + (1 - \theta) y _ {n + 1}} = \mu P (x) + (1 - \mu) P (y),
$$

where

$$
\mu = \frac {\theta x _ {n + 1}}{\theta x _ {n + 1} + (1 - \theta) y _ {n + 1}} \in [ 0, 1 ].
$$

This correspondence between $\theta$ and is monotonic: as $\theta$ varies between 0 and 1 $\mu$ (which sweeps out the line segment $[ x , y ]$ ), $\mu$ varies between 0 and 1 (which sweeps out the line segment $[ P ( x ) , P ( y ) ] )$ . This shows that $P ( [ x , y ] ) = [ P ( x ) , P ( y ) ]$ .

Now suppose $C$ is convex with $C \subseteq \mathbf { d o m } P$ (i.e., $x _ { n + 1 } > 0$ for all $x \in C$ ), and $x , \ y \in C$ . To establish convexity of $P ( C )$ we need to show that the line segment $[ P ( x ) , P ( y ) ]$ is in $P ( C )$ . But this line segment is the image of the line segment $[ x , y ]$ under $P$ , and so lies in $P ( C )$ .

The inverse image of a convex set under the perspective function is also convex: if $C \subseteq \mathbf { R } ^ { n }$ is convex, then

$$
P ^ {- 1} (C) = \{(x, t) \in \mathbf {R} ^ {n + 1} \mid x / t \in C, t > 0 \}
$$

is convex. To show this, suppose $( x , t ) \in P ^ { - 1 } ( C )$ , $( y , s ) \in P ^ { - 1 } ( C )$ , and $0 \leq \theta \leq 1$ . We need to show that

$$
\theta (x, t) + (1 - \theta) (y, s) \in P ^ {- 1} (C),
$$

i.e., that

$$
\frac {\theta x + (1 - \theta) y}{\theta t + (1 - \theta) s} \in C
$$

$( \theta t + ( 1 - \theta ) s > 0$ is obvious). This follows from

$$
\frac {\theta x + (1 - \theta) y}{\theta t + (1 - \theta) s} = \mu (x / t) + (1 - \mu) (y / s),
$$

where

$$
\mu = \frac {\theta t}{\theta t + (1 - \theta) s} \in [ 0, 1 ].
$$

# Linear-fractional functions

A linear-fractional function is formed by composing the perspective function with an affine function. Suppose $g : \mathbf { R } ^ { n }  \mathbf { R } ^ { m + 1 }$ is affine, i.e.,

$$
g (x) = \left[ \begin{array}{c} A \\ c ^ {T} \end{array} \right] x + \left[ \begin{array}{l} b \\ d \end{array} \right], \tag {2.12}
$$

where $A \in \mathbf { R } ^ { m \times n }$ , $b \in \mathbf { R } ^ { m }$ , $c \in \mathbf { R } ^ { n }$ , and $d \in \mathbf { R }$ . The function $f : \mathbf { R } ^ { n }  \mathbf { R } ^ { \prime \prime \iota }$ given by $f = P \circ g$ , i.e.,

$$
f (x) = (A x + b) / \left(c ^ {T} x + d\right), \quad \mathbf {d o m} f = \{x \mid c ^ {T} x + d > 0 \}, \tag {2.13}
$$

is called a linear-fractional (or projective) function. If $c = 0$ and $d > 0$ , the domain of $f$ is $\mathbf { R } ^ { n }$ , and $f$ is an affine function. So we can think of affine and linear functions as special cases of linear-fractional functions.

Remark 2.2 Projective interpretation. It is often convenient to represent a linearfractional function as a matrix

$$
Q = \left[ \begin{array}{c c} A & b \\ c ^ {T} & d \end{array} \right] \in \mathbf {R} ^ {(m + 1) \times (n + 1)} \tag {2.14}
$$

that acts on (multiplies) points of form $( x , 1 )$ , which yields $( A x + b , c ^ { T } x + d )$ . This result is then scaled or normalized so that its last component is one, which yields $( f ( x ) , 1 )$ .

This representation can be interpreted geometrically by associating $\mathbf { R } ^ { n }$ with a set of rays in $\mathbf { R } ^ { n + 1 }$ as follows. With each point $z$ in $\mathbf { R } ^ { n }$ we associate the (open) ray $\mathcal { P } ( z ) = \{ t ( z , 1 ) \mid t > 0 \}$ in $\mathbf { R } ^ { n + 1 }$ . The last component of this ray takes on positive values. Conversely any ray in $\mathbf { R } ^ { n + 1 }$ , with base at the origin and last component which takes on positive values, can be written as $\mathcal { P } ( v ) = \{ t ( v , 1 ) \mid t \geq 0 \}$ for some $v \in \mathbf { R } ^ { n }$ . This (projective) correspondence $\mathcal { P }$ between $\mathbf { R } ^ { n }$ and the halfspace of rays with positive last component is one-to-one and onto.

The linear-fractional function (2.13) can be expressed as

$$
f (x) = \mathcal {P} ^ {- 1} (Q \mathcal {P} (x)).
$$

Thus, we start with $x \in \mathbf { d o m } f$ , i.e., $c ^ { 2 } x + d > 0$ . We then form the ray $\mathcal { P } ( x )$ in $\mathbf { R } ^ { n + 1 }$ . The linear transformation with matrix $Q$ acts on this ray to produce another ray $Q \mathcal { P } ( x )$ . Since $x \in \mathbf { d o m } f$ , the last component of this ray assumes positive values. Finally we take the inverse projective transformation to recover $f ( x )$ .

![](数学书/凸优化/images/3d58fea6a664ee9ca60c9a7d37400013abef247540d1add5cfc9e3cea959597f.jpg)

![](数学书/凸优化/images/a062ec23ca313016fbf39396e8e23676b9965b468cb683f07bc5f0c793f95b7e.jpg)  
Figure 2.16 Left. A set $C \subseteq \mathbf { R } ^ { 2 }$ . The dashed line shows the boundary of the domain of the linear-fractional function $f ( x ) = x / ( x _ { 1 } + x _ { 2 } + 1 )$ with $\mathbf { d o m } f = \{ ( x _ { 1 } , x _ { 2 } ) \mid x _ { 1 } + x _ { 2 } + 1 > 0 \}$ . Right. Image of $C$ under $f$ . The dashed line shows the boundary of the domain of $f ^ { - 1 }$ .

Like the perspective function, linear-fractional functions preserve convexity. If $C$ is convex and lies in the domain of $f$ (i.e., $c ^ { T } x + d > 0$ for $x \in C$ ), then its image $f ( C )$ is convex. This follows immediately from results above: the image of $C$ under the affine mapping (2.12) is convex, and the image of the resulting set under the perspective function $P$ , which yields $f ( C )$ , is convex. Similarly, if $C \subseteq \mathbf { R } ^ { m }$ i s convex, then the inverse image $f ^ { - 1 } ( C )$ is convex.

Example 2.13 Conditional probabilities. Suppose $u$ and $\boldsymbol { v }$ are random variables that take on values in $\{ 1 , \ldots , n \}$ and $\{ 1 , \ldots , m \}$ , respectively, and let $p _ { i j }$ denote $\mathbf { p r o b } ( u = i , v = j )$ ). Then the conditional probability $f _ { i j } = \mathbf { p r o b } ( u = i | v = j $ ) is given by

$$
f _ {i j} = \frac {p _ {i j}}{\sum_ {k = 1} ^ {n} p _ {k j}}.
$$

Thus $f$ is obtained by a linear-fractional mapping from $p$ .

It follows that if $C$ is a convex set of joint probabilities for $( u , v )$ , then the associated set of conditional probabilities of $_ u$ given $v$ is also convex.

Figure 2.16 shows a set $C \subseteq \mathbf { R } ^ { 2 }$ , and its image under the linear-fractional function

$$
f (x) = \frac {1}{x _ {1} + x _ {2} + 1} x, \quad \mathbf {d o m} f = \left\{\left(x _ {1}, x _ {2}\right) \mid x _ {1} + x _ {2} + 1 > 0 \right\}.
$$

# 2.4 Generalized inequalities

# 2.4.1 Proper cones and generalized inequalities

A cone $K \subseteq \mathbf { R } ^ { \pi }$ is called a proper cone if it satisfies the following:

• $K$ is convex.   
• $K$ is closed.   
• $K$ is solid, which means it has nonempty interior.   
• $K$ is pointed, which means that it contains no line (or equivalently, $x \in$ $K , \ - x \in K \implies x = 0$ ).

A proper cone $K$ can be used to define a generalized inequality, which is a partial ordering on $\mathbf { R } ^ { n }$ that has many of the properties of the standard ordering on $\mathbf { R }$ . We associate with the proper cone $K$ the partial ordering on $\mathbf { R } ^ { n }$ defined by

$$
x \preceq_ {K} y \iff y - x \in K.
$$

We also write $x \succeq _ { K } y$ for $y \preceq _ { K } x$ . Similarly, we define an associated strict partial ordering by

$$
x \prec_ {K} y \iff y - x \in \operatorname {i n t} K,
$$

and write $x \ \succ _ { K } \ y$ for $y \prec _ { K } x$ . (To distinguish the generalized inequality $\preceq _ { K }$ from the strict generalized inequality, we sometimes refer to $\preceq _ { K }$ as the nonstrict generalized inequality.)

When $K = { \bf R } _ { + }$ , the partial ordering $\preceq _ { K }$ is the usual ordering $\leq$ on $\mathbf { R }$ , and the strict partial ordering $\prec _ { K }$ is the same as the usual strict ordering $<$ < on $\mathbf { R }$ . So generalized inequalities include as a special case ordinary (nonstrict and strict) inequality in $\mathbf { R }$ .

Example 2.14 Nonnegative orthant and componentwise inequality. The nonnegative orthant ${ \cal K } = { \bf R } _ { + } ^ { n }$ is a proper cone. The associated generalized inequality $\preceq _ { K }$ corresponds to componentwise inequality between vectors: $x \preceq _ { K } ~ y$ means that $x _ { i } \ \leq \ y _ { i }$ , $i = 1 , \ldots , n$ . The associated strict inequality corresponds to componentwise strict inequality: $x \prec \kappa \ y$ means that $x _ { i } < y _ { i }$ , $i = 1 , \ldots , n$ .

The nonstrict and strict partial orderings associated with the nonnegative orthant arise so frequently that we drop the subscript ${ \bf R } _ { + } ^ { n }$ ; it is understood when the symbol $\preceq$ or $\prec$ appears between vectors.

Example 2.15 Positive semidefinite cone and matrix inequality. The positive semidefinite cone $\mathbf { S } _ { + } ^ { n }$ is a proper cone in $\mathbf { S } ^ { n }$ . The associated generalized inequality $\preceq _ { K }$ is the usual matrix inequality: $X ~ \preceq _ { K } ~ Y$ means $Y \ - \ X$ is positive semidefinite. The interior of $\mathbf { S } _ { + } ^ { n }$ (in $\mathbf { S } ^ { n }$ ) consists of the positive definite matrices, so the strict generalized inequality also agrees with the usual strict inequality between symmetric matrices: $X \prec _ { K } Y$ means $Y - X$ is positive definite.

Here, too, the partial ordering arises so frequently that we drop the subscript: for symmetric matrices we write simply $X ~ \preceq ~ Y$ or $X ~ \prec ~ Y$ . It is understood that the generalized inequalities are with respect to the positive semidefinite cone.

Example 2.16 Cone of polynomials nonnegative on $\lfloor 0 , 1 \rfloor$ . Let $K$ be defined as

$$
K = \left\{c \in \mathbf {R} ^ {n} \mid c _ {1} + c _ {2} t + \dots + c _ {n} t ^ {n - 1} \geq 0 \text {f o r} t \in [ 0, 1 ] \right\}, \tag {2.15}
$$

i.e., $K$ is the cone of (coefficients of) polynomials of degree $n - 1$ that are nonnegative on the interval [0, 1]. It can be shown that $K$ is a proper cone; its interior is the set of coefficients of polynomials that are positive on the interval $\lfloor 0 , 1 \rfloor$ .

Two vectors $c , d \in \mathbf { R } ^ { n }$ satisfy $c \preceq _ { K }$ d if and only if

$$
c _ {1} + c _ {2} t + \dots + c _ {n} t ^ {n - 1} \leq d _ {1} + d _ {2} t + \dots + d _ {n} t ^ {n - 1}
$$

for all $t \in [ 0 , 1 ]$ .

# Properties of generalized inequalities

A generalized inequality $\preceq _ { K }$ satisfies many properties, such as

• $\preceq _ { K }$ is preserved under addition: if $x \preceq _ { K } y$ and $u \preceq _ { K } v$ , then $x + u \preceq _ { K } y + v$ .   
• $\preceq _ { K }$ is transitive: if $x \preceq _ { K } y$ and $y \preceq _ { K } z$ then $x \preceq _ { K } z$ .   
• $\preceq _ { K }$ is preserved under nonnegative scaling: if $x ~ \preceq _ { K } ~ y$ and $\alpha \geq 0$ then αx K αy.   
• $\preceq _ { K }$ is reflexive: $x \preceq _ { K } x$   
• $\preceq _ { K }$ is antisymmetric: if $x \preceq _ { K } y$ and $y \preceq _ { K } x$ , then $x = y$ .   
• $\preceq _ { K }$ is preserved under limits: if $x _ { i } \preceq _ { K }$ yi for $i = 1 , \ 2 , \ldots$ , $x _ { i }  x$ and $y _ { i } \to y$ as $i \to \infty$ , then $x \preceq _ { K } y$ .

The corresponding strict generalized inequality $\prec _ { K }$ satisfies, for example,

• if $x \prec _ { K } y$ then $x \preceq _ { K } y$ .   
• if $x \prec _ { K } y$ and $u \preceq _ { K } v$ then $x + u \prec _ { K } y + v$ .   
• if $x \prec _ { K } y$ and $\alpha > 0$ then $\alpha x \prec _ { K } \alpha y$ .   
• $x \not \prec _ { K } x$ .   
• if $x \prec _ { K } y$ , then for $u$ and $\boldsymbol { v }$ small enough, $x + u \prec _ { K } y + v$ .

These properties are inherited from the definitions of $\preceq _ { K }$ and $\prec _ { K }$ , and the properties of proper cones; see exercise 2.30.

# 2.4.2 Minimum and minimal elements

The notation of generalized inequality (i.e., $\preceq _ { K }$ , $\prec _ { K }$ ) is meant to suggest the analogy to ordinary inequality on $\mathbf { R } \left( i . e . , \leq , < \right)$ $\mathbf { R }$ . While many properties of ordinary inequality do hold for generalized inequalities, some important ones do not. The most obvious difference is that $\leq$ on $\mathbf { R }$ is a linear ordering: any two points are comparable, meaning either $x \ \leq \ y$ or $y \ \leq \ x$ . This property does not hold for other generalized inequalities. One implication is that concepts like minimum and maximum are more complicated in the context of generalized inequalities. We briefly discuss this in this section.

We say that $x \in S$ is the minimum element of $S$ (with respect to the generalized inequality $\preceq _ { K }$ ) if for every $y \in S$ we have $x \preceq _ { K } y$ . We define the maximum element of a set $S$ , with respect to a generalized inequality, in a similar way. If a set has a minimum (maximum) element, then it is unique. A related concept is minimal element. We say that $x \in S$ is a minimal element of $S$ (with respect to the generalized inequality $\preceq _ { K }$ ) if $y \in S$ , $y \preceq _ { K } ~ x$ only if $y = x$ . We define maximal element in a similar way. A set can have many different minimal (maximal) elements.

We can describe minimum and minimal elements using simple set notation. A point $x \in S$ is the minimum element of $S$ if and only if

$$
S \subseteq x + K.
$$

Here $x + K$ denotes all the points that are comparable to $x$ and greater than or equal to $x$ (according to $\preceq _ { K }$ ). A point $x \in S$ is a minimal element if and only if

$$
(x - K) \cap S = \{x \}.
$$

Here $x - K$ denotes all the points that are comparable to $x$ and less than or equal to $x$ (according to $\preceq _ { K }$ ); the only point in common with $S$ is $x$ .

For $K = { \bf R } _ { + }$ , which induces the usual ordering on $\mathbf { R }$ , the concepts of minimal and minimum are the same, and agree with the usual definition of the minimum element of a set.

Example 2.17 Consider the cone ${ \bf R } _ { + } ^ { 2 }$ , which induces componentwise inequality in $\mathbf { R } ^ { 2 }$ . Here we can give some simple geometric descriptions of minimal and minimum elements. The inequality $x \preceq y$ means $y$ is above and to the right of $_ { x }$ . To say that $x \in S$ is the minimum element of a set $S$ means that all other points of $S$ lie above and to the right. To say that $_ { x }$ is a minimal element of a set $S$ means that no other point of $S$ lies to the left and below $_ { x }$ . This is illustrated in figure 2.17.

Example 2.18 Minimum and minimal elements of a set of symmetric matrices. We associate with each $A \in \mathbf { S } _ { + + } ^ { n }$ an ellipsoid centered at the origin, given by

$$
\mathcal {E} _ {A} = \{x \mid x ^ {T} A ^ {- 1} x \leq 1 \}.
$$

We have $A \preceq B$ if and only if $\mathcal { E } _ { A } \subseteq \mathcal { E } _ { B }$ .

Let $v _ { 1 } , \ldots , v _ { k } \in \mathbf { R } ^ { n }$ be given and define

$$
S = \left\{P \in \mathbf {S} _ {+ +} ^ {n} \mid v _ {i} ^ {T} P ^ {- 1} v _ {i} \leq 1, i = 1, \dots , k \right\},
$$

![](数学书/凸优化/images/adb9cd897c13a502c1da65295ed8c29edd81f598331a36ead85b918594c47789.jpg)

![](数学书/凸优化/images/cedd8ef56e71d2ea2ee84bbb2e37d842060cb2467cf6ccb4eda411be67a28d97.jpg)  
Figure 2.17 Left. The set $S _ { 1 }$ has a minimum element $x _ { 1 }$ with respect to componentwise inequality in $\mathbf { R } ^ { 2 }$ . The set $x _ { 1 } + K$ is shaded lightly; $x _ { 1 }$ is the minimum element of $S _ { 1 }$ since $S _ { 1 } \subseteq x _ { 1 } + K$ . Right. The point $x _ { 2 }$ is a minimal point of $S _ { 2 }$ . The set $x _ { 2 } - K$ is shown lightly shaded. The point $x _ { 2 }$ is minimal because $x _ { 2 } - K$ and $S _ { 2 }$ intersect only at $x _ { 2 }$ .

which corresponds to the set of ellipsoids that contain the points $v _ { 1 } , \ldots , v _ { k }$ . The set $S$ does not have a minimum element: for any ellipsoid that contains the points $v _ { 1 } , \ldots , v _ { k }$ we can find another one that contains the points, and is not comparable to it. An ellipsoid is minimal if it contains the points, but no smaller ellipsoid does. Figure 2.18 shows an example in $\mathbf { R } ^ { 2 }$ with $k = 2$ .

# 2.5 Separating and supporting hyperplanes

# 2.5.1 Separating hyperplane theorem

In this section we describe an idea that will be important later: the use of hyperplanes or affine functions to separate convex sets that do not intersect. The basic result is the separating hyperplane theorem: Suppose $C$ and $D$ are nonempty disjoint convex sets, i.e., $C \cap D = \emptyset$ . Then there exist $a \neq 0$ and $b$ such that $a ^ { T } x \leq b$ for all $x \in C$ and $a ^ { T } x \geq b$ for all $x \in D$ . In other words, the affine function $a ^ { \mathrm { T } } x - b$ is nonpositive on $C$ and nonnegative on $D$ . The hyperplane $\{ x \mid a ^ { \prime } x = b \}$ is called a separating hyperplane for the sets $C$ and $D$ , or is said to separate the sets $C$ and $D$ . This is illustrated in figure 2.19.

# Proof of separating hyperplane theorem

Here we consider a special case, and leave the extension of the proof to the general case as an exercise (exercise 2.22). We assume that the (Euclidean) distance between $C$ and $D$ , defined as

$$
\operatorname {d i s t} (C, D) = \inf  \left\{\| u - v \| _ {2} \mid u \in C, v \in D \right\},
$$

![](数学书/凸优化/images/7cf77ecd1a8705e28c715e3d3f6c2e717402f63ceb246c66f8f59db8adc4ef08.jpg)  
Figure 2.18 Three ellipsoids in $\mathbf { R } ^ { 2 }$ , centered at the origin (shown as the lower dot), that contain the points shown as the upper dots. The ellipsoid $\mathcal { E } _ { 1 }$ is not minimal, since there exist ellipsoids that contain the points, and are smaller (e.g., $\xi _ { 3 }$ ). $\xi _ { 3 }$ is not minimal for the same reason. The ellipsoid $\xi _ { 2 }$ is minimal, since no other ellipsoid (centered at the origin) contains the points and is contained in $\xi _ { 2 }$ .

![](数学书/凸优化/images/cfb648836e79ce61b82eb257af7fbf4daa009924c3406b793162ee699804d865.jpg)  
Figure 2.19 The hyperplane $\{ x \mid a ^ { \prime } x = b \}$ separates the disjoint convex sets $C$ and $D$ . The affine function $\boldsymbol { a } ^ { T } \boldsymbol { x } - \boldsymbol { b }$ is nonpositive on $C$ and nonnegative on $D$ .

![](数学书/凸优化/images/87553c15939da66fa2bc66de0bbd5fc3346a3d3029af2855612a187ef0a0c229.jpg)  
Figure 2.20 Construction of a separating hyperplane between two convex sets. The points $c \in C$ and $d \in D$ are the pair of points in the two sets that are closest to each other. The separating hyperplane is orthogonal to, and bisects, the line segment between $c$ and $d$ .

is positive, and that there exist points $c \in C$ and $d \in D$ that achieve the minimum distance, i.e., $\| c - d \| _ { 2 } = \mathbf { d i s t } ( C , D )$ . (These conditions are satisfied, for example, when $C$ and $D$ are closed and one set is bounded.)

Define

$$
a = d - c, \qquad b = \frac {\| d \| _ {2} ^ {2} - \| c \| _ {2} ^ {2}}{2}.
$$

We will show that the affine function

$$
f (x) = a ^ {T} x - b = (d - c) ^ {T} (x - (1 / 2) (d + c))
$$

is nonpositive on $C$ and nonnegative on $D$ , i.e., that the hyperplane $\{ x \mid a ^ { \prime } x = b \}$ separates $C$ and $D$ . This hyperplane is perpendicular to the line segment between $c$ and $d$ , and passes through its midpoint, as shown in figure 2.20.

We first show that $f$ is nonnegative on $D$ . The proof that $f$ is nonpositive on $C$ is similar (or follows by swapping $C$ and $D$ and considering $- f$ ). Suppose there were a point $u \in D$ for which

$$
f (u) = \left(d - c\right) ^ {T} \left(u - (1 / 2) (d + c)\right) <   0. \tag {2.16}
$$

We can express $f ( u )$ as

$$
f (u) = \left(d - c\right) ^ {T} (u - d + (1 / 2) (d - c)) = \left(d - c\right) ^ {T} (u - d) + (1 / 2) \| d - c \| _ {2} ^ {2}.
$$

We see that (2.16) implies $( d - c ) ^ { T } ( u - d ) < 0$ . Now we observe that

$$
\frac{d}{dt}\| d + t(u - d) - c\|_{2}^{2}\bigg|_{t = 0} = 2(d - c)^{T}(u - d) <   0,
$$

so for some small $t > 0$ , with $t \leq 1$ , we have

$$
\left\| d + t (u - d) - c \right\| _ {2} <   \left\| d - c \right\| _ {2},
$$

i.e., the point $d + t ( u - d )$ is closer to $c$ than $d$ is. Since $D$ is convex and contains $d$ and $u$ , we have $d + t ( u - d ) \in D$ . But this is impossible, since $d$ is assumed to be the point in $D$ that is closest to $C$ .

Example 2.19 Separation of an affine and a convex set. Suppose $C$ is convex and $D$ is affine, i.e., $D = \{ F u + g \mid u \in \mathbf { R } ^ { m } \}$ , where $F \in \mathbf { R } ^ { n \times m }$ . Suppose $C$ and $D$ are disjoint, so by the separating hyperplane theorem there are $a \neq 0$ and $b$ such that $a ^ { x } x \leq b$ for all $x \in C$ and $a ^ { x } x \geq b$ for all $x \in D$ .

Now $a ^ { 2 } x \geq b$ for all $x \in D$ means $a ^ { T } F u \geq b - a ^ { T } g$ for all $u \in \mathbf { R } ^ { m }$ . But a linear function is bounded below on $\mathbf { R } ^ { m }$ only when it is zero, so we conclude $a ^ { 2 } F = 0$ (and hence, $b \leq a ^ { 2 } \overset { \prime } { \cdot } g$ ).

Thus we conclude that there exists $a \neq 0$ such that $F ^ { T } a = 0$ and $a ^ { \prime } x \leq a ^ { \prime } g$ for all $x \in C$ .

# Strict separation

The separating hyperplane we constructed above satisfies the stronger condition that $a ^ { T } x \ < \ b$ for all $x \in C$ and $a ^ { \mathrm { ' } } x > b$ for all $x \in D$ . This is called strict separation of the sets $C$ and $D$ . Simple examples show that in general, disjoint convex sets need not be strictly separable by a hyperplane (even when the sets are closed; see exercise 2.23). In many special cases, however, strict separation can be established.

Example 2.20 Strict separation of a point and a closed convex set. Let $C$ be a closed convex set and $x _ { 0 } \notin { \cal { C } }$ . Then there exists a hyperplane that strictly separates $x _ { 0 }$ from $C$ .

To see this, note that the two sets $C$ and $B ( x _ { 0 } , \epsilon )$ do not intersect for some $\epsilon > 0$ . By the separating hyperplane theorem, there exist $a \neq 0$ and $b$ such that $a ^ { x } x \leq b$ for $x \in C$ and $a ^ { x } x \geq b$ for $x \in B ( x _ { 0 } , \epsilon )$ .

Using $B ( x _ { 0 } , \epsilon ) = \{ x _ { 0 } + u \mid \| u \| _ { 2 } \leq \epsilon \}$ , the second condition can be expressed as

$$
a ^ {T} \left(x _ {0} + u\right) \geq b \text {f o r a l l} \| u \| _ {2} \leq \epsilon .
$$

The $u$ that minimizes the lefthand side is $u = - \epsilon a / \| a \| _ { 2 }$ ; using this value we have

$$
a ^ {T} x _ {0} - \epsilon \| a \| _ {2} \geq b.
$$

Therefore the affine function

$$
f (x) = a ^ {T} x - b - \epsilon \| a \| _ {2} / 2
$$

is negative on $C$ and positive at $x _ { 0 }$ .

As an immediate consequence we can establish a fact that we already mentioned above: a closed convex set is the intersection of all halfspaces that contain it. Indeed, let $C$ be closed and convex, and let $S$ be the intersection of all halfspaces containing $C$ . Obviously $x \in C \Rightarrow x \in S$ . To show the converse, suppose there exists $x \in S$ , $x \not \in C$ . By the strict separation result there exists a hyperplane that strictly separates $x$ from $C$ , i.e., there is a halfspace containing $C$ but not $_ { x }$ . In other words, $x \not \in S$ .

# Converse separating hyperplane theorems

The converse of the separating hyperplane theorem (i.e., existence of a separating hyperplane implies that $C$ and $D$ do not intersect) is not true, unless one imposes additional constraints on $C$ or $D$ , even beyond convexity. As a simple counterexample, consider $C = D = \{ 0 \} \subseteq \mathbf { R }$ . Here the hyperplane $x = 0$ separates $C$ and $D$ .

By adding conditions on $C$ and $D$ various converse separation theorems can be derived. As a very simple example, suppose $C$ and $D$ are convex sets, with $C$ open, and there exists an affine function $f$ that is nonpositive on $C$ and nonnegative on $D$ . Then $C$ and $D$ are disjoint. (To see this we first note that $f$ must be negative on $C$ ; for if $f$ were zero at a point of $C$ then $f$ would take on positive values near the point, which is a contradiction. But then $C$ and $D$ must be disjoint since $f$ is negative on $C$ and nonnegative on $D$ .) Putting this converse together with the separating hyperplane theorem, we have the following result: any two convex sets $C$ and $D$ , at least one of which is open, are disjoint if and only if there exists a separating hyperplane.

Example 2.21 Theorem of alternatives for strict linear inequalities. We derive the necessary and sufficient conditions for solvability of a system of strict linear inequalities

$$
A x \prec b. \tag {2.17}
$$

These inequalities are infeasible if and only if the (convex) sets

$$
C = \left\{b - A x \mid x \in \mathbf {R} ^ {n} \right\}, \qquad D = \mathbf {R} _ {+ +} ^ {m} = \left\{y \in \mathbf {R} ^ {m} \mid y \succ 0 \right\}
$$

do not intersect. The set $D$ is open; $C$ is an affine set. Hence by the result above, $C$ and $D$ are disjoint if and only if there exists a separating hyperplane, i.e., a nonzero $\lambda \in \mathbf { R } ^ { m }$ and $\boldsymbol { \mu } \in \mathbf { R }$ such that $\lambda ^ { \prime } y \leq \mu$ on $C$ and $\lambda ^ { \prime } \boldsymbol { y } \geq \mu$ on $D$ .

Each of these conditions can be simplified. The first means $\lambda ^ { \prime } ( b - A x ) \leq \mu$ for all $_ { x }$ . This implies (as in example 2.19) that $A ^ { T } \lambda = 0$ and $\lambda ^ { T } b \leq \mu$ . The second inequality means $\lambda ^ { \prime } \boldsymbol { y } \geq \mu$ for all $y \succ 0$ . This implies $\mu \leq 0$ and $\lambda \succeq 0$ , $\lambda \neq 0$ .

Putting it all together, we find that the set of strict inequalities (2.17) is infeasible if and only if there exists $\lambda \in \mathbf { R } ^ { m }$ such that

$$
\lambda \neq 0, \quad \lambda \succeq 0, \quad A ^ {T} \lambda = 0, \quad \lambda^ {T} b \leq 0. \tag {2.18}
$$

This is also a system of linear inequalities and linear equations in the variable $\lambda \in \mathbf { R } ^ { m }$ . We say that (2.17) and (2.18) form a pair of alternatives: for any data $A$ and $^ { b }$ , exactly one of them is solvable.

# 2.5.2 Supporting hyperplanes

Suppose $C \subseteq \mathbf { R } ^ { n }$ , and $x _ { 0 }$ is a point in its boundary $\mathbf { b d } C$ , i.e.,

$$
x _ {0} \in \operatorname {b d} C = \operatorname {c l} C \backslash \operatorname {i n t} C.
$$

If $a \neq 0$ satisfies $a ^ { \scriptscriptstyle T } x \le a ^ { \scriptscriptstyle T } x _ { 0 }$ for all $x \in C$ , then the hyperplane $\{ x \mid a ^ { \prime } x = a ^ { \prime } x _ { 0 } \}$ is called a supporting hyperplane to $C$ at the point $x _ { 0 }$ . This is equivalent to saying

![](数学书/凸优化/images/6eb9023b4bf6738a9aa9556b805c95d12ea97b65cd0751dc51d05cadabe4e16d.jpg)  
Figure 2.21 The hyperplane $\{ x \mid a ^ { \prime } x = a ^ { \prime } x _ { 0 } \}$ supports $C$ at $x _ { 0 }$

that the point $x _ { 0 }$ and the set $C$ are separated by the hyperplane $\{ x \mid a ^ { \prime } x = a ^ { \prime } x _ { 0 } \}$ . The geometric interpretation is that the hyperplane $\{ x \mid a ^ { \mathcal { I } } x = a ^ { \mathcal { I } } x _ { 0 } \}$ is tangent to $C$ at $x _ { 0 }$ , and the halfspace $\{ x \mid a ^ { \mathcal { I } } x \leq a ^ { \mathcal { I } } x _ { 0 } \}$ contains $C$ . This is illustrated in figure 2.21.

A basic result, called the supporting hyperplane theorem, states that for any nonempty convex set $C$ , and any $x _ { 0 } \in \mathbf { b d } C$ , there exists a supporting hyperplane to $C$ at $x _ { 0 }$ . The supporting hyperplane theorem is readily proved from the separating hyperplane theorem. We distinguish two cases. If the interior of $C$ is nonempty, the result follows immediately by applying the separating hyperplane theorem to the sets $\{ x _ { 0 } \}$ and $\mathbf { i n t } C$ . If the interior of $C$ is empty, then $C$ must lie in an affine set of dimension less than $n$ , and any hyperplane containing that affine set contains $C$ and $x _ { 0 }$ , and is a (trivial) supporting hyperplane.

There is also a partial converse of the supporting hyperplane theorem: If a set is closed, has nonempty interior, and has a supporting hyperplane at every point in its boundary, then it is convex. (See exercise 2.27.)


# 2.6 Dual cones and generalized inequalities

# 2.6.1 Dual cones

Let $K$ be a cone. The set

$$
K ^ {*} = \left\{y \mid x ^ {T} y \geq 0 \text {f o r a l l} x \in K \right\} \tag {2.19}
$$

is called the dual cone of $K$ . As the name suggests, $K ^ { * }$ is a cone, and is always convex, even when the original cone $K$ is not (see exercise 2.31).

Geometrically, $y \in K ^ { * }$ if and only if $- y$ is the normal of a hyperplane that supports $K$ at the origin. This is illustrated in figure 2.22.

![](数学书/凸优化/images/a5890b3dcbe796bedc7999b8c4341c890b4f7e1e16c190b19cd433d5f56b9712.jpg)

![](数学书/凸优化/images/8e9e2eb0549c199cf05c7bce154cca22496a0f44c3856d37830881edb6f95fb1.jpg)  
Figure 2.22 Left. The halfspace with inward normal $y$ contains the cone $K$ , so $y \in K ^ { * }$ . Right. The halfspace with inward normal $z$ does not contain $K$ , so $z \not \in K ^ { * }$ .

Example 2.23 Nonnegative orthant. The cone $\mathbf { R } _ { + } ^ { n }$ is its own dual:

$$
x ^ {T} y \geq 0 \text {f o r a l l} x \succeq 0 \iff y \succeq 0.
$$

We call such a cone self-dual.

Example 2.24 Positive semidefinite cone. On the set of symmetric $n \times n$ matrices $\mathbf { S } ^ { n }$ , we use the standard inner product $\begin{array} { r } { \mathbf { t r } ( X Y ) = \sum _ { i , j = 1 } ^ { n } X _ { i j } Y _ { i j } } \end{array}$ Pni,j=1 XijYij (see §A.1.1). The positive semidefinite cone $\mathbf { S } _ { + } ^ { n }$ is self-dual, i.e., for $X$ , $Y \in \mathbf { S } ^ { n }$ ,

$$
\operatorname {t r} (X Y) \geq 0 \text {f o r a l l} X \succeq 0 \iff Y \succeq 0.
$$

We will establish this fact.

Suppose $Y \not \in { \mathbf { S } } _ { + } ^ { n }$ . Then there exists $q \in \mathbf { R } ^ { n }$ with

$$
q ^ {T} Y q = \mathbf {t r} (q q ^ {T} Y) <   0.
$$

Hence the positive semidefinite matrix $X = q q ^ { T }$ satisfies $\mathbf { t r } ( X Y ) < 0$ ; it follows that $Y \not \in ( \mathbf { S } _ { + } ^ { n } ) ^ { * }$ .

as Now suppose $\begin{array} { r } { X = \sum _ { i = 1 } ^ { n } \lambda _ { i } q _ { i } q _ { i } ^ { T } } \end{array}$ $X$ , $Y \in { \bf S } _ { + } ^ { n }$ . We can express ere (the eigenvalues) $X$ in terms of its eigenvalue decomposition $\lambda _ { i } \geq 0$ , $i = 1 , \ldots , n$ . Then we have

$$
\mathbf {t r} (Y X) = \mathbf {t r} \left(Y \sum_ {i = 1} ^ {n} \lambda_ {i} q _ {i} q _ {i} ^ {T}\right) = \sum_ {i = 1} ^ {n} \lambda_ {i} q _ {i} ^ {T} Y q _ {i} \geq 0.
$$

This shows that $Y \in ( \mathbf { S } _ { + } ^ { n } ) ^ { * }$ .

Example 2.25 Dual of a norm cone. Let $| | \cdot | |$ be a norm on $\mathbf { R } ^ { n }$ . The dual of the associated cone $K = \left\{ ( x , t ) \in \mathbf { R } ^ { n + 1 } \mid \left. x \right. \leq t \right\}$ is the cone defined by the dual norm, i.e.,

$$
K ^ {*} = \{(u, v) \in \mathbf {R} ^ {n + 1} \mid \| u \| _ {*} \leq v \},
$$

where the dual norm is given by $\| u \| _ { * } = \operatorname* { s u p } \{ u ^ { T } x \mid \| x \| \leq 1 \}$ (see (A.1.6)).

To prove the result we have to show that

$$
x ^ {T} u + t v \geq 0 \text {w h e n e v e r} \| x \| \leq t \Longleftrightarrow \| u \| _ {*} \leq v. \tag {2.20}
$$

Let us start by showing that the righthand condition on $( u , v )$ implies the lefthand condition. Suppose $\| u \| _ { * } \leq v$ , and $\| x \| \leq t$ for some $t > 0$ . (If $t = 0$ , $_ { x }$ must be zero, so obviously $u ^ { T } x + v t \geq 0$ .) Applying the definition of the dual norm, and the fact that $\| - x / t \| \leq 1$ , we have

$$
u ^ {T} (- x / t) \leq \| u \| _ {*} \leq v,
$$

and therefore $u ^ { x } + v t \geq 0$ .

Next we show that the lefthand condition in (2.20) implies the righthand condition in (2.20). Suppose $\left\| u \right\| _ { * } > v$ , i.e., that the righthand condition does not hold. Then by the definition of the dual norm, there exists an $x$ with $\| x \| \leq 1$ and $x ^ { T } u > v$ . Taking $t = 1$ , we have

$$
u ^ {T} (- x) + v <   0,
$$

which contradicts the lefthand condition in (2.20).

Dual cones satisfy several properties, such as:

• $K ^ { * }$ is closed and convex.   
• $K _ { 1 } \subseteq K _ { 2 }$ implies $K _ { 2 } ^ { * } \subseteq K _ { 1 } ^ { * }$ .   
• If $K$ has nonempty interior, then $K ^ { * }$ is pointed.   
• If the closure of $K$ is pointed then $K ^ { * }$ has nonempty interior.   
• $K ^ { * * }$ is the closure of the convex hull of $K$ . (Hence if $K$ is convex and closed, $K ^ { * * } = K$ .)

(See exercise 2.31.) These properties show that if $K$ is a proper cone, then so is its dual $K ^ { * }$ , and moreover, that $K ^ { * * } = K$ .

# 2.6.2 Dual generalized inequalities

Now suppose that the convex cone $K$ is proper, so it induces a generalized inequality $\preceq _ { K }$ . Then its dual cone $K ^ { * }$ is also proper, and therefore induces a generalized inequality. We refer to the generalized inequality $\preceq _ { K ^ { * } }$ as the dual of the generalized inequality $\preceq _ { K }$ .

Some important properties relating a generalized inequality and its dual are:

• $x \preceq _ { K } y$ if and only if $\lambda ^ { T } x \le \lambda ^ { T } y$ for all $\lambda \succeq _ { K ^ { * } } 0$ .   
• $x \prec _ { K } y$ if and only if $\lambda ^ { T } x < \lambda ^ { T } y$ for all $\lambda \succeq _ { K ^ { * } } 0$ , $\lambda \neq 0$ .

Since $K = K ^ { * * }$ , the dual generalized inequality associated with $\preceq _ { K ^ { * } }$ is $\preceq _ { K }$ , so these properties hold if the generalized inequality and its dual are swapped. As a specific example, we have $\lambda \preceq _ { K ^ { * } }$ $\mu$ if and only if $\lambda ^ { T } x \leq \mu ^ { T } x$ for all $x \succeq _ { K }$ 0.

Example 2.26 Theorem of alternatives for linear strict generalized inequalities. Suppose $K \subseteq \mathbf { R } ^ { m }$ is a proper cone. Consider the strict generalized inequality

$$
A x \prec_ {K} b, \tag {2.21}
$$

where $x \in \mathbf { R } ^ { n }$ .

We will derive a theorem of alternatives for this inequality. Suppose it is infeasible, i.e., the affine set $\{ b - A x \mid x \in \mathbf { R } ^ { n } \}$ does not intersect the open convex set $\operatorname { i n t } K$ . Then there is a separating hyperplane, i.e., a nonzero $\lambda \in \mathbf { R } ^ { m }$ and $\mu \in \mathbf { R }$ such that $\lambda ^ { T } ( b - A x ) \leq \mu$ for all $x$ , and $\lambda ^ { \mathrm { { \scriptscriptstyle T } } } y \geq \mu$ for all $y \in \mathbf { i n t } K$ . The first condition implies $A ^ { T } \lambda = 0$ and $\lambda ^ { T } b \leq \mu$ . The second condition implies $\lambda ^ { \prime } \boldsymbol { y } \geq \mu$ for all $y \in K$ , which can only happen if $\lambda \in K ^ { * }$ and $\mu \leq 0$ .

Putting it all together we find that if (2.21) is infeasible, then there exists $\lambda$ such that

$$
\lambda \neq 0, \quad \lambda \succeq_ {K ^ {*}} 0, \quad A ^ {T} \lambda = 0, \quad \lambda^ {T} b \leq 0. \tag {2.22}
$$

Now we show the converse: if (2.22) holds, then the inequality system (2.21) cannot be feasible. Suppose that both inequality systems hold. Then we have $\lambda ^ { T } ( b - A x ) >$ $_ 0$ , since $\lambda \neq 0$ , $\lambda \succeq _ { K ^ { * } } 0$ , and $b - A x \ \succ _ { K } \ 0$ . But using $A ^ { \mathrm { T } } \lambda = 0$ we find that $\lambda ^ { T } ( b - A x ) = \lambda ^ { T } b \leq 0$ , which is a contradiction.

Thus, the inequality systems (2.21) and (2.22) are alternatives: for any data $A$ , $b$ , exactly one of them is feasible. (This generalizes the alternatives (2.17), (2.18) for the special case $K = { \bf R } _ { + } ^ { m }$ . )

# 2.6.3 Minimum and minimal elements via dual inequalities

We can use dual generalized inequalities to characterize minimum and minimal elements of a (possibly nonconvex) set $S \subseteq \mathbf { R } ^ { \prime \prime \iota }$ with respect to the generalized inequality induced by a proper cone $K$ .

# Dual characterization of minimum element

We first consider a characterization of the minimum element: $x$ is the minimum element of $S$ , with respect to the generalized inequality $\preceq _ { K }$ , if and only if for all $\lambda \succ _ { K ^ { * } } 0$ , $x$ is the unique minimizer of $\lambda ^ { T } z$ over $z \in S$ . Geometrically, this means that for any $\lambda \succ _ { K ^ { * } }$ 0, the hyperplane

$$
\left\{z \mid \lambda^ {T} (z - x) = 0 \right\}
$$

is a strict supporting hyperplane to $S$ at $x$ . (By strict supporting hyperplane, we mean that the hyperplane intersects $S$ only at the point $x$ .) Note that convexity of the set $S$ is not required. This is illustrated in figure 2.23.

To show this result, suppose $x$ is the minimum element of $S$ , i.e., $x \preceq _ { K } z$ for all $z \in S$ , and let $\lambda \succ _ { K ^ { * } }$ 0. Let $z \in S$ , $z \neq x$ . Since $x$ is the minimum element of $S$ , we have $z - x \succeq _ { K } 0$ . From $\lambda \succ _ { K ^ { * } }$ 0 and $z - x \succeq _ { K } 0$ , $z - x \neq 0$ , we conclude $\lambda ^ { T } ( z - x ) > 0$ . Since $z$ is an arbitrary element of $S$ , not equal to $x$ , this shows that $x$ is the unique minimizer of $\lambda ^ { T } z$ over $z \in S$ . Conversely, suppose that for all $\lambda \succ _ { K ^ { * } } 0$ , $x$ is the unique minimizer of $\lambda ^ { T } z$ over $z \in S$ , but $x$ is not the minimum

![](数学书/凸优化/images/5a002484c37d8d9837830d25dfd1fdb95b2c587adba6522b687840639066320e.jpg)  
Figure 2.23 Dual characterization of minimum element. The point $x$ is the minimum element of the set $S$ with respect to $\mathbf { R } _ { + } ^ { 2 }$ . This is equivalent to: for every $\lambda \succ 0$ , the hyperplane $\{ z \mid \lambda ^ { T } ( z - x ) = 0 \}$ strictly supports $S$ a t $_ { x }$ , i.e., contains $S$ on one side, and touches it only at $_ { x }$ .

element of $S$ . Then there exists $z \in S$ with $z \not \subseteq \kappa \ x$ . Since $z - x \not \subseteq \kappa \ : 0$ , there exists $\tilde { \lambda } \succeq _ { K ^ { * } } 0$ with $\bar { \lambda } ^ { T } ( z - x ) < 0$ . Hence $\lambda ^ { T } ( z - x ) < 0$ for $\lambda \succ _ { K ^ { * } } 0$ in the neighborhood of $\lambda$ . This contradicts the assumption that $x$ is the unique minimizer of $\lambda ^ { T } z$ over $S$ .

# Dual characterization of minimal elements

We now turn to a similar characterization of minimal elements. Here there is a gap between the necessary and sufficient conditions. If $\lambda \succ _ { K ^ { * } }$ 0 and $x$ minimizes $\lambda ^ { T } z$ over $z \in S$ , then $x$ is minimal. This is illustrated in figure 2.24.

To show this, suppose that $\lambda \succ _ { K ^ { * } } 0$ , and $x$ minimizes $\lambda ^ { T } z$ over $S$ , but $x$ is not minimal, i.e., there exists a $z \in S$ , $z \neq x$ , and $z \preceq _ { K } x$ . Then $\lambda ^ { T } ( x - z ) > 0$ , which contradicts our assumption that $x$ is the minimizer of $\lambda ^ { T } z$ over $S$ .

The converse is in general false: a point $x$ can be minimal in $S$ , but not a minimizer of $\lambda ^ { T } z$ over $z \in S$ , for any $\lambda$ , as shown in figure 2.25. This figure suggests that convexity plays an important role in the converse, which is correct. Provided the set $S$ is convex, we can say that for any minimal element $x$ there exists a nonzero $\lambda \succeq _ { K ^ { * } }$ 0 such that $x$ minimizes $\lambda ^ { T } z$ over $z \in S$ .

To show this, suppose $x$ is minimal, which means that $( ( x - K ) \setminus \{ x \} ) \cap S = \emptyset$ . Applying the separating hyperplane theorem to the convex sets $( x - K ) \setminus \{ x \}$ and $S$ , we conclude that there is a $\lambda \neq 0$ and $\mu$ such that $\lambda ^ { \prime } ( x - y ) \leq \mu$ for all $y \in K$ , and $\lambda ^ { T } z \ge \mu$ for all $z \in S$ . From the first inequality we conclude $\lambda \succeq _ { K ^ { * } }$ 0. Since $x \in S$ and $x \in x - K$ , we have $\lambda ^ { T } x = \mu$ , so the second inequality implies that $\mu$ is the minimum value of $\lambda ^ { T } z$ over $S$ . Therefore, $x$ is a minimizer of $\lambda ^ { T } z$ over $S$ , where $\lambda \neq 0$ , $\lambda \succeq _ { K ^ { * } }$ 0.

This converse theorem cannot be strengthened to $\lambda \succ _ { K ^ { * } } 0$ . Examples show that a point $x$ can be a minimal point of a convex set $S$ , but not a minimizer of

![](数学书/凸优化/images/03b08d9468543ee545706cb30f2df0d8d90d4d90a7f3f8e8302c49416d6dc3fb.jpg)  
Figure 2.24 A set $S \subseteq \mathbf { R } ^ { 2 }$ . Its set of minimal points, with respect to $\mathbf { R } _ { + } ^ { 2 }$ , is shown as the darker section of its (lower, left) boundary. The minimizer of $\lambda _ { 1 } ^ { T } z$ over $S$ is $x _ { 1 }$ , and is minimal since $\lambda _ { 1 } \succ 0$ . The minimizer of $\lambda _ { 2 } ^ { T } z$ over $S$ is $x _ { 2 }$ , which is another minimal point of $S$ , since $\lambda _ { 2 } \succ 0$ .

![](数学书/凸优化/images/a3c95c0f3f4946fdfa421cc8469483762774b6dc24d72d6c4a4826c84ab89e34.jpg)  
Figure 2.25 The point $x$ is a minimal element of $S \subseteq \mathbf { R } ^ { 2 }$ with respect to $\mathbf { R } _ { + } ^ { 2 }$ . However there exists no $\lambda$ for which $_ { x }$ minimizes $\lambda ^ { T } z$ over $z \in S$ .

![](数学书/凸优化/images/60f9a967e9d3c7a705085944855ea067f308bdf59876c6d799a3a2130b4de594.jpg)

![](数学书/凸优化/images/02838d8a909a6b61f863baee540a17fcff8aa825f27fbf8e9efa73db95a89214.jpg)  
Figure 2.26 Left. The point $x _ { 1 } \in S _ { 1 }$ is minimal, but is not a minimizer of $\lambda ^ { T } z$ over $S _ { 1 }$ for any $\lambda \succ 0$ . (It does, however, minimize $\lambda ^ { T } z$ over $z \in S _ { 1 }$ for $\lambda = ( 1 , 0 )$ .) Right. The point $x _ { 2 } \in S _ { 2 }$ is not minimal, but it does minimize $\lambda ^ { T } z$ over $z \in S _ { 2 }$ for $\lambda = ( 0 , 1 ) \succeq 0$ .

$\lambda ^ { T } z$ over $z \in S$ for any $\lambda \succ _ { K ^ { * } }$ 0. (See figure 2.26, left.) Nor is it true that any minimizer of $\lambda ^ { T } z$ over $z \in S$ , with $\lambda \succeq _ { K ^ { * } } 0$ , is minimal (see figure 2.26, right.)

Example 2.27 Pareto optimal production frontier. We consider a product which requires $n$ resources (such as labor, electricity, natural gas, water) to manufacture. The product can be manufactured or produced in many ways. With each production method, we associate a resource vector $x \in \mathbf { R } ^ { n }$ , where $x _ { i }$ denotes the amount of resource $_ i$ consumed by the method to manufacture the product. We assume that $x _ { i } \geq$ 0 (i.e., resources are consumed by the production methods) and that the resources are valuable (so using less of any resource is preferred).

The production set $P \subseteq \mathbf { R } ^ { n }$ is defined as the set of all resource vectors $_ { x }$ that correspond to some production method.

Production methods with resource vectors that are minimal elements of $P$ , with respect to componentwise inequality, are called Pareto optimal or efficient. The set of minimal elements of $P$ is called the efficient production frontier.

We can give a simple interpretation of Pareto optimality. We say that one production method, with resource vector $x$ , is better than another, with resource vector $y$ , if $x _ { i } \ \leq y _ { i }$ for all $_ i$ , and for some $_ i$ , $x _ { i } ~ < ~ y _ { i }$ . In other words, one production method is better than another if it uses no more of each resource than another method, and for at least one resource, actually uses less. This corresponds to $x \preceq y$ , $x \neq y$ . Then we can say: A production method is Pareto optimal or efficient if there is no better production method.

We can find Pareto optimal production methods (i.e., minimal resource vectors) by minimizing

$$
\lambda^ {T} x = \lambda_ {1} x _ {1} + \dots + \lambda_ {n} x _ {n}
$$

over the set $P$ of production vectors, using any $\lambda$ that satisfies $\lambda \succ 0$ .

Here the vector $\lambda$ has a simple interpretation: $\lambda _ { i }$ is the price of resource i. By minimizing $\lambda ^ { T } x$ over $P$ we are finding the overall cheapest production method (for the resource prices $\lambda _ { i }$ ). As long as the prices are positive, the resulting production method is guaranteed to be efficient.

These ideas are illustrated in figure 2.27.

![](数学书/凸优化/images/f2ec7cc1447ccbde7bbd88d3c46f6cd6227ed0dde5387d19841ec4ad568d0856.jpg)  
Figure 2.27 The production set $P$ , for a product that requires labor and fuel to produce, is shown shaded. The two dark curves show the efficient production frontier. The points $x _ { 1 }$ , $x _ { 2 }$ and $x _ { 3 }$ are efficient. The points $x _ { 4 }$ and $x _ { 5 }$ are not (since in particular, $x _ { 2 }$ corresponds to a production method that uses no more fuel, and less labor). The point $x _ { 1 }$ is also the minimum cost production method for the price vector $\lambda$ (which is positive). The point $x _ { 2 }$ is efficient, but cannot be found by minimizing the total cost $\lambda ^ { T } x$ for any price vector $\lambda \succeq 0$ .


# Exercises

# Definition of convexity

2.1 Let $C \subseteq \mathbf { R } ^ { n }$ be a convex set, with $x _ { 1 } , \ldots , x _ { k } \in C$ , and let $\theta _ { 1 } , \ldots , \theta _ { k } \in \mathbf { R }$ satisfy $\theta _ { i } \geq 0$ , $\theta _ { 1 } + \cdot \cdot \cdot + \theta _ { k } = 1$ . Show that $\theta _ { 1 } x _ { 1 } + \cdot \cdot \cdot + \theta _ { k } x _ { k } \in C$ . (The definition of convexity is that this holds for $k = 2$ ; you must show it for arbitrary $k$ .) Hint. Use induction on $k$ .   
2.2 Show that a set is convex if and only if its intersection with any line is convex. Show that a set is affine if and only if its intersection with any line is affine.   
2.3 Midpoint convexity. A set $C$ is midpoint convex if whenever two points $a , b$ are in $C$ , the average or midpoint $( a + b ) / 2$ is in $C$ . Obviously a convex set is midpoint convex. It can be proved that under mild conditions midpoint convexity implies convexity. As a simple case, prove that if $C$ is closed and midpoint convex, then $C$ is convex.   
2.4 Show that the convex hull of a set $S$ is the intersection of all convex sets that contain $S$ . (The same method can be used to show that the conic, or affine, or linear hull of a set $S$ is the intersection of all conic sets, or affine sets, or subspaces that contain $S$ .)

# Examples

2.5 What is the distance between two parallel hyperplanes $\{ x \in \mathbf { R } ^ { n } \mid a ^ { T } x = b _ { 1 } \}$ and $\{ x \in$ $\mathbf { R } ^ { n } \mid a ^ { T } x = b _ { 2 } \} ^ { \prime }$ ?

2.6 When does one halfspace contain another? Give conditions under which

$$
\{x \mid a ^ {T} x \leq b \} \subseteq \{x \mid \tilde {a} ^ {T} x \leq \tilde {b} \}
$$

(where $a \neq 0$ , $\tilde { a } \ne 0$ ). Also find the conditions under which the two halfspaces are equal.

2.7 Voronoi description of halfspace. Let $a$ and $b$ be distinct points in $\mathbf { R } ^ { n }$ . Show that the set of all points that are closer (in Euclidean norm) to $a$ than $b$ , i.e., $\{ x \mid \| x - a \| _ { 2 } \leq \| x - b \| _ { 2 } \}$ , is a halfspace. Describe it explicitly as an inequality of the form $c ^ { T } x \leq d$ . Draw a picture.

2.8 Which of the following sets $S$ are polyhedra? If possible, express $S$ in the form $S =$ $\{ x \mid A x \preceq b , F x = g \}$ .

(a) $S = \{ y _ { 1 } a _ { 1 } + y _ { 2 } a _ { 2 } \mid - 1 \le y _ { 1 } \le 1 , \ - 1 \le y _ { 2 } \le 1 \}$ , where $a _ { 1 } , a _ { 2 } \in \mathbf { R } ^ { n }$   
(b) $S = \{ x \in \mathbf { R } ^ { n } \mid x \succeq 0$ x = 1, Pni=1 xiai = b1,. $\textstyle \sum _ { i = 1 } ^ { n } x _ { i } a _ { i } ^ { 2 } \ = \ b _ { 2 } \}$ , where $a _ { 1 } , \ldots , a _ { n } \in \mathbf { R }$ $b _ { 1 } , b _ { 2 } \in \mathbf { R }$   
(c) $S = \{ x \in \mathbf { R } ^ { n } \mid x \succeq 0 , \ x ^ { T } y \leq 1$ for all $_ y$ with $\| y \| _ { 2 } = 1 \}$ .   
(d) $S = \{ x \in \mathbf { R } ^ { n } \mid x \succeq 0 , \ x ^ { T } y \leq 1$ for all $_ y$ with $\textstyle \sum _ { i = 1 } ^ { n } | y _ { i } | = 1 \}$

2.9 Voronoi sets and polyhedral decomposition. Let $x _ { 0 } , . . . , x _ { K } \in \mathbf { R } ^ { n }$ be distinct. Consider the set of points that are closer (in Euclidean norm) to $x _ { 0 }$ than the other $x _ { i }$ , i.e.,

$$
V = \{x \in \mathbf {R} ^ {n} \mid \| x - x _ {0} \| _ {2} \leq \| x - x _ {i} \| _ {2}, i = 1, \dots , K \}.
$$

$V$ is called the Voronoi region around $x _ { 0 }$ with respect to $x _ { 1 } , \ldots , x _ { K }$ .

(a) Show that $V$ is a polyhedron. Express $V$ in the form $V = \{ x \mid A x \preceq b \}$   
(b) Conversely, given a polyhedron $P$ with nonempty interior, show how to find $x _ { 0 } , \ldots , x _ { K }$ so that the polyhedron is the Voronoi region of $x _ { 0 }$ with respect to $x _ { 1 } , \ldots , x _ { K }$ .   
(c) We can also consider the sets

$$
V _ {k} = \left\{x \in \mathbf {R} ^ {n} \mid \| x - x _ {k} \| _ {2} \leq \| x - x _ {i} \| _ {2}, i \neq k \right\}.
$$

The set $V _ { k }$ consists of points in $\mathbf { R } ^ { n }$ for which the closest point in the set $\{ x _ { 0 } , \ldots , x _ { K } \}$ is $x _ { k }$ .

The sets $V _ { k }$ r olyhe, i.e., $V _ { 0 } , \ldots , V _ { K }$ a witand give a polyhedral decomposition of nonempty interior, intersect at most $\textstyle \bigcup _ { k = 0 } ^ { K } V _ { k } = \mathbf { R } ^ { n }$ $\mathbf { R } ^ { n }$ , and ry. . More precisely, the sets $\mathbf { i n t } V _ { i } \cap \mathbf { i n t } V _ { j } = \emptyset$ $i \neq j$ $V _ { i }$ $V _ { j }$

Suppose that $P _ { 1 } , \ldots , P _ { m }$ are polyhedra with nonempty interior such that $\textstyle \bigcup _ { i = 1 } ^ { m } P _ { i } =$ $\mathbf { R } ^ { n }$ , int Pi ∩ int Pj = ∅ for $i \neq j$ . Can this polyhedral decomposition of $\mathbf { R } ^ { n }$ b e described as the Voronoi regions generated by an appropriate set of points?

2.10 Solution set of a quadratic inequality. Let $C \subseteq \mathbf { R } ^ { n }$ be the solution set of a quadratic inequality,

$$
C = \{x \in \mathbf {R} ^ {n} \mid x ^ {T} A x + b ^ {T} x + c \leq 0 \},
$$

with $A \in \mathbf { S } ^ { n }$ , $b \in \mathbf { R } ^ { n }$ , and $c \in \mathbf { R }$ .

(a) Show that $C$ is convex if $A \succeq 0$ .   
(b) Show that the intersection of $C$ and the hyperplane defined by $g ^ { T } x + h = 0$ (where $g \neq 0$ ) is convex if $A + \lambda g g ^ { T } \succeq 0$ for some $\lambda \in \mathbf { R }$ .

Are the converses of these statements true?

2.11 Hyperbolic sets. Show that the hyperbolic set $\{ x \in \mathbf { R } _ { + } ^ { 2 } \mid x _ { 1 } x _ { 2 } \geq 1 \}$ is convex. As a generalization, show that $\begin{array} { r } { \{ x \in \mathbf { R } _ { + } ^ { n } \mid \mid \prod _ { i = 1 } ^ { n } x _ { i } \geq 1 \} } \end{array}$ is convex. Hint. If $a , b \geq 0$ and $0 \leq \theta \leq 1$ , then $a ^ { \theta } b ^ { 1 - \theta } \leq \theta a + ( 1 - \theta ) b$ ; see §3.1.9.   
2.12 Which of the following sets are convex?

(a) A slab, i.e., a set of the form $\{ x \in \mathbf { R } ^ { n } \mid \alpha \leq a ^ { 2 } x \leq \beta \}$ .   
(b) A rectangle, i.e., a set of the form $\{ x \in \mathbf { R } ^ { n } \mid \alpha _ { i } \leq x _ { i } \leq \beta _ { i } , i = 1 , \ldots , n \}$ $i = 1 , \ldots , n \}$ . A rectangle is sometimes called a hyperrectangle when $n > 2$ .   
(c) A wedge, i.e., $\{ x \in \mathbf { R } ^ { n } \mid a _ { 1 } ^ { \prime \prime } x \leq b _ { 1 } , a _ { 2 } ^ { \prime \prime } x \leq b _ { 2 } \}$ .   
(d) The set of points closer to a given point than a given set, i.e.,

$$
\{x \mid \| x - x _ {0} \| _ {2} \leq \| x - y \| _ {2} \text {f o r a l l} y \in S \}
$$

where $S \subseteq \mathbf { R } ^ { n }$ .

(e) The set of points closer to one set than another, i.e.,

$$
\{x \mid \operatorname {d i s t} (x, S) \leq \operatorname {d i s t} (x, T) \},
$$

where $S , T \subseteq \mathbf { R } ^ { n }$ , and

$$
\operatorname {d i s t} (x, S) = \inf  \left\{\left\| x - z \right\| _ {2} \mid z \in S \right\}.
$$

(f) [HUL93, volume 1, page 93] The set $\{ x \mid x + S _ { 2 } \subseteq S _ { 1 } \}$ , where $S _ { 1 } , S _ { 2 } \subseteq \mathbf { R } ^ { n }$ with $S _ { 1 }$ convex.   
(g) The set of points whose distance to $a$ does not exceed a fixed fraction $\theta$ of the distance to $b$ , i.e., the set $\{ x \mid \| x - a \| _ { 2 } \leq \theta \| x - b \| _ { 2 } \}$ . You can assume $a \neq b$ and $0 \leq \theta \leq 1$ .

2.13 Conic hull of outer products. Consider the set of rank- $k$ outer products, defined as $\{ X X ^ { T } \mid X \in \mathbf { R } ^ { n \times k }$ , $\mathbf { r a n k } X = k \}$ . Describe its conic hull in simple terms.

2.14 Expanded and restricted sets. Let $S \subseteq \mathbf { R } ^ { n }$ , and let $\| \cdot \|$ be a norm on $\mathbf { R } ^ { n }$

(a) For $a \geq 0$ we define $S _ { a }$ as $\{ x \mid \mathbf { d i s t } ( x , S ) \leq a \}$ , where $\mathbf { d i s t } ( x , S ) = \operatorname* { i n f } _ { y \in S } \| x - y \|$ We refer to $S _ { a }$ as $S$ expanded or extended by $a$ . Show that if $S$ is convex, then $S _ { a }$ is convex.   
(b) For $a \geq 0$ we define $S _ { - a } = \{ x \mid B ( x , a ) \subseteq S \}$ , where $B ( x , a )$ is the ball (in the norm $\| \cdot \| )$ , centered at $x$ , with radius $a$ . We refer to $S _ { - a }$ as $S$ shrunk or restricted by $a$ since $S _ { - a }$ consists of all points that are at least a distance $a$ from ${ \mathbf { R } } ^ { n } \backslash S$ . Show that if $S$ is convex, then $S _ { - a }$ is convex.

2.15 Some sets of probability distributions. Let $_ { x }$ be a real-valued random variable with $\mathbf { p r o b } ( x = a _ { i } ) = p _ { i }$ , $i = 1 , \ldots , n$ , where $a _ { 1 } < a _ { 2 } < \cdots < a _ { n }$ . Of course $p \in \mathbf { R } ^ { n }$ lies in the standard probability simplex $P = \{ p \mid \mathbf { 1 } ^ { T } p = 1 , \ p \succeq 0 \}$ . Which of the following conditions are convex in $p$ ? (That is, for which of the following conditions is the set of $p \in { \cal P }$ that satisfy the condition convex?)

(a) $\underline { { { \alpha } } } ~ \le ~ \mathbf { E } ~ f ( x ) ~ \le ~ \beta$ , where $\mathbf { E } f ( x )$ is the expected value of $f ( x )$ , i.e., $\mathbf { E } f ( x ) \ =$ $\scriptstyle \sum _ { i = 1 } ^ { n } p _ { i } f ( a _ { i } )$ . (The function $f : \mathbf { R }  \mathbf { R }$ is given.)   
(b) $\mathbf { p r o b } ( x > \alpha ) \leq \beta$   
(c) $\mathbf { E } \left| x ^ { 3 } \right| \leq \alpha \mathbf { E } \left| x \right|$   
(d) $\mathbf { E } x ^ { 2 } \leq \alpha$   
(e) $\mathbf { E } x ^ { 2 } \geq \alpha$   
(f) $\mathbf { v a r } ( x ) \leq \alpha$ , where $\mathbf { v a r } ( x ) = \mathbf { E } ( x - \mathbf { E } x ) ^ { : 2 }$ is the variance of $_ { x }$   
(g) $\mathbf { v a r } ( x ) \geq \alpha$ .   
(h) quartile $( x ) \geq \alpha$ , where quartile(x) = inf{β | prob(x ≤ β) ≥ 0.25}.   
(i) quartile(x) ≤ α.

# Operations that preserve convexity

2.16 Show that if $S _ { 1 }$ and $S _ { 2 }$ are convex sets in $\mathbf { R } ^ { m + n }$ , then so is their partial sum

$$
S = \left\{\left(x, y _ {1} + y _ {2}\right) \mid x \in \mathbf {R} ^ {m}, y _ {1}, y _ {2} \in \mathbf {R} ^ {n}, \left(x, y _ {1}\right) \in S _ {1}, \left(x, y _ {2}\right) \in S _ {2} \right\}.
$$

2.17 Image of polyhedral sets under perspective function. In this problem we study the image of hyperplanes, halfspaces, and polyhedra under the perspective function $P ( x , t ) = x / t$ , with ${ \bf d o m } { \cal P } = { \bf R } ^ { n } \times { \bf R } _ { + + }$ . For each of the following sets $C$ , give a simple description of

$$
P (C) = \{v / t \mid (v, t) \in C, t > 0 \}.
$$

(a) The polyhedron $C = \mathbf { c o n v \{ } (  v _ { 1 } , t _ { 1 } ) , \ldots , ( v _ { K } , t _ { K } ) \big \}$ where $v _ { i } \in \mathbf { R } ^ { n }$ and $t _ { i } > 0$ .   
(b) The hyperplane $C = \{ ( v , t ) \mid f ^ { T } v + g t = h \}$ (with $f$ and $g$ not both zero).   
(c) The halfspace $C = \{ ( v , t ) \mid f ^ { T } v + g t \leq h \}$ (with $f$ and $g$ not both zero).   
(d) The polyhedron $C = \{ ( v , t ) \mid F v + g t \preceq h \}$ .

2.18 Invertible linear-fractional functions. Let $f : \mathbf { R } ^ { n }  \mathbf { R } ^ { n }$ be the linear-fractional function

$$
f (x) = \left(A x + b\right) / \left(c ^ {T} x + d\right), \quad \mathbf {d o m} f = \left\{x \mid c ^ {T} x + d > 0 \right\}.
$$

Suppose the matrix

$$
Q = \left[ \begin{array}{c c} A & b \\ c ^ {T} & d \end{array} \right]
$$

is nonsingular. Show that $f$ is invertible and that $f ^ { - 1 }$ is a linear-fractional mapping. Give an explicit expression for $f ^ { - 1 }$ and its domain in terms of $A$ , $b$ , $c$ , and $d$ . Hint. It may be easier to express $f ^ { - 1 }$ in terms of $Q$ .

2.19 Linear-fractional functions and convex sets. Let $f : \mathbf { R } ^ { m }  \mathbf { R } ^ { n }$ be the linear-fractional function

$$
f (x) = \left(A x + b\right) / \left(c ^ {T} x + d\right), \quad \mathbf {d o m} f = \left\{x \mid c ^ {T} x + d > 0 \right\}.
$$

In this problem we study the inverse image of a convex set $C$ under $f$ , i.e.,

$$
f ^ {- 1} (C) = \{x \in \operatorname {d o m} f \mid f (x) \in C \}.
$$

For each of the following sets $C \subseteq \mathbf { R } ^ { n }$ , give a simple description of $f ^ { - 1 } ( C )$ .

(a) The halfspace $C = \{ y \mid g ^ { \mathcal { I } ^ { \prime } } y \leq h \}$ (with $g \neq 0$ ).   
(b) The polyhedron $C = \{ y \mid G y \preceq h \}$ .   
(c) The ellipsoid $\{ y \mid y ^ { T } P ^ { - 1 } y \leq 1 \}$ (where $P \in \mathbf { S } _ { + + } ^ { n }$ ).   
(d) The solution set of a linear matrix inequality, $C = \{ y \mid y _ { 1 } A _ { 1 } + \cdot \cdot \cdot + y _ { n } A _ { n } \preceq B \}$ , where $A _ { 1 }$ , . . . , $A _ { n }$ , $B \in \mathbf { S } ^ { p }$ .


# Separation theorems and supporting hyperplanes

2.20 Strictly positive solution of linear equations. Suppose $A \in \mathbf { R } ^ { m \times n }$ , $b \in \mathbf { R } ^ { m }$ , with $b \in { \mathcal { R } } ( A )$ Show that there exists an $x$ satisfying

$$
x \succ 0, \quad A x = b
$$

if and only if there exists no $\lambda$ with

$$
A ^ {T} \lambda \succeq 0, \qquad A ^ {T} \lambda \neq 0, \qquad b ^ {T} \lambda \leq 0.
$$

Hint. First prove the following fact from linear algebra: $c ^ { T } x = d$ for all $x$ satisfying $A x = b$ if and only if there is a vector $\lambda$ such that $c = A ^ { T } \lambda$ , $d = b ^ { T } \lambda$ .

2.21 The set of separating hyperplanes. Suppose that $C$ and $D$ are disjoint subsets of $\mathbf { R } ^ { n }$ . Consider the set of $( a , b ) \in \mathbf { R } ^ { n + 1 }$ for which $a ^ { x } x \leq b$ for all $x \in C$ , and $a ^ { 2 } x \geq b$ for all $x \in D$ . Show that this set is a convex cone (which is the singleton $\{ 0 \}$ if there is no hyperplane that separates $C$ and $D$ ).   
2.22 Finish the proof of the separating hyperplane theorem in §2.5.1: Show that a separating hyperplane exists for two disjoint convex sets $C$ and $D$ . You can use the result proved in §2.5.1, i.e., that a separating hyperplane exists when there exist points in the two sets whose distance is equal to the distance between the two sets.

Hint. If $C$ and $D$ are disjoint convex sets, then the set $\{ x - y \mid x \in C , \ y \in D \}$ is convex and does not contain the origin.

2.23 Give an example of two closed convex sets that are disjoint but cannot be strictly separated.   
2.24 Supporting hyperplanes.

(a) Express the closed convex set $\{ x \in \mathbf { R } _ { + } ^ { 2 } \mid x _ { 1 } x _ { 2 } \geq 1 \}$ as an intersection of halfspaces.   
(b) Let $C = \{ x \in \mathbf { R } ^ { n } \mid \| x \| _ { \infty } \leq 1 \}$ , the $\ell _ { \infty }$ -norm unit ball in $\mathbf { R } ^ { n }$ , and let $\hat { x }$ be a point in the boundary of $C$ . Identify the supporting hyperplanes of $C$ at $\hat { x }$ explicitly.

2.25 Inner and outer polyhedral approximations. Let $C \subseteq \mathbf { R } ^ { n }$ be a closed convex set, and suppose that $x _ { 1 } , \ldots , x _ { K }$ are on the boundary of $C$ . Suppose that for each $_ i$ , $a _ { i } ^ { \prime } ( x - x _ { i } ) = 0$ defines a supporting hyperplane for $C$ at $x _ { i }$ , i.e., $C \subseteq \{ x \mid a _ { i } ^ { T } ( x - x _ { i } ) \leq 0 \}$ . Consider the two polyhedra

$$
P _ {\text {i n n e r}} = \mathbf {c o n v} \left\{x _ {1}, \dots , x _ {K} \right\}, \quad P _ {\text {o u t e r}} = \left\{x \mid a _ {i} ^ {T} \left(x - x _ {i}\right) \leq 0, i = 1, \dots , K \right\}.
$$

Show that $P _ { \mathrm { i n n e r } } \subseteq C \subseteq P _ { \mathrm { o u t e r } }$ . Draw a picture illustrating this.

2.26 Support function. The support function of a set $C \subseteq \mathbf { R } ^ { n }$ is defined as

$$
S _ {C} (y) = \sup  \left\{y ^ {T} x \mid x \in C \right\}.
$$

(We allow $S _ { C } ( y )$ to take on the value $+ \infty$ .) Suppose that $C$ and $D$ are closed convex sets in $\mathbf { R } ^ { n }$ . Show that $C = D$ if and only if their support functions are equal.

2.27 Converse supporting hyperplane theorem. Suppose the set $C$ is closed, has nonempty interior, and has a supporting hyperplane at every point in its boundary. Show that $C$ is convex.

# Convex cones and generalized inequalities

2.28 Positive semidefinite cone for $n = 1$ , 2, 3. Give an explicit description of the positive semidefinite cone $\mathbf { S } _ { + } ^ { n }$ , in terms of the matrix coefficients and ordinary inequalities, for $n = 1$ , 2, 3. To describe a general element of $\mathbf { S } ^ { n }$ , for $n = 1 , ~ 2 , ~ 3$ , use the notation

$$
x _ {1}, \qquad \left[ \begin{array}{c c} x _ {1} & x _ {2} \\ x _ {2} & x _ {3} \end{array} \right], \qquad \left[ \begin{array}{c c c} x _ {1} & x _ {2} & x _ {3} \\ x _ {2} & x _ {4} & x _ {5} \\ x _ {3} & x _ {5} & x _ {6} \end{array} \right].
$$

2.29 Cones in $\mathbf { R } ^ { 2 }$ . Suppose $K \subseteq \mathbf { R } ^ { 2 }$ is a closed convex cone.

(a) Give a simple description of $K$ in terms of the polar coordinates of its elements $x = r ( \cos \phi , \sin \phi )$ with $r \geq 0$ ).   
(b) Give a simple description of $K ^ { * }$ , and draw a plot illustrating the relation between $K$ and $K ^ { * }$ .   
(c) When is $K$ pointed?   
(d) When is $K$ proper (hence, defines a generalized inequality)? Draw a plot illustrating what $x \preceq _ { K } y$ means when $K$ is proper.

2.30 Properties of generalized inequalities. Prove the properties of (nonstrict and strict) generalized inequalities listed in §2.4.1.

2.31 Properties of dual cones. Let $K ^ { * }$ be the dual cone of a convex cone $K$ , as defined in (2.19). Prove the following.

(a) $K ^ { * }$ is indeed a convex cone.   
(b) $K _ { 1 } \subseteq K _ { 2 }$ implies $K _ { 2 } ^ { * } \subseteq K _ { 1 } ^ { * }$ .   
(c) $K ^ { * }$ is closed.   
(d) The interior of $K ^ { * }$ is given by $\mathbf { i n t } K ^ { * } = \{ y \mid y ^ { T } x > 0$ for all $x \in \mathbf { c l } K \}$   
(e) If $K$ has nonempty interior then $K ^ { * }$ is pointed.   
(f) $K ^ { * * }$ is the closure of $K$ . (Hence if $K$ is closed, $K ^ { * * } = K$ .)   
(g) If the closure of $K$ is pointed then $K ^ { * }$ has nonempty interior.

2.32 Find the dual cone of $\{ A x \mid x \succeq 0 \}$ , where $A \in \mathbf { R } ^ { m \times n }$ .

2.33 The monotone nonnegative cone. We define the monotone nonnegative cone as

$$
K _ {\mathrm {m} +} = \left\{x \in \mathbf {R} ^ {n} \mid x _ {1} \geq x _ {2} \geq \dots \geq x _ {n} \geq 0 \right\}.
$$

i.e., all nonnegative vectors with components sorted in nonincreasing order.

(a) Show that $K _ { \mathrm { m + } }$ is a proper cone.   
(b) Find the dual cone $K _ { \mathrm { m + } } ^ { \ast }$ . Hint. Use the identity

$$
\begin{array}{l} \sum_ {i = 1} ^ {n} x _ {i} y _ {i} = (x _ {1} - x _ {2}) y _ {1} + (x _ {2} - x _ {3}) (y _ {1} + y _ {2}) + (x _ {3} - x _ {4}) (y _ {1} + y _ {2} + y _ {3}) + \dots \\ + \left(x _ {n - 1} - x _ {n}\right) \left(y _ {1} + \dots + y _ {n - 1}\right) + x _ {n} \left(y _ {1} + \dots + y _ {n}\right). \\ \end{array}
$$

2.34 The lexicographic cone and ordering. The lexicographic cone is defined as

$$
K _ {\text {l e x}} = \{0 \} \cup \left\{x \in \mathbf {R} ^ {n} \mid x _ {1} = \dots = x _ {k} = 0, x _ {k + 1} > 0, \text {f o r s o m e} k, 0 \leq k <   n \right\},
$$

i.e., all vectors whose first nonzero coefficient (if any) is positive.

(a) Verify that $K _ { \mathrm { l e x } }$ is a cone, but not a proper cone.   
(b) We define the lexicographic ordering on $\mathbf { R } ^ { n }$ as follows: $x \ \leq _ { \mathrm { l e x } } \ y$ if and only if $y - x \in K _ { \mathrm { l e x } }$ . (Since $K _ { \mathrm { l e x } }$ is not a proper cone, the lexicographic ordering is not a generalized inequality.) Show that the lexicographic ordering is a linear ordering: for any $x , \ y \in \mathbf { R } ^ { n }$ , either $x \leq _ { \mathrm { l e x } } y$ or $y \leq _ { \mathrm { l e x } } x$ . Therefore any set of vectors can be sorted with respect to the lexicographic cone, which yields the familiar sorting used in dictionaries.   
(c) Find $K _ { \mathrm { l e x } } ^ { * }$

2.35 Copositive matrices. A matrix $X \in \mathbf { S } ^ { n }$ is called copositive if $z ^ { T } X z \ge 0$ for all $z \succeq 0$ . Verify that the set of copositive matrices is a proper cone. Find its dual cone.

2.36 Euclidean distance matrices. Let $x _ { 1 } , \ldots , x _ { n } \in \mathbf { R } ^ { k }$ . The matrix $D \in \mathbf { S } ^ { n }$ defined by $D _ { i j } =$ $\| x _ { i } - x _ { j } \| _ { 2 } ^ { 2 }$ is called a Euclidean distance matrix. It satisfies some obvious properties such as $D _ { i j } = D _ { j i }$ , $D _ { i i } = 0$ , $D _ { i j } \geq 0$ , and (from the triangle inequality) $D _ { i k } ^ { 1 / 2 } \leq D _ { i j } ^ { 1 / 2 } + D _ { j k } ^ { 1 / 2 }$ 2 ≤ D1/2ij We now pose the question: When is a matrix $D \in \mathbf { S } ^ { n }$ a Euclidean distance matrix (for some points in $\mathbf { R } ^ { k }$ , for some $k$ )? A famous result answers this question: $D \in \mathbf { S } ^ { n }$ is a Euclidean distance matrix if and only if $D _ { i i } = 0$ and $x ^ { T } D x \leq 0$ for all $_ { x }$ with $\mathbf { 1 } ^ { T } x = 0$ . (See §8.3.3.)

Show that the set of Euclidean distance matrices is a convex cone.

2.37 Nonnegative polynomials and Hankel LMIs. Let $K _ { \mathrm { p o l } }$ be the set of (coefficients of) nonnegative polynomials of degree $2 k$ on $\mathbf { R }$ :

$$
K _ {\mathrm {p o l}} = \left\{x \in \mathbf {R} ^ {2 k + 1} \mid x _ {1} + x _ {2} t + x _ {3} t ^ {2} + \dots + x _ {2 k + 1} t ^ {2 k} \geq 0 \text {f o r a l l} t \in \mathbf {R} \right\}.
$$

(a) Show that $K _ { \mathrm { p o l } }$ is a proper cone.   
(b) A basic result states that a polynomial of degree $2 k$ is nonnegative on $\mathbf { R }$ if and only if it can be expressed as the sum of squares of two polynomials of degree $k$ or less. In other words, $x \in K _ { \mathrm { p o l } }$ if and only if the polynomial

$$
p (t) = x _ {1} + x _ {2} t + x _ {3} t ^ {2} + \dots + x _ {2 k + 1} t ^ {2 k}
$$

can be expressed as

$$
p (t) = r (t) ^ {2} + s (t) ^ {2},
$$

where $T$ and $s$ are polynomials of degree $k$ .

Use this result to show that

$$
K _ {\mathrm {p o l}} = \left\{x \in \mathbf {R} ^ {2 k + 1} \left| x _ {i} = \sum_ {m + n = i + 1} Y _ {m n} \text {f o r s o m e} Y \in \mathbf {S} _ {+} ^ {k + 1} \right. \right\}.
$$

there exists a matrix In other words, $p ( t ) = x _ { 1 } + x _ { 2 } t + x _ { 3 } t ^ { 2 } + \cdot \cdot \cdot + x _ { 2 k + 1 } t ^ { 2 k }$ $Y \in \mathbf { S } _ { + } ^ { k + 1 }$ · such that is nonnegative if and only if

$$
x _ {1} = Y _ {1 1}
$$

$$
x _ {2} = Y _ {1 2} + Y _ {2 1}
$$

$$
x _ {3} = Y _ {1 3} + Y _ {2 2} + Y _ {3 1}
$$

$$
x _ {2 k + 1} = Y _ {k + 1, k + 1}.
$$

(c) Show that $K _ { \mathrm { p o l } } ^ { * } = K _ { \mathrm { h a n } }$ where

$$
K _ {\mathrm {h a n}} = \left\{z \in \mathbf {R} ^ {2 k + 1} \mid H (z) \succeq 0 \right\}
$$

and

$$
H (z) = \left[ \begin{array}{c c c c c c} z _ {1} & z _ {2} & z _ {3} & \dots & z _ {k} & z _ {k + 1} \\ z _ {2} & z _ {3} & z _ {4} & \dots & z _ {k + 1} & z _ {k + 2} \\ z _ {3} & z _ {4} & z _ {5} & \dots & z _ {k + 2} & z _ {k + 4} \\ \vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\ z _ {k} & z _ {k + 1} & z _ {k + 2} & \dots & z _ {2 k - 1} & z _ {2 k} \\ z _ {k + 1} & z _ {k + 2} & z _ {k + 3} & \dots & z _ {2 k} & z _ {2 k + 1} \end{array} \right].
$$

(This is the Hankel matrix with coefficients $z _ { 1 } , \ldots , z _ { 2 k + 1 }$ .)

(d) Let $K _ { \mathrm { m o m } }$ be the conic hull of the set of all vectors of the form $( 1 , t , t ^ { 2 } , \ldots , t ^ { 2 k } )$ where $t \in \mathbf { R }$ . Show that $y \in K _ { \mathrm { m o m } }$ if and only if $y _ { 1 } \geq 0$ and

$$
y = y _ {1} \left(1, \mathbf {E} u, \mathbf {E} u ^ {2}, \dots , \mathbf {E} u ^ {2 k}\right)
$$

for some random variable $u$ . In other words, the elements of $K _ { \mathrm { m o m } }$ are nonnegative multiples of the moment vectors of all possible distributions on $\mathbf { R }$ . Show that $K _ { \mathrm { p o l } } =$ $K _ { \mathrm { m o m } } ^ { * }$ .

(e) Combining the results of (c) and (d), conclude that $K _ { \mathrm { h a n } } = \mathbf { c } \mathbf { l } K _ { \mathrm { m o m } }$

As an example illustrating the relation between $K _ { \mathrm { m o m } }$ and $K _ { \mathrm { h a n } }$ , take $k = 2$ and $\boldsymbol { z } = ( 1 , 0 , 0 , 0 , 1 )$ . Show that $z \in K _ { \mathrm { h a n } }$ , $z \not \in K _ { \mathrm { m o m } }$ . Find an explicit sequence of points in $K _ { \mathrm { m o m } }$ which converge to $z$ .

2.38 [Roc70, pages 15, 61] Convex cones constructed from sets.

(a) The barrier cone of a set $C$ is defined as the set of all vectors $_ y$ such that $y ^ { T } x$ i s bounded above over $x \in C$ . In other words, a nonzero vector $y$ is in the barrier cone if and only if it is the normal vector of a halfspace $\{ x \mid y ^ { x } x \leq \alpha \}$ that contains $C$ Verify that the barrier cone is a convex cone (with no assumptions on $C$ ).   
(b) The recession cone (also called asymptotic cone) of a set $C$ is defined as the set of all vectors $_ y$ such that for each $x \in C$ , $x - t y \in C$ for all $t \geq 0$ . Show that the recession cone of a convex set is a convex cone. Show that if $C$ is nonempty, closed, and convex, then the recession cone of $C$ is the dual of the barrier cone.   
(c) The normal cone of a set $C$ at a boundary point $x _ { 0 }$ is the set of all vectors $_ y$ such that $y ^ { T } ( x - x _ { 0 } ) \leq 0$ for all $x \in C$ (i.e., the set of vectors that define a supporting hyperplane to $C$ at $x _ { 0 }$ ). Show that the normal cone is a convex cone (with no assumptions on $C$ ). Give a simple description of the normal cone of a polyhedron $\{ x \mid A x \preceq b \}$ at a point in its boundary.

2.39 Separation of cones. Let $K$ and $\tilde { K }$ be two convex cones whose interiors are nonempty and disjoint. Show that there is a nonzero $y$ such that $y \in K ^ { * }$ , $- y \in \tilde { K } ^ { * }$ .


# 第二章

# 凸集

# 2.1 仿射集与凸集

# 2.1.1 直线与线段

假设 $x _ { 1 } \neq x _ { 2 }$ 是 $\mathbf { R } ^ { n }$ 中的两个点。形如

$$
y = \theta x _ {1} + (1 - \theta) x _ {2},
$$

其中 $\theta \in \mathbf { R }$ 的点，构成了通过 $x _ { 1 }$ 和 $x _ { 2 }$ 的直线。参数值 $\theta = 0$ 对应 $y = x _ { 2 }$，参数值 $\theta = 1$ 对应 $y = x _ { 1 }$。参数 $\theta$ 在 0 和 1 之间的值对应 $x _ { 1 }$ 和 $x _ { 2 }$ 之间的（闭）线段。

将 $y$ 表示为

$$
y = x _ {2} + \theta \left(x _ {1} - x _ {2}\right)
$$

给出了另一种解释：$y$ 是基点 $x _ { 2 }$（对应 $\theta = 0$）与方向 $x _ { 1 } - x _ { 2 }$（从 $x _ { 2 }$ 指向 $x _ { 1 }$）乘以参数 $\theta$ 的和。因此，$\theta$ 给出了从 $x _ { 2 }$ 到 $x _ { 1 }$ 的路径上 $y$ 所在位置的比例。当 $\theta$ 从 0 增加到 1 时，点 $y$ 从 $x _ { 2 }$ 移动到 $x _ { 1 }$；对于 $\theta > 1$，点 $y$ 位于 $x _ { 1 }$ 之外的直线上。如图 2.1 所示。

# 2.1.2 仿射集

如果通过 $C$ 中任意两个不同点的直线位于 $C$ 中，则集合 $C \subseteq \mathbf { R } ^ { n }$ 是仿射的，即，对于任何 $x _ { 1 } , x _ { 2 } \in C$ 和 $\theta \in \mathbf { R }$，我们有 $\theta x _ { 1 } + ( 1 - \theta ) x _ { 2 } \in C$。换句话说，$C$ 包含 $C$ 中任意两点的线性组合，只要线性组合中的系数之和为一。

这个概念可以推广到两个以上的点。我们将形如 $\theta _ { 1 } x _ { 1 } + \cdot \cdot \cdot + \theta _ { k } x _ { k }$，其中 $\theta _ { 1 } + \cdot \cdot \cdot + \theta _ { k } = 1$ 的点称为点 $x _ { 1 }$ , . . . , $x _ { k }$ 的仿射组合。使用仿射集定义的归纳法（即它包含其任意两点的每个仿射组合），可以证明

![](数学书/凸优化/images/00a5ff06617b4fc5cf57e13b3123b2736b853ba4e38f65283cb7e1a7c52491dc.jpg)
图 2.1 通过 $x _ { 1 }$ 和 $x _ { 2 }$ 的直线由 $\theta x _ { 1 } + ( 1 - \theta ) x _ { 2 }$ 参数化描述，其中 $\theta$ 在 $\mathbf { R }$ 上变化。$x _ { 1 }$ 和 $x _ { 2 }$ 之间的线段（对应 $\theta$ 在 0 和 1 之间）显示为较暗部分。

仿射集包含其点的每个仿射组合：如果 $C$ 是仿射集，$x _ { 1 } , \ldots , x _ { k } \in C$，且 $\theta _ { 1 } + \cdot \cdot \cdot + \theta _ { k } = 1$，那么点 $\theta _ { 1 } x _ { 1 } + \cdot \cdot \cdot + \theta _ { k } x _ { k }$ 也属于 $C$。

如果 $C$ 是仿射集且 $x _ { 0 } \in C$，那么集合

$$
V = C - x _ {0} = \{x - x _ {0} \mid x \in C \}
$$

是一个子空间，即对加法和标量乘法封闭。为了说明这一点，假设 $v _ { 1 } , \ v _ { 2 } \in V$ 且 $\alpha , ~ \beta \in \mathbf { R }$。那么我们有 $v _ { 1 } + x _ { 0 } \in C$ 和 $v _ { 2 } + x _ { 0 } \in C$，因此

$$
\alpha \left(v _ {1} + x _ {0}\right) + \beta \left(v _ {2} + x _ {0}\right) + (1 - \alpha - \beta) x _ {0} = \alpha v _ {1} + \beta v _ {2} + x _ {0}  \in C,
$$

因为 $C$ 是仿射的，且 $\alpha + \beta + ( 1 - \alpha - \beta ) = 1$。我们得出结论 $\alpha v _ { 1 } + \beta v _ { 2 } \in V$，因为 $\alpha v _ { 1 } + \beta v _ { 2 } + x _ { 0 } \in C$。

因此，仿射集 $C$ 可以表示为

$$
C = V + x _ {0} = \{v + x _ {0} \mid v \in V \},
$$

即，一个子空间加上一个偏移。与仿射集 $C$ 相关联的子空间 $V$ 不依赖于 $x _ { 0 }$ 的选择，因此 $x _ { 0 }$ 可以选择为 $C$ 中的任意点。我们将仿射集 $C$ 的维数定义为子空间 $V = C - x _ { 0 }$ 的维数，其中 $x _ { 0 }$ 是 $C$ 的任意元素。

例 2.1 线性方程组的解集。线性方程组的解集 $C = \{ x \mid A x = b \}$，其中 $A \in \mathbf { R } ^ { m \times n }$ 且 $b \in \mathbf { R } ^ { m }$，是一个仿射集。为了证明这一点，假设 $x _ { 1 } , \ x _ { 2 } \in C$，即 $A x _ { 1 } = b$，$A x _ { 2 } = b$。那么对于任何 $\theta$，我们有

$$
\begin{array}{l} A \left(\theta x _ {1} + (1 - \theta) x _ {2}\right) = \theta A x _ {1} + (1 - \theta) A x _ {2} \\ = \theta b + (1 - \theta) b \\ = b, \\ \end{array}
$$

这表明仿射组合 $\theta x _ { 1 } + ( 1 - \theta ) x _ { 2 }$ 也在 $C$ 中。与仿射集 $C$ 相关联的子空间是 $A$ 的零空间，<mark style="background: #FFF3A3A6;">也就是ker(A)。</mark>

我们也有一个逆命题：每个仿射集都可以表示为一个线性方程组的解集。

某个集合 $C \subseteq \mathbf { R } ^ { n }$ 中所有点的仿射组合的集合称为 $C$ 的仿射包，记作 aff $C$：

$$
\mathbf {a f f} C = \left\{\theta_ {1} x _ {1} + \dots + \theta_ {k} x _ {k} \mid x _ {1}, \dots , x _ {k} \in C, \theta_ {1} + \dots + \theta_ {k} = 1 \right\}.
$$

<mark style="background: #FFF3A3A6;">仿射包是包含 C 的最小仿射集</mark>，意义如下：如果 $S$ 是任何包含 $C$ 的仿射集，那么 aff $C \subseteq S$。
![[数学书/凸优化/附件/Pasted image 20260208172817.png]]
# 2.1.3 仿射维数与相对内部

我们将集合 $C$ 的仿射维数定义为其仿射包的维数。仿射维数在凸分析和优化中很有用，但并不总是与其他维数定义一致。例如，考虑 $\mathbf { R } ^ { 2 }$ 中的单位圆，即 $\{ x \in \mathbf { R } ^ { \ Q } \mid x _ { 1 } ^ { 2 } + x _ { 2 } ^ { 2 } = 1 \}$。它的仿射包是整个 $\mathbf { R } ^ { 2 }$，所以它的仿射维数是二。然而，根据大多数维数定义，$\mathbf { R } ^ { 2 }$ 中的单位圆具有维数一。

如果集合 $C \subseteq \mathbf { R } ^ { n }$ 的<mark style="background: #FFF3A3A6;">仿射维数</mark>小于 $n$，那么该集合位于仿射集 aff $C \neq \mathbf { R } ^ { n }$ 中（$C$ <mark style="background: #FFF3A3A6;">是其仿射集的子集</mark>）。我们定义集合 $C$ 的相对内部，记作 relint $C$，为其相对于 aff $C$ 的内部：

存在正数半径r，使得球与<mark style="background: #FFF3A3A6;">仿射包的交集（interior去掉这一部分）</mark>完全位于集合C内，则该点在C的相对内部。

$$
\operatorname {r e l i n t} C = \{x \in C \mid B (x, r) \cap \operatorname {aff} C \subseteq C \text { for some } r > 0 \},
$$

其中 $B ( x , r ) = \{ y \mid \| y - x \| \leq r \}$，是以 $x$ 为中心、半径为 $r$ 的球（在范数 $\| \cdot \|$ 下）。（这里 $\| \cdot \|$ 是任意范数；所有范数定义相同的相对内部。）然后我们可以定义集合 $C$ 的相对边界为 $\mathbf { c l } C \ \backslash \ \mathbf { r e l i n t } C$，其中 $\mathbf { c l } { \boldsymbol { C } }$ 是 $C$ 的闭包（<mark style="background: #FFF3A3A6;">closure，包含C的最小闭集</mark>）。

例 2.2 考虑 $\mathbf { R } ^ { 3 }$ 中 $( x _ { 1 } , x _ { 2 } )$ 平面上的一个正方形，定义为

$$
C = \{x \in \mathbf {R} ^ {3} \mid - 1 \leq x _ {1} \leq 1, - 1 \leq x _ {2} \leq 1, x _ {3} = 0 \}.
$$

它的仿射包是 $( x _ { 1 } , x _ { 2 } )$ 平面，即 aff $C = \{ x \in \mathbf { R } ^ { 3 } \mid x _ { 3 } = 0 \}$。$C$ 的内部是空的，但相对内部是

$$
\operatorname {r e l i n t} C = \left\{x \in \mathbf {R} ^ {3} \mid - 1 <   x _ {1} <   1, - 1 <   x _ {2} <   1, x _ {3} = 0 \right\}.
$$

它的边界（在 $\mathbf { R } ^ { 3 }$ 中）是它自身（定义为$\mathbf { c l } C \ \backslash \ \mathbf { i n t } C$）；它的相对边界是线框轮廓，

$$
\{x \in \mathbf {R} ^ {3} \mid \max  \{| x _ {1} |, | x _ {2} | \} = 1, x _ {3} = 0 \}.
$$

# 2.1.4 凸集

如果 $C$ 中任意两点之间的线段位于 $C$ 中，则集合 $C$ 是凸的，即，如果对于任何 $x _ { 1 } , x _ { 2 } \in C$ 和任何满足 $0 \leq \theta \leq 1$ 的 $\theta$，我们有

$$
\theta x _ {1} + (1 - \theta) x _ {2} \in C.
$$

![](数学书/凸优化/images/a89c60fbaa31fc1b6538edce57e1d5b17bc26bf582ea91d579cdd42694d798c8.jpg)

![](数学书/凸优化/images/5a779a4f8fbcbfebb880d07784f63e534ca4a854b3f3c52b346c73e9a8680d8d.jpg)
图 2.2 一些简单的凸和非凸集。左图：包含其边界（显示为较暗）的六边形是凸的。中图：肾形集合不是凸的，因为图中显示为点的两点之间的线段不包含在集合中。右图：正方形包含一些边界点但不包含其他边界点，因此不是凸的。
图 2.3 $\mathbf { R } ^ { 2 }$ 中两个集合的<mark style="background: #FFF3A3A6;">凸包</mark>。左图：十五个点（显示为点）的凸包是五边形（显示为阴影区域）。右图：图 2.2 中肾形集合的凸包是阴影区域。

粗略地说，如果一个集合中的每个点都可以被集合中的其他点沿着它们之间一条无障碍的直线路径看到，则该集合是凸的，其中无障碍意味着位于集合内。<mark style="background: #FFF3A3A6;">每个仿射集也是凸的，因为它包含其任意两个不同点之间的整条直线，因此也包含这两点之间的线段。</mark>图 2.2 展示了 $\mathbf { R } ^ { 2 }$ 中一些简单的凸和非凸集合。

我们将形如 $\theta _ { 1 } x _ { 1 } + \cdot \cdot \cdot + \theta _ { k } x _ { k }$，其中 $\theta _ { 1 } + \cdot \cdot \cdot + \theta _ { k } = 1$ 且 $\theta _ { i } \geq 0$，$i = 1 , \ldots , k$ 的点称为点 $x _ { 1 }$ , . . . , $x _ { k }$ 的凸组合。与仿射集类似，可以证明一个集合是凸的当且仅当它包含其点的每个凸组合。点的凸组合可以看作是点的混合或加权平均，其中 $\theta _ { i }$ 是 $x _ { i }$ 在混合中的比例。

集合 $C$ 的凸包，记作 conv $C$，是 $C$ 中所有点的凸组合的集合：

$$
\mathbf {c o n v} C = \left\{\theta_ {1} x _ {1} + \dots + \theta_ {k} x _ {k} \mid x _ {i} \in C, \theta_ {i} \geq 0, i = 1, \dots , k, \theta_ {1} + \dots + \theta_ {k} = 1 \right\}.
$$

顾名思义，凸包 conv $C$ 总是凸的。它是包含 $C$ 的<mark style="background: #FFF3A3A6;">最小凸集</mark>：如果 $B$ 是任何包含 $C$ 的凸集，那么 conv $C \subseteq$ $B$。图 2.3 说明了凸包的定义。

凸组合的概念可以推广到包括无穷和、积分，以及最一般形式下的概率分布。假设 $\theta _ { 1 } , \theta _ { 2 } , \ldots$ 满足

$$
\theta_ {i} \geq 0, \quad i = 1, 2, \dots , \quad \sum_ {i = 1} ^ {\infty} \theta_ {i} = 1,
$$

且 $x _ { 1 } , x _ { 2 } , \dotsc \in C$，其中 $C \subseteq \mathbf { R } ^ { n }$ 是凸的。那么

$$
\sum_ {i = 1} ^ {\infty} \theta_ {i} x _ {i} \in C,
$$

如果级数收敛。

<mark style="background: #FFF3A3A6;">最一般地</mark>，假设 $p : \mathbf { R } ^ {n } \to \mathbf { R }$ 满足对于所有 $x \in C$ 有 $p ( x ) \geq 0$ 且 $\int _ { C } p ( x )$ dx = 1，其中 $C \subseteq \mathbf { R } ^ { n }$ 是凸的。那么

$$
\int_ {C} p (x) x d x \in C,
$$

如果积分存在。

在最一般的形式中，假设 $C \subseteq \mathbf { R } ^ { n }$ 是凸的，且 $x$ 是一个随机向量，以概率一满足 $x \in C$。那么 $\mathbf { E } x \in C$。实际上，这种形式包含了所有其他情况作为特例。例如，假设随机变量 $x$ 只取两个值 $x _ { 1 }$ 和 $x _ { 2 }$，且 $\mathbf { p r o b } ( x = x _ { 1 } ) = \theta$ 和 $\mathbf { p r o b } ( x = x _ { 2 } ) = 1 - \theta$，其中 $0 \leq \theta \leq 1$。那么 $\mathbf { E } x = \theta x _ { 1 } + ( 1 - \theta ) x _ { 2 }$，我们又回到了两个点的简单凸组合。

# 2.1.5 锥

如果对于每个 $x \in C$ 和 $\theta \geq 0$ 我们有 $\theta x \in C$，则集合 $C$ 称为锥，或非负齐次的。如果集合 $C$ 既是凸的又是锥，则它是凸锥，这意味着对于任何 $x _ { 1 } , x _ { 2 } \in C$ 和 $\theta _ { 1 } , \ \theta _ { 2 } \geq 0$，我们有

$$
\theta_ {1} x _ {1} + \theta_ {2} x _ {2} \in C.
$$

这种形式的点几何上可以描述为形成以 0 为顶点、边通过 $x _ { 1 }$ 和 $x _ { 2 }$ 的二维扇形。（见图 2.4。）

形如 $\theta _ { 1 } x _ { 1 } + \cdot \cdot \cdot + \theta _ { k } x _ { k }$ 且 $\theta _ { 1 } , \ldots , \theta _ { k } \ \geq \ 0$ 的点称为 $x _ { 1 } , \ldots , x _ { k }$ 的锥组合（或非负线性组合）。如果 $x _ { i }$ 在凸锥 $C$ 中，那么 $x _ { i }$ 的每个锥组合都在 $C$ 中。反之，集合 $C$ 是凸锥当且仅当它包含其元素的所有锥组合。与凸（或仿射）组合类似，锥组合的概念可以推广到无穷和和积分。

集合 $C$ 的锥包是 $C$ 中所有点的锥组合的集合，即，

$$
\left\{\theta_ {1} x _ {1} + \dots + \theta_ {k} x _ {k} \mid x _ {i} \in C, \theta_ {i} \geq 0, i = 1, \dots , k \right\},
$$

它也是包含 $C$ 的最小凸锥（见图 2.5）。

![](数学书/凸优化/images/643db35a8da2f4e06fe05ee3ac09758796262ed1fb663d3b717f1cfdfa32a016.jpg)
图 2.4 扇形显示了所有形如 $\theta _ { 1 } x _ { 1 } + \theta _ { 2 } x _ { 2 }$ 的点，其中 $\theta _ { 1 } , \ \theta _ { 2 } \geq 0$。扇形的顶点（对应 $\theta _ { 1 } = \theta _ { 2 } = 0$）在 $_ 0$ 处；其边（对应 $\theta _ { 1 } = 0$ 或 $\theta _ { 2 } = 0$）通过点 $x _ { 1 }$ 和 $x _ { 2 }$。

![](数学书/凸优化/images/efe70d12bc16893829c82f6149afca63f0b34da3a1f77adfd3a76df50472ab67.jpg)

![](数学书/凸优化/images/015bdb258e6a51c4b28e3cc20682e0a3dfa97e54d787f039fc68fd9d2c33f2fb.jpg)
图 2.5 图 2.3 中两个集合的锥包（显示为阴影区域）。

# 2.2 一些重要的例子

在本节中，我们将描述一些重要的凸集例子，这些例子将在本书的其余部分中遇到。我们从一些简单的例子开始。

• 空集 $\varnothing$、任何单点集（即单元素集）$\{ x _ { 0 } \}$ 和整个空间 $\mathbf { R } ^ { n }$ 是仿射（因此也是凸）的。
• 任何直线都是仿射的。如果它通过零点，则它是一个子空间，因此也是一个凸锥。
• 线段是凸的，但不是仿射的（除非它退化为一个点）。
• 射线，其形式为 $\{ x _ { 0 } + \theta v \mid \theta \geq 0 \}$，其中 $v \neq 0$，是凸的，但不是仿射的。如果其基点 $x _ { 0 }$ 是 $0$，则它是一个凸锥。
• 任何子空间都是仿射的，并且是凸锥（因此是凸的）：子空间必然经过原点。


# 2.2.1 超平面与半空间

超平面是形如

$$
\{x \mid a ^ {T} x = b \},
$$

的集合，其中 $a \in \mathbf { R } ^ { n }$，$a \neq 0$，且 $b \in \mathbf { R }$。解析上，它是 $x$ 的分量之间一个非平凡线性方程的解集（因此是仿射集）。几何上，超平面 $\{ x \mid a ^ { \prime } x = b \}$ 可以解释为与给定向量 $a$ 具有恒定内积的点集，或者解释为具有法向量 $a$ 的超平面；常数 $b \in \mathbf { R }$ 决定了超平面与原点的偏移量。这种几何解释可以通过将超平面表示为以下形式来理解：

$$
\{x \mid a ^ {T} (x - x _ {0}) = 0 \},
$$

其中 $x _ { 0 }$ 是超平面中的任意点（即满足 $a ^ { T } x _ { 0 } = b$ 的任何点）。这种表示又可以表示为

$$
\{x \mid a ^ {T} (x - x _ {0}) = 0 \} = x _ {0} + a ^ {\perp},
$$

其中 $a ^ { \perp }$ 表示 $a$ 的正交补，即所有与 $a$ 正交的向量的集合：

$$
a ^ {\perp} = \left\{v \mid a ^ {T} v = 0 \right\}.
$$

这表明超平面由一个偏移 $x _ { 0 }$ 加上所有与（法）向量 $a$ 正交的向量组成。这些几何解释如图 2.6 所示。

超平面将 $\mathbf { R } ^ { n }$ 分成两个半空间。（闭）半空间是形如

$$
\{x \mid a ^ {T} x \leq b \}, \tag {2.1}
$$

的集合，其中 $a \neq 0$，即一个（非平凡）线性不等式的解集。半空间是凸的，但不是仿射的。如图 2.7 所示。

![](数学书/凸优化/images/9972cc908a9e7fb67b6834d650c6a0174afb76cc756aa72b7d3b579b90a161ef.jpg)
图 2.6 $\mathbf { R } ^ { 2 }$ 中的超平面，具有法向量 $a$ 和超平面中的一个点 $x _ { 0 }$。对于超平面中的任意点 $_ { x }$，$x - x _ { 0 }$（显示为较暗的箭头）与 $^ { a }$ 正交。

![](数学书/凸优化/images/86126f40eeca5c17f494a4d742e4aa98c04dc07ea34f67eb0a845dbbf58a5e47.jpg)
图 2.7 $\mathbf { R } ^ { 2 }$ 中由 $a ^ { x } x = b$ 定义的超平面确定了两个半空间。由 $a ^ { x } x \geq b$ 确定的半空间（未阴影）是沿 $a$ 方向延伸的半空间。由 $a ^ { x } x \leq b$ 确定的半空间（显示为阴影）沿 $- a$ 方向延伸。向量 $a$ 是这个半空间的外法线。

![](数学书/凸优化/images/7ccf1ed3c829012d7ca4cb433bbea169c2e2338a967b13674b1e31a004063df0.jpg)
图 2.8 阴影区域是由 $a ^ { \prime } ( x - x _ { 0 } ) \leq 0$ 确定的半空间。向量 $x _ { 1 } - x _ { 0 }$ 与 $a$ 成锐角，所以 $x _ { 1 }$ 不在半空间中。向量 $x _ { 2 } - x _ { 0 }$ 与 $a$ 成钝角，因此在半空间中。

半空间 (2.1) 也可以表示为

$$
\{x \mid a ^ {T} (x - x _ {0}) \leq 0 \}, \tag {2.2}
$$

其中 $x _ { 0 }$ 是关联超平面上的任意点，即满足 $a ^ { \mathrm { { ' } } } x _ { 0 } = b$。表示 (2.2) 提出了一个简单的几何解释：半空间由 $x _ { 0 }$ 加上任何与（外法线）向量 $a$ 成钝角（或直角）的向量组成。如图 2.8 所示。

半空间 (2.1) 的边界是超平面 $\{ x \mid a ^ { \prime } x = b \}$。集合 $\{ x \mid a ^ { T } x < b \}$，即<mark style="background: #FFF3A3A6;">半空间</mark> $\{ x \mid a ^ { T } x \leq b \}$ 的内部，称为<mark style="background: #FFF3A3A6;">开半空间</mark>。

# 2.2.2 欧几里得球与椭球

$\mathbf { R } ^ { n }$ 中的（欧几里得）球（或简称球）具有形式

$$
B \left(x _ {c}, r\right) = \left\{x \mid \| x - x _ {c} \| _ {2} \leq r \right\} = \left\{x \mid \left(x - x _ {c}\right) ^ {T} \left(x - x _ {c}\right) \leq r ^ {2} \right\},
$$

其中 $r > 0$，且 $\| \cdot \| _ { 2 }$ 表示欧几里得范数，即 $\| u \| _ { 2 } = ( u ^ { T } u ) ^ { 1 / 2 }$。向量 $x _ { c }$ 是球的中心，标量 $r$ 是其半径；$\boldsymbol { B } ( \boldsymbol { x } _ { c } , \boldsymbol { r } )$ 由所有与中心 $x _ { c }$ 距离不超过 $r$ 的点组成。欧几里得球的另一种常见表示是

$$
B \left(x _ {c}, r\right) = \left\{x _ {c} + r u \mid \| u \| _ {2} \leq 1 \right\}.
$$

![](数学书/凸优化/images/0079f16831776421994779e63dd61fa9d471503c82bc1461f7019b19ef5c3e65.jpg)
图 2.9 $\mathbf { R } ^ { 2 }$ 中的椭球，显示为阴影区域。中心 $x _ { c }$ 显示为一个点，两个半轴显示为线段。

欧几里得球是一个凸集：如果 $\| x _ { 1 } - x _ { c } \| _ { 2 } \ \leq \ r$，$\| x _ { 2 } - x _ { c } \| _ { 2 } \ \leq \ r$，且 $0 \leq \theta \leq 1$，那么

$$
\begin{array}{l} \left\| \theta x _ {1} + (1 - \theta) x _ {2} - x _ {c} \right\| _ {2} = \left\| \theta \left(x _ {1} - x _ {c}\right) + (1 - \theta) \left(x _ {2} - x _ {c}\right) \right\| _ {2} \\ \leq \theta \| x _ {1} - x _ {c} \| _ {2} + (1 - \theta) \| x _ {2} - x _ {c} \| _ {2} \\ \leq r. \\ \end{array}
$$

（这里我们使用了 $\lVert \cdot \rVert _ { 2 }$ 的齐次性质和三角不等式；见 §A.1.2。）

一个相关的凸集族是椭球，其形式为

$$
\mathcal {E} = \left\{x \mid \left(x - x _ {c}\right) ^ {T} P ^ {- 1} \left(x - x _ {c}\right) \leq 1 \right\}, \tag {2.3}
$$

其中 $P = P ^ { T } \succ 0$，即 $P$ 是对称正定的。向量 $x _ { c } \in \mathbf { R } ^ { \pi }$ 是椭球的中心。矩阵 $P$ 决定了椭球从 $x _ { c }$ 向每个方向延伸多远；$\varepsilon$ 的半轴长度由 $\sqrt { \lambda _ { i } }$ 给出，其中 $\lambda _ { i }$ 是 $P$ 的特征值。球是 $P = r ^ { 2 } I$ 的椭球。图 2.9 显示了 $\mathbf { R } ^ { 2 }$ 中的一个椭球。

椭球的另一种常见表示是

$$
\mathcal {E} = \left\{x _ {c} + A u \mid \| u \| _ {2} \leq 1 \right\}, \tag {2.4}
$$

其中 $A$ 是方阵且非奇异（$P=AA^{T}$）。在这种表示中，我们可以不失一般性地（==因为第二种定义会出现碰撞——两个不同的A产生一个相同的椭球，但第一种不会==）假设 $A$ 是对称正定的。取 $A = P ^ { 1 / 2 }$，这种表示给出了 (2.3) 中定义的椭球。当 (2.4) 中的矩阵 $A$ 是奇异矩阵时，(2.4) 中的集合称为退化椭球；==其仿射维数等于 $A$ 的秩==。退化椭球也是凸的。

![[数学书/凸优化/附件/Pasted image 20260208210545.png]]

# 2.2.3 范数球与范数锥

假设 $\left\| \cdot \right\|$ 是 $\mathbf { R } ^ { n }$ 上的任意范数（见 §A.1.2）。根据范数的一般性质，可以证明半径为 $r$、中心为 $x _ { c }$ 的范数球 $\{ x \mid \| x - x _ { c } \| \leq r \}$ 是凸的。与范数 $\| \cdot \|$ 相关联的范数锥是集合

$$
C = \{(x, t) \mid \| x \| \leq t \} \subseteq \mathbf {R} ^ {n + 1}.
$$

![](数学书/凸优化/images/0f5c7d4944e39c93d282af2ff684ffe548ef91110c7d68fe700a4f4d96cd1188.jpg)
图 2.10 $\mathbf { R } ^ { 3 }$ 中二阶锥的边界，$\begin{array} { r } { \{ ( x _ { 1 } , x _ { 2 } , t ) \mid ( x _ { 1 } ^ { 2 } + x _ { 2 } ^ { 2 } ) ^ { 1 / 2 } \leq } \end{array}$ $t \}$。

它（顾名思义）是一个凸锥。

例 2.3 二阶锥是欧几里得范数的范数锥，即，

$$
\begin{array}{l} C = \{(x, t) \in \mathbf {R} ^ {n + 1} \mid \| x \| _ {2} \leq t \} \\ = \left\{\left[ \begin{array}{c} x \\ t \end{array} \right] \Bigg | \left[ \begin{array}{c} x \\ t \end{array} \right] ^ {T} \left[ \begin{array}{c c} I & 0 \\ 0 & - 1 \end{array} \right] \left[ \begin{array}{c} x \\ t \end{array} \right] \leq 0, t \geq 0 \right\}. \\ \end{array}
$$

二阶锥也有其他几个名称。它被称为二次锥，因为它由二次不等式定义。它也被称为洛伦兹锥或冰淇淋锥。图 2.10 显示了 $\mathbf { R } ^ { 3 }$ 中的二阶锥。

![[数学书/凸优化/附件/Pasted image 20260208214345.png]]
# 2.2.4 多面体 (Polyhera)

多面体定义为有限个线性等式和不等式的解集：

$$
\mathcal {P} = \{x \mid a _ {j} ^ {T} x \leq b _ {j}, j = 1, \dots , m, c _ {j} ^ {T} x = d _ {j}, j = 1, \dots , p \}. \tag {2.5}
$$

因此，多面体是有限个半空间和超平面的交集。仿射集（例如子空间、超平面、直线）、射线、线段和半空间都是多面体。很容易证明多面体是凸集（线性可加）。==有界多面体有时称为多胞体==，但有些作者使用相反的约定（即，多胞体指任何形如 (2.5) 的集合，而多面体指有界的情况）。

![[数学书/凸优化/images/81bd7bb0c6d63039c601cfb434e905b8b94084dba6db6a88e6b0dcd2ac8346a1.jpg]]  
图 2.11 多面体 $\mathcal { P }$（阴影部分）是五个半空间的交集，其外向法向量为 $a _ { 1 } , \ldots , a _ { 5 }$。

使用紧凑记号会很方便：

$$
\mathcal {P} = \{x \mid A x \preceq b, C x = d \} \tag {2.6}
$$

表示 (2.5)，其中

$$
A = \left[ \begin{array}{c} a _ {1} ^ {T} \\ \vdots \\ a _ {m} ^ {T} \end{array} \right], \qquad C = \left[ \begin{array}{c} c _ {1} ^ {T} \\ \vdots \\ c _ {p} ^ {T} \end{array} \right],
$$

符号 $\preceq$ 表示 $\mathbf { R } ^ { m }$ 中的向量不等式或分量不等式：==$u \preceq v$ 意味着对于 $i = 1 , \ldots , m$，有 $u _ { i } \leq v _ { i }$。==

**例 2.4** 非负象限是具有非负分量的点集，即

$$
\mathbf {R} _ {+} ^ {n} = \{x \in \mathbf {R} ^ {n} \mid x _ {i} \geq 0, i = 1, \dots , n \} = \{x \in \mathbf {R} ^ {n} \mid x \succeq 0 \}.
$$

（这里 $\mathbf { R } _ { + }$ 表示非负数的集合：$\mathbf { R } _ { + } = \{ x \in \mathbf { R } \mid x \geq 0 \}$。）非负象限是一个多面体也是一个锥（因此称为多面体锥）。

# 单纯形（simplexes）

单纯形是另一类重要的多面体。假设 $k + 1$ 个点 $v _ { 0 } , \ldots , v _ { k } \ \in \ \mathbf { R } ^ { n }$ 是==**仿射无关**==的，这意味着 $v _ { 1 } - v _ { 0 } , \ldots , v _ { k } - v _ { 0 }$ (共k项)是线性无关的。由它们确定的单纯形由下式给出：

$$
C = \operatorname {c o n v} \left\{v _ {0}, \dots , v _ {k} \right\} = \left\{\theta_ {0} v _ {0} + \dots + \theta_ {k} v _ {k} \mid \theta \succeq 0, \mathbf {1} ^ {T} \theta = 1 \right\}, \tag {2.7}
$$

其中 1 表示所有分量为 1 的向量。这个单纯形的仿射维数是 $k$，因此有时==称其为 $\mathbf { R } ^ { n }$ 中的 $k$ 维单纯形。==

**例 2.5** 一些常见的单纯形。1 维单纯形是线段；2 维单纯形是三角形（包括其内部）；==3 维单纯形是四面体。==

==单位单纯形==是由零向量和单位向量确定的 $n$ 维单纯形，即 $\mathbf { R } ^ { n }$ 中的 0, $e _ { 1 } , \ldots , e _ { n }$。它可以表示为满足以下条件的向量集合：

$$
x \succeq 0, \quad \mathbf {1} ^ {T} x \leq 1.
$$

==概率单纯形==是由单位向量 $e _ { 1 } , \ldots , e _ { n } \in \mathbf { R } ^ { n }$ 确定的 $( n - 1 )$ 维单纯形。它是满足以下条件的向量集合：

$$
x \succeq 0, \quad \mathbf {1} ^ {T} x = 1.
$$

概率单纯形中的向量对应于具有 $n$ 个元素的集合上的概率分布，==其中 $x _ { i }$ 解释为第 i 个元素的概率。（满足正定性，正则性）==

为了将单纯形 (2.7) 描述为多面体，即形如 (2.6) 的形式，我们按如下步骤进行。

证明：
根据定义，$x \in C$ 当且仅当 $x = \theta _ { 0 } v _ { 0 } + \theta _ { 1 } v _ { 1 } + \cdot \cdot \cdot + \theta _ { k } v _ { k }$ 对于某个满足 $\mathbf { 1 } ^ { T } \theta = 1$ 的 $\theta \succeq 0$ 成立。等价地，如果我们定义 $y = ( \theta _ { 1 } , \ldots , \theta _ { k } )$ 和

$$
B = \left[ \begin{array}{c c c} v _ {1} - v _ {0} & \dots & v _ {k} - v _ {0} \end{array} \right] \in \mathbf {R} ^ {n \times k},
$$

我们可以说 $x \in C$ 当且仅当

$$
x = v _ {0} + B y \tag {2.8}
$$

对于某个满足 $\mathbf { 1 } ^ { T } y \le 1$ 的 $y \succeq 0$ 成立。现在我们注意到，点 $v _ { 0 } , \ldots , v _ { k }$ 的仿射无关性意味着矩阵 $B$ 的秩为 $k$。因此存在一个非奇异矩阵 $A = ( A _ { 1 } , A _ { 2 } ) \in \mathbf { R } ^ { n \times n }$ 使得

$$
A B = \left[ \begin{array}{c} A _ {1} \\ A _ {2} \end{array} \right] B = \left[ \begin{array}{c} I \\ 0 \end{array} \right].
$$

将 (2.8) 左乘 $A$，我们得到

$$
A _ {1} x = A _ {1} v _ {0} + y, \quad A _ {2} x = A _ {2} v _ {0}.
$$

由此我们看到 $x \in C$ 当且仅当 $A _ { 2 } x \ = \ A _ { 2 } v _ { 0 }$，并且向量 $y =$ $A _ { 1 } x - A _ { 1 } v _ { 0 }$ 满足 $y \succeq 0$ 和 $\mathbf { 1 } ^ { T } y \leq 1$。换句话说，我们有 $x \in C$ 当且仅当

$$
A _ {2} x = A _ {2} v _ {0}, \quad A _ {1} x \succeq A _ {1} v _ {0}, \quad \mathbf {1} ^ {T} A _ {1} x \leq 1 + \mathbf {1} ^ {T} A _ {1} v _ {0},
$$

这是 $x$ 的一组线性等式和不等式，因此描述了一个多面体. $\square$


# 多面体的凸包描述

有限集 $\{ v _ { 1 } , \ldots , v _ { k } \}$ 的凸包是

$$
\mathbf {c o n v} \{v _ {1}, \dots , v _ {k} \} = \left\{\theta_ {1} v _ {1} + \dots + \theta_ {k} v _ {k} \mid \theta \succeq 0, \mathbf {1} ^ {T} \theta = 1 \right\}.
$$

这个集合是一个多面体，并且是有界的，但是（除了特殊情况，例如单纯形）用形式 (2.5) 表达它，即通过一组线性等式和不等式，并不简单。

这种凸包描述的推广是

$$
\left\{\theta_ {1} v _ {1} + \dots + \theta_ {k} v _ {k} \mid \theta_ {1} + \dots + \theta_ {m} = 1, \theta_ {i} \geq 0, i = 1, \dots , k \right\}, \tag {2.9}
$$

其中 $m \leq k$。这里我们考虑 $v _ { i }$ 的非负线性组合，但只有前 $m$ 个系数被要求和为一。或者，我们可以将 (2.9) 解释为点 $v _ { 1 } , \ldots , v _ { m }$ 的凸包==加上（向量运算意义上的，不是集合意义上的）==点 $v _ { m + 1 } , \ldots , v _ { k }$ 的锥包。集合 (2.9) 定义了一个多面体，反之，每个多面体都可以用这种形式表示（尽管我们不会证明这一点）。

多面体如何表示的问题很微妙，并且具有非常重要的实际意义。作为一个简单的例子，考虑 $\mathbf { R } ^ { n }$ 中 $\ell _ { \infty }$ 范数的单位球，

$$
C = \{x \mid | x _ {i} | \leq 1, i = 1, \dots , n \}.
$$
![[数学书/凸优化/附件/Pasted image 20260209224617.png]]

集合 $C$ 可以用形式 (2.5) 描述（==半空间与超平面的交集==），包含 $2 n$ （==正负2 × 空间维度n==）个线性不等式 $\pm e _ { i } ^ { {  T } } x \le 1$，其中 $e _ { i }$ 是第 $i$ 个位置为1的单位向量。要用凸包形式 (2.9) 描述它至少需要 $2 ^ { n }$ 个点：

$$
C = \operatorname {c o n v} \left\{v _ {1}, \dots , v _ {2 ^ {n}} \right\},
$$

其中 $v _ { 1 } , \ldots , v _ { 2 ^ { n } }$ 是所有分量都是 1 或 $^ { - 1 }$ 的 $2 ^ { n }$ 个向量。因此，对于大的 $n$，两种描述的大小差异很大。

# 2.2.5 半正定锥

我们使用符号 $\mathbf { S } ^ { n }$ 表示 $n \times n$ 对称矩阵的集合，

$$
\mathbf {S} ^ {n} = \left\{X \in \mathbf {R} ^ {n \times n} \mid X = X ^ {T} \right\},
$$

这是一个维数为 $n ( n + 1 ) / 2$ 的向量空间。我们使用符号 $\mathbf { S } _ { + } ^ { n }$ 表示对称半正定矩阵的集合：

$$
\mathbf {S} _ {+} ^ {n} = \{X \in \mathbf {S} ^ {n} \mid X \succeq 0 \},
$$

符号 $\mathbf { S } _ { + + } ^ { n }$ 表示对称正定矩阵的集合：

$$
\mathbf { S } _ { + + } ^ { n } = \{X \in \mathbf {S} ^ {n} \mid X \succ 0 \}.
$$

（这个符号旨在类比 $\mathbf { R } _ { + }$，表示非负实数，以及 $\mathbf { R } _ { + + }$，表示正实数。）

==集合 $\mathbf { S } _ { + } ^ { n }$ 是一个凸锥==：如果 $\theta _ { 1 } , \theta _ { 2 } \geq 0$ 且 $A$ , $B \in { \mathbf S } _ { + } ^ { n }$，那么 $\theta _ { 1 } A + \theta _ { 2 } B \in \mathbf { S } _ { + } ^ { n }$。这可以直接从半正定的定义看出：对于任何 $\boldsymbol { x } \in \mathbf { R } ^ { \pi }$，我们有

$$
x ^ {T} (\theta_ {1} A + \theta_ {2} B) x = \theta_ {1} x ^ {T} A x + \theta_ {2} x ^ {T} B x \geq 0,
$$

如果 $A \succeq 0$ , $B \succeq 0$ 且 $\theta _ { 1 }$ , $\theta _ { 2 } \geq 0$。

**例 2.6** $\mathbf { S } ^ { 2 }$ 中的半正定锥。我们有

$$
X = \left[ \begin{array}{c c} x & y \\ y & z \end{array} \right] \in \mathbf {S} _ {+} ^ {2} \quad \Longleftrightarrow \quad x \geq 0, \quad z \geq 0, \quad x z \geq y ^ {2}.
$$

这个锥的边界如图 2.12 所示，在 $\mathbf { R } ^ { 3 }$ 中绘制为 $( x , y , z )$。


![[数学书/凸优化/images/c6bb50d1ee1470ca26f5dae5ce30f8083d9425bd3a4ae0c68f94ddce954b1ead.jpg]]  
图 2.12 $\mathbf { S } ^ { 2 }$ 中半正定锥的边界。

# 2.3 保持凸性的运算

在本节中，我们描述一些保持集合凸性的运算，或者允许我们从其他集合构造凸集。这些运算与 §2.2 中描述的简单例子一起，构成了凸集的演算，对于确定或建立集合的凸性很有用。

# 2.3.1 交集

==凸性在交集下保持不变：如果 $S _ { 1 }$ 和 $S _ { 2 }$ 是凸的，那么 $S _ { 1 } \cap S _ { 2 }$ 是凸的。这个性质扩展到无限多个集合的交集：如果对于每个 $\alpha \in { \mathcal { A } }$，$S _ { \alpha }$ 是凸的，那么 $\textstyle \bigcap _ { \alpha \in A } S _ { \alpha }$ 是凸的。==（子空间、仿射集和凸锥也在任意交集下封闭。）作为一个简单的例子，多面体是半空间和超平面（它们是凸的）的交集，因此是凸的。

**例 2.7** 半正定锥 ${ \bf S } _ { + } ^ { n }$ 可以表示为

$$
\bigcap_ {z \neq 0} \{X \in \mathbf {S} ^ {n} \mid z ^ {T} X z \geq 0 \}.
$$

对于每个 $z \neq 0$，$z ^ { T } X z$ 是 $X$ 的一个（不恒为零的）线性函数，所以集合

$$
\{X \in \mathbf {S} ^ {n} \mid z ^ {T} X z \geq 0 \}
$$

实际上是 $\mathbf { S } ^ { n }$ 中的半空间。因此，半正定锥是无限多个半空间的交集，所以是凸的。

**例 2.8** 我们考虑集合

$$
S = \left\{x \in \mathbf {R} ^ {m} \mid | p (t) | \leq 1 \text { for } | t | \leq \pi / 3 \right\}, \tag {2.10}
$$

其中 $\begin{array} { r } { p ( t ) = \sum _ { k = 1 } ^ { m } x _ { k } \cos k t } \end{array}$。集合 $S$ 可以表示为无限多个板（slab）的交集：$\begin{array} { r } { S = \bigcap_ { | t | \leq \pi / 3 } S _ { t } } \end{array}$，其中
$$
S _ {t} = \left\{x \mid - 1 \leq \sum _ { k = 1 } ^ { m } x _ { k } \underbrace{(\cos k t)}_{\text{常数}} \leq 1 \right\},
$$

因此是凸的。定义和集合如图 2.13 和 2.14 所示，其中 $m = 2$。

![[数学书/凸优化/images/ac912070f370203de27f5f4a92d73988dd15a01ff827e811a5a9e71c6d9f239e.jpg]]  
图 2.13 与集合 $S$（定义见 (2.10)，$m = 2$）中的点相关的三个三角多项式。用虚线绘制的三角多项式是另外两个的平均值。

![[数学书/凸优化/images/62b6536ea3fc7b3bbfd92befe82907d64f3f229c12dac6e92fd5fe09b6ff9ef0.jpg]]  
图 2.14 定义在 (2.10) 中的集合 $S$（$m = 2$）显示为图中中间的白色区域。该集合是无限多个板（其中显示了 20 个）的交集，因此是凸的。

在上面的例子中，我们通过将集合表示为（可能是无限的）半空间的交集来建立其凸性。我们将在 §2.5.1 中看到，逆命题也成立：==每个闭凸集 $S$ 是（通常是无限的）半空间的交集。==事实上，==闭凸集 $S$ 是所有包含它的半空间的交集==：

$$
S = \bigcap \{\mathcal {H} \mid \mathcal {H} \text { halfspace }, S \subseteq \mathcal {H} \}.
$$

# 2.3.2 仿射函数

回想一下，函数 $f : \mathbf { R } ^ { n } \rightarrow  \mathbf { R } ^ { m }$ 是仿射的，如果它是一个线性函数和一个常数的和，即如果它具有形式 $f ( x ) = A x + b$，其中 $A \in \mathbf { R } ^ { m \times n }$ 且 $b \in \mathbf { R } ^ { m }$。假设 $S \subseteq \mathbf { R } ^ { n}$ 是凸的，且 $f : \mathbf { R } ^ { n } \rightarrow \mathbf { R } ^ { m }$ 是一个仿射函数。那么 $S$ 在 $f$ 下的像，

$$
f (S) = \{f (x) \mid x \in S \},
$$



是凸的。类似地，如果 $f : \mathbf { R } ^ { k } \rightarrow \mathbf { R } ^ { n }$ 是一个仿射函数，那么 $S$ 在 $f$ 下的逆像，

$$
f ^ {- 1} (S) = \{x \mid f (x) \in S \},
$$

是凸的。

两个简单的例子是缩放和平移。如果 $S \subseteq \mathbf { R } ^ { n }$ 是凸的，$\alpha \in \mathbf { R }$，且 $a \in \mathbf { R } ^ { n }$，那么集合 $\alpha S$ 和 $S + a$ 是凸的，其中

$$
\alpha S = \{\alpha x \mid x \in S \}, \qquad S + a = \{x + a \mid x \in S \}.
$$

凸集到其某些坐标上的投影是凸的：如果 $S \subseteq$ $\mathbf { R } ^ { m } \times \mathbf { R } ^ { n }$ 是凸的，那么

$$
T = \left\{x _ {1} \in \mathbf {R} ^ {m} \mid (x _ {1}, x _ {2}) \in S \text { for some } x _ {2} \in \mathbf {R} ^ {n} \right\}
$$

是凸的。

两个集合的和定义为

$$
S _ {1} + S _ {2} = \{x + y \mid x \in S _ {1}, y \in S _ {2} \}.
$$

==如果 $S _ { 1 }$ 和 $S _ { 2 }$ 是凸的，那么 $S _ { 1 } + S _ { 2 }$ 是凸的。==为了看到这一点，如果 $S _ { 1 }$ 和 $S _ { 2 }$ 是凸的，那么它们的直积或笛卡尔积

$$
S _ {1} \times S _ {2} = \left\{\left(x _ {1}, x _ {2}\right) \mid x _ {1} \in S _ {1}, x _ {2} \in S _ {2} \right\}.
$$

也是凸的。这个集合在线性函数 $f ( x _ { 1 } , x _ { 2 } ) = x _ { 1 } + x _ { 2 }$ 下的像就是和 $S _ { 1 } + S _ { 2 }$。

我们也可以考虑 $S _ { 1 } , \ S _ { 2 } \in \mathbf { R } ^ { n } \times \mathbf { R } ^ { m }$ 的部分和，定义为

$$
S = \left\{\left(x, y _ {1} + y _ {2}\right) \mid \left(x, y _ {1}\right) \in S _ {1}, \left(x, y _ {2}\right) \in S _ {2} \right\},
$$

其中 $\boldsymbol { x } \in \mathbf { R } ^ { n }$ 且 $y _ { i } \in \mathbf { R } ^ { m }$。对于 $m = 0$，部分和给出 $S _ { 1 }$ 和 $S _ { 2 }$ 的交集；对于 $n = 0$，它是集合加法。凸集的部分和是凸的（见练习 2.16，==先证明x组成的集合是凸的，再证明y1+
y2组成的集合是凸集的和，也是凸的==）。

**例 2.9** 多面体。多面体 $\{ x \mid A x \preceq b , C x = d \}$ 可以表示为笛卡尔积（非负象限，原点）在仿射函数 $f ( x ) = ( b - A x , d - C x )$ 下的逆像：

$$
\{x \mid A x \preceq b, C x = d \} = \{x \mid f (x) \in \mathbf {R} _ {+} ^ {m} \times \{0 \} \}.
$$
因此，多面体是凸的。

**例 2.10** 线性矩阵不等式的解集。条件（矩阵比较大小需要看差值是否正定）

$$
A (x) = x _ {1} A _ {1} + \dots + x _ {n} A _ {n} \preceq B, \tag {2.11}
$$

其中 $B$ , $A _ { i } \in { \bf S } ^ { m }$，被称为 $x$ 的线性矩阵不等式（LMI）。（注意与普通线性不等式的相似性，

$$
a ^ {T} x = x _ {1} a _ {1} + \dots + x _ {n} a _ {n} \leq b,
$$

其中 $b , \ a _ { i } \in \mathbf { R }$。）

线性矩阵不等式的解集 $\{ x \mid A ( x ) \preceq B \}$ 是凸的。实际上，它是半正定锥（由半正定矩阵构成）在仿射函数 $f : \mathbf { R } ^ { n }  \rightarrow\mathbf { S } ^ { m }$ 下的逆像，其中 $f ( x ) = B - A ( x )$。

**例 2.11** 双曲锥。集合

$$
\{x \mid x ^ {T} P x \leq (c ^ {T} x) ^ {2}, c ^ {T} x \geq 0 \}
$$

其中 $P \in \mathbf { S } _ { + } ^ { n }$ 且 $c \in \mathbf { R } ^ { n }$，是凸的，因为它是二阶锥，

$$
\{(z, t) \mid z ^ {T} z \leq t ^ {2}, t \geq 0 \},
$$

在仿射函数 $f ( x ) = ( P ^ { 1 / 2 } x , c ^ { T } x )$ 下的逆像。

**例 2.12** 椭球。椭球

$$
\mathcal {E} = \{x \mid (x - x _ {c}) ^ {T} P ^ {- 1} (x - x _ {c}) \leq 1 \},
$$

其中 $P \in \mathbf { S } _ { + + } ^ { n }$，是单位欧几里得球 $\{ u \mid \| u \| _ { 2 } \leq 1 \}$ 在仿射映射 $f ( u ) = P ^ { 1 / 2 } u + x _ { c }$ 下的像。（它也是单位球在仿射映射 $g ( x ) = P ^ { - 1 / 2 } ( x - x _ { c } )$ 下的逆像。）

# 2.3.3 线性分式和透视函数

在本节中，我们探讨一类函数，称为==线性分式函数，它比仿射函数更一般，但仍然保持凸性。==

# 透视函数

我们定义透视函数 $P : \mathbf { R } ^ { n + 1 } \rightarrow  \mathbf { R } ^ { n }$，定义域为 dom $P = \mathbf { R } ^ { n } \times$ $\mathbf { R } _ { + + }$，为 $P ( z , t ) = z / t$。（这里 $\mathbf { R } _ { + + }$ 表示正数的集合：$\mathbf { R } _ { + + } =$ $\{ x \in \mathbf { R } \mid x > 0 \}$。）透视函数缩放或归一化向量，使得最后一个分量为 1，然后去掉最后一个分量。

**备注 2.1** 我们可以将透视函数解释为针孔相机的动作。针孔相机（在 $\mathbf { R } ^ { 3 }$ 中）由一个不透明的水平平面 $x _ { 3 } = 0$ 组成，平面上有一个位于原点的针孔，光线可以通过，还有一个水平像平面 $x _ { 3 } = - 1$。相机上方（即 $x _ { 3 } > 0$）的物体 $x$ 在像平面上的点 $- ( x _ { 1 } / x _ { 3 } , x _ { 2 } / x _ { 3 } , 1 )$ 处形成图像。去掉图像点的最后一个分量（因为它总是 $^ { - 1 }$），点 $x$ 的图像出现在像平面上的 $y = - ( x _ { 1 } / x _ { 3 } , x _ { 2 } / x _ { 3 } ) = - P ( x )$ 处。如图 2.15 所示。

如果 $C \subseteq \mathbf { d o m } P$ 是凸的，那么它的像

$$
P (C) = \{P (x) \mid x \in C \}
$$

是凸的。

![[数学书/凸优化/附件/Pasted image 20260309220726.png]]

这个结果当然是直观的：一个凸的物体，通过针孔相机观察，会产生一个凸的图像。为了证明这个事实，我们证明线段在透视函数下被映射为线段。（这也说得通：一个线段，通过针孔相机观察，会产生一个线段图像。）假设 $x = ( \tilde { x } , x _ { n + 1 } ) , \ y = ( \tilde { y } , y _ { n + 1 } ) \in \mathbf { R } ^ { n + 1 }$ 且 $x _ { n + 1 } > 0$，$y _ { n + 1 } > 0$。那么对于 $0 \leq \theta \leq 1$，

$$
P (\theta x + (1 - \theta) y) = \frac {\theta \tilde {x} + (1 - \theta) \tilde {y}}{\theta x _ {n + 1} + (1 - \theta) y _ {n + 1}} = \mu P (x) + (1 - \mu) P (y),
$$

其中

$$
\mu = \frac {\theta x _ {n + 1}}{\theta x _ {n + 1} + (1 - \theta) y _ {n + 1}} \in [ 0, 1 ].
$$

$\theta$ 和 $\mu$ 之间的这种对应是单调的：当 $\theta$ 在 0 和 1 之间变化时（它扫过线段 $[ x , y ]$），$\mu$ 在 0 和 1 之间变化（它扫过线段 $[ P ( x ) , P ( y ) ] )$。这表明 $P ( [ x , y ] ) = [ P ( x ) , P ( y ) ]$。

现在假设 $C$ 是凸的，且 $C \subseteq \mathbf { d o m } P$（即对于所有 $x \in C$，$x _ { n + 1 } > 0$），且 $x , \ y \in C$。为了建立 $P ( C )$ 的凸性，我们需要证明线段 $[ P ( x ) , P ( y ) ]$ 在 $P ( C )$ 中。但是这个线段是线段 $[ x , y ]$ 在 $P$ 下的像，因此位于 $P ( C )$ 中。

凸集在透视函数下的逆像也是凸的：如果 $C \subseteq \mathbf { R } ^ { n }$ 是凸的，那么

$$
P ^ {- 1} (C) = \{(x, t) \in \mathbf {R} ^ {n + 1} \mid x / t \in C, t > 0 \}
$$

是凸的。

![[数学书/凸优化/附件/Pasted image 20260309220438.png]]

为了证明这一点，假设 $( x , t ) \in P ^ { - 1 } ( C )$，$( y , s ) \in P ^ { - 1 } ( C )$，且 $0 \leq \theta \leq 1$。我们需要证明

$$
\theta (x, t) + (1 - \theta) (y, s) \in P ^ {- 1} (C),
$$

即

$$
\frac {\theta x + (1 - \theta) y}{\theta t + (1 - \theta) s} \in C
$$

（$( \theta t + ( 1 - \theta ) s > 0$ 是显然的）。这由下式得出：


$$
\frac {\theta x + (1 - \theta) y}{\theta t + (1 - \theta) s} = \mu \underbrace{(x / t)}_{\text{属于 } C} + (1 - \mu) \underbrace{(y / s)}_{\text{属于 } C}
$$

其中

$$
\mu = \frac {\theta t}{\theta t + (1 - \theta) s} \in [ 0, 1 ].
$$

# 线性分式函数

线性分式函数是通过将透视函数与仿射函数复合而形成的。假设 $g : \mathbf { R } ^ { n }  \rightarrow \mathbf { R } ^ { m + 1 }$ 是仿射的，即

$$
g (x) = \left[ \begin{array}{c} A \\ c ^ {T} \end{array} \right] x + \left[ \begin{array}{l} b \\ d \end{array} \right], \tag {2.12}
$$

其中 $A \in \mathbf { R } ^ { m \times n }$ , $b \in \mathbf { R } ^ { m }$ , $c \in \mathbf { R } ^ { n }$ , 且 $d \in \mathbf { R }$。函数 $f : \mathbf { R } ^ { n }  \rightarrow \mathbf { R } ^ { m }$ 由 $f = P \circ g$ 给出，即

$$
f (x) = (A x + b) / \left(c ^ {T} x + d\right), \quad \mathbf {d o m} f = \{x \mid c ^ {T} x + d > 0 \}, \tag {2.13}
$$

被称为线性分式（或射影）函数。如果 $c = 0$ 且 $d > 0$，则 $f$ 的定义域为 $\mathbf { R } ^ { n }$，且 $f$ 是一个仿射函数。所以我们可以将仿射函数和线性函数视为线性分式函数的特例。

**备注 2.2** 射影解释。通常将线性分式函数表示为矩阵会很方便

$$
Q = \left[ \begin{array}{c c} A & b \\ c ^ {T} & d \end{array} \right] \in \mathbf {R} ^ {(m + 1) \times (n + 1)} \tag {2.14}
$$

它作用于（乘以）形式为 $( x , 1 )$ 的点，得到 $( A x + b , c ^ { T } x + d )$。然后对这个结果进行缩放或归一化，使其最后一个分量为 1，从而得到 $( f ( x ) , 1 )$。

这种表示可以通过将 $\mathbf { R } ^ { n }$ 与 $\mathbf { R } ^ { n + 1 }$ 中的一组射线相关联来进行几何解释，如下所示。对于 $\mathbf { R } ^ { n }$ 中的每个点 $z$，我们关联 $\mathbf { R } ^ { n + 1 }$ 中的（开）射线 $\mathcal { P } ( z ) = \{ t ( z , 1 ) \mid t > 0 \}$。这条射线的最后一个分量取正值。相反，$\mathbf { R } ^ { n + 1 }$ 中任何以原点为基点且最后一个分量取正值的射线，都可以写为 $\mathcal { P } ( v ) = \{ t ( v , 1 ) \mid t \geq 0 \}$，对于某个 $v \in \mathbf { R } ^ { n }$。$\mathbf { R } ^ { n }$ 与具有正最后一个分量的射线半空间之间的这种（射影）对应关系 $\mathcal { P }$ 是一一对应且满射的。

线性分式函数 (2.13) 可以表示为

$$
f (x) = \mathcal {P} ^ {- 1} (Q \mathcal {P} (x))=\mathcal {P}^{-1}Q(tx,t)^T=\mathcal {P}^{-1}(Atx+bt,C^Ttx+dt)=(A x + b) / \left(c ^ {T} x + d\right).
$$

- 正如透视方程一样，线性分式方程同样会保留凸性。由上面对于线性分式函数是仿射变换和透视变换的复合函数可知。

例2.13 条件概率。假设 $u$ 和 $\boldsymbol { v }$ 是分别在 $\{ 1 , \ldots , n \}$ 和 $\{ 1 , \ldots , m \}$ 上取值的随机变量，并令 $p _ { i j }$ 表示 $\mathbf { p r o b } ( u = i , v = j )$。那么条件概率 $f _ { i j } = \mathbf { p r o b } ( u = i | v = j )$ 由下式给出：

$$
f _ {i j} = \frac {p _ {i j}}{\sum_ {k = 1} ^ {n} p _ {k j}}.
$$

因此，$f$ 是通过 $p$ 的一个线性分式映射得到的。

由此可知，如果 $C$ 是 $( u , v )$ 的一个联合概率凸集，那么给定 $v$ 时 $u$ 的相应条件概率集也是凸的。

图 2.16 展示了一个集合 $C \subseteq \mathbf { R } ^ { 2 }$ 及其在线性分式函数

$$
f (x) = \frac {1}{x _ {1} + x _ {2} + 1} x, \quad \mathbf {d o m} f = \left\{\left(x _ {1}, x _ {2}\right) \mid x _ {1} + x _ {2} + 1 > 0 \right\}.
$$

下的像。 

为理解定义域的从左到右的变换，尝试证明：线性分式函数的逆依旧是线性分式函数。（根据2.13式线性变换可得）
==2026.3.9==
![[数学书/凸优化/附件/Pasted image 20260310005856.png]]


  
# 2.4 广义不等式
# 2.4.1 正常锥与广义不等式

  

一个锥 $K \subseteq \mathbf { R } ^ { n }$ 被称为**正常锥**，如果它满足以下条件：

  

• $K$ 是凸的。  

• $K$ 是闭的。  

• $K$ 是实心的，这意味着它有非空内部。  

• $K$ 是尖的，这意味着它不包含任何直线（或者等价地，$x \in$ $K , \ - x \in K \implies x = 0$ ）。

  

一个正常锥 $K$ 可以用来定义一个**广义不等式**，它是 $\mathbf { R } ^ { n }$ 上的一个偏序，具有 $\mathbf { R }$ 上标准序的许多性质。我们将与正常锥 $K$ 相关联的 $\mathbf { R } ^ { n }$ 上的偏序定义为

  

$$

x \preceq_ {K} y \iff y - x \in K.

$$

  

我们也用 $x \succeq _ { K } y$ 表示 $y \preceq _ { K } x$ 。类似地，我们通过以下方式定义一个关联的严格偏序

  

$$

x \prec_ {K} y \iff y - x \in \operatorname {i n t} K,

$$

  

并用 $x \ \succ _ { K } \ y$ 表示 $y \prec _ { K } x$ 。（为了区分广义不等式 $\preceq _ { K }$ 和严格广义不等式，我们有时将 $\preceq _ { K }$ 称为非严格广义不等式。）

  

当 $K = { \bf R } _ { + }$ 时，偏序 $\preceq _ { K }$ 是 $\mathbf { R }$ 上的通常序 $\leq$，而严格偏序 $\prec _ { K }$ 与 $\mathbf { R }$ 上的通常严格序 $<$ 相同。因此，广义不等式包含了 $\mathbf { R }$ 中普通（非严格和严格）不等式作为特例。

*矩阵的大小比较：Lowner序，$K$定义在半正定锥$S_{+}^n$上。*

**例 2.14 非负象限与分量不等式。** 非负象限 ${ \cal K } = { \bf R } _ { + } ^ { n }$ 是一个正常锥。关联的广义不等式 $\preceq _ { K }$ 对应于向量之间的分量不等式：$x \preceq _ { K } ~ y$ 意味着 $x _ { i } \ \leq \ y _ { i }$，$i = 1 , \ldots , n$。关联的严格不等式对应于分量严格不等式：$x \prec \kappa \ y$ 意味着 $x _ { i } < y _ { i }$，$i = 1 , \ldots , n$。

  

与非负象限相关的非严格和严格偏序出现得非常频繁，以至于我们省略下标 ${ \bf R } _ { + } ^ { n }$；当符号 $\preceq$ 或 $\prec$ 出现在向量之间时，就理解为这种情况。

  

**例 2.15 半正定锥与矩阵不等式。** 半正定锥 $\mathbf { S } _ { + } ^ { n }$ 是 $\mathbf { S } ^ { n }$ 中的一个正常锥。关联的广义不等式 $\preceq _ { K }$ 是通常的矩阵不等式：$X ~ \preceq _ { K } ~ Y$ 意味着 $Y \ - \ X$ 是半正定的。$\mathbf { S } _ { + } ^ { n }$ 的内部（在 $\mathbf { S } ^ { n }$ 中）由正定矩阵组成，因此严格广义不等式也与对称矩阵之间的通常严格不等式一致：$X \prec _ { K } Y$ 意味着 $Y - X$ 是正定的。

  

同样，这里的偏序出现得非常频繁，以至于我们省略下标：对于对称矩阵，我们简单地写成 $X ~ \preceq ~ Y$ 或 $X ~ \prec ~ Y$。广义不等式是相对于半正定锥的，这一点是默认的。

  

**例 2.16 在 $\lfloor 0 , 1 \rfloor$ 上非负的多项式锥。** 设 $K$ 定义为

  

$$

K = \left\{c \in \mathbf {R} ^ {n} \mid c _ {1} + c _ {2} t + \dots + c _ {n} t ^ {n - 1} \geq 0 \text { for } t \in [ 0, 1 ] \right\}, \tag {2.15}

$$

  
![[数学书/凸优化/附件/Figure 1.png]]
即，$K$ 是（系数为）在区间 [0, 1] 上非负的 $n - 1$ 次多项式的锥。可以证明 $K$ 是一个正常锥；它的内部是在区间 $\lfloor 0 , 1 \rfloor$ 上为正的多项式的系数集合。

  

两个向量 $c , d \in \mathbf { R } ^ { n }$ 满足 $c \preceq _ { K }$ d 当且仅当

  

$$

c _ {1} + c _ {2} t + \dots + c _ {n} t ^ {n - 1} \leq d _ {1} + d _ {2} t + \dots + d _ {n} t ^ {n - 1}

$$

  

对于所有 $t \in [ 0 , 1 ]$ 成立。

  

# 广义不等式的性质

  

广义不等式 $\preceq _ { K }$ 满足许多性质，例如

  

• $\preceq _ { K }$ 在加法下保持不变：如果 $x \preceq _ { K } y$ 且 $u \preceq _ { K } v$，那么 $x + u \preceq _ { K } y + v$。  

• $\preceq _ { K }$ 是传递的：如果 $x \preceq _ { K } y$ 且 $y \preceq _ { K } z$，那么 $x \preceq _ { K } z$。  

• $\preceq _ { K }$ 在非负缩放下保持不变：如果 $x ~ \preceq _ { K } ~ y$ 且 $\alpha \geq 0$，那么 $\alpha x ~ \preceq _ { K } ~ \alpha y$ 。  

• $\preceq _ { K }$ 是自反的：$x \preceq _ { K } x$。  

• $\preceq _ { K }$ 是反对称的：如果 $x \preceq _ { K } y$ 且 $y \preceq _ { K } x$，那么 $x = y$。  

• $\preceq _ { K }$ 在极限下保持不变：如果 $x _ { i } \preceq _ { K }y_{i}$  对于 $i = 1 , \ 2 , \ldots$，$x _ { i }\to  x$ 且 $y _ { i } \to y$ 当 $i \to \infty$，那么 $x \preceq _ { K } y$。

  

对应的严格广义不等式 $\prec _ { K }$ 满足，例如，

  

• 如果 $x \prec _ { K } y$，那么 $x \preceq _ { K } y$。  

• 如果 $x \prec _ { K } y$ 且 $u \preceq _ { K } v$，那么 $x + u \prec _ { K } y + v$。  

• 如果 $x \prec _ { K } y$ 且 $\alpha > 0$，那么 $\alpha x \prec _ { K } \alpha y$。  

• $x \not \prec _ { K } x$。  

• 如果 $x \prec _ { K } y$，那么对于足够小的 $u$ 和 $\boldsymbol { v }$，$x + u \prec _ { K } y + v$。

  

这些性质继承自 $\preceq _ { K }$ 和 $\prec _ { K }$ 的定义以及正常锥的性质；参见练习 2.30。

  

# 2.4.2 最小元与极小元

  

广义不等式（即 $\preceq _ { K }$，$\prec _ { K }$）的符号意在暗示与 $\mathbf { R }$ 上普通不等式（即 $\leq$，$<$）的类比。虽然普通不等式的许多性质确实适用于广义不等式，但一些重要的性质并不适用。最明显的区别是 $\mathbf { R }$ 上的 $\leq$ 是一个线性序：任何两点都是可比较的，意味着要么 $x \ \leq \ y$，要么 $y \ \leq \ x$。这个性质对于其他广义不等式不成立。一个含义是，在广义不等式的背景下，像最小和最大这样的概念更加复杂。我们在本节简要讨论这一点。

  

我们说 $x \in S$ 是 $S$ 的**最小元**（关于广义不等式 $\preceq _ { K }$），如果对于每个 $y \in S$，我们有 $x \preceq _ { K } y$。我们类似地定义集合 $S$ 的**最大元**（关于广义不等式）。如果一个集合有最小（最大）元，那么它是唯一的。一个相关的概念是**极小元**。我们说 $x \in S$ 是 $S$ 的一个**极小元**（关于广义不等式 $\preceq _ { K }$），如果 $y \in S$，$y \preceq _ { K } ~ x$ 仅当 $y = x$。我们类似地定义**极大元**。一个集合可以有许多不同的极小（极大）元。

*最小元一定是极小元。极小元不一定是最小元。*
*但是，所有元素可比情况下，二者等价。*
*定义极小元的目的就在于处理不可比情况。*

我们可以使用简单的集合符号来描述最小元和极小元。一个点 $x \in S$ 是 $S$ 的最小元当且仅当

  

$$

S \subseteq x _{+ K}.

$$

  

这里 $x_{+ K}$ 表示所有与 $x$ 可比且大于或等于 $x$ 的点（根据 $\preceq _ { K }$）。一个点 $x \in S$ 是极小元当且仅当

  

$$

(x_{- K}) \cap S = \{x \}.

$$

  

这里 $x_{ - K}$ 表示所有与 $x$ 可比且小于或等于 $x$ 的点（根据 $\preceq _ { K }$）；与 $S$ 的唯一公共点是 $x$。

  

对于 $K = { \bf R } _ { + }$，它诱导了 $\mathbf { R }$ 上的通常序，极小元和最小元的概念是相同的，并且与集合最小元的通常定义一致。

  

**例 2.17** 考虑锥 ${ \bf R } _ { + } ^ { 2 }$，它诱导了 $\mathbf { R } ^ { 2 }$ 中的分量不等式。这里我们可以给出极小元和最小元的一些简单几何描述。不等式 $x \preceq y$ 意味着 $y$ 在 $x$ 的上方和右侧。例如， $x \in S$ 是集合 $S$ 的最小元意味着 $S$ 的所有其他点都在上方和右侧。再例如 ${ x }$ 是集合 $S$ 的一个极小元意味着 $S$ 中没有其他点在 ${ x }$ 的左侧和下方。这如图 2.17 所示。


![[数学书/凸优化/images/adb9cd897c13a502c1da65295ed8c29edd81f598331a36ead85b918594c47789.jpg]]

  

![[数学书/凸优化/images/cedd8ef56e71d2ea2ee84bbb2e37d842060cb2467cf6ccb4eda411be67a28d97.jpg]]  

图 2.17 左。集合 $S _ { 1 }$ 有一个最小元 $x _ { 1 }$，关于 $\mathbf { R } ^ { 2 }$ 中的分量不等式。集合 $x _ { 1 } + K$ 被浅色阴影覆盖；$x _ { 1 }$ 是 $S _ { 1 }$ 的最小元，因为 $S _ { 1 } \subseteq x _ { 1 } + K$。
右。点 $x _ { 2 }$ 是 $S _ { 2 }$ 的一个极小点。集合 $x _ { 2 } - K$ 显示为浅色阴影。点 $x _ { 2 }$ 是极小的，因为 $x _ { 2 } - K$ 和 $S _ { 2 }$ 仅在 $x _ { 2 }$ 处相交，但是$x_{2}$不能与第二第四象限的点比较大小，因此只能是极小元。

**例 2.18 对称正定矩阵集合的最小元和极小元。** 我们与每个 $A \in \mathbf { S } _ { + + } ^ { n }$ 关联一个以原点为中心的椭球，由下式给出
$$

\mathcal {E} _ {A} = \{x \mid x ^ {T} A ^ {- 1} x \leq 1 \}.

$$

我们有 $A \preceq B$ 当且仅当 $\mathcal { E } _ { A } \subseteq \mathcal { E } _ { B }$。
 
 证明：
 $A \preceq B$ 意味着$B^{-1} \preceq A^{-1}$ ，即$B^{-1} - A^{-1}$半负定
 
 如果有$x$满足 $x ^ {T} A ^ {- 1} x \leq 1$，即$x \in \mathcal {E} _ {A}$
 
 那么$x ^ {T} B ^ {- 1} x= x ^ {T}(B^{-1}-A^{-1}+A ^ {- 1} )x=x ^ {T}(B^{-1}-A^{-1})  x+x ^ {T}A ^ {- 1} x\leq 1$
 即$x$一定满足$x\in\mathcal {E} _ {B}$
 因此，$\mathcal { E } _ { A } \subseteq \mathcal { E } _ { B }$. ▯

设 $v _ { 1 } , \ldots , v _ { k } \in \mathbf { R } ^ { n }$ 给定，并定义

$$

S = \left\{P \in \mathbf {S} _ {+ +} ^ {n} \mid v _ {i} ^ {T} P ^ {- 1} v _ {i} \leq 1, i = 1, \dots , k \right\},

$$

  它对应于包含点 $v _ { 1 } , \ldots , v _ { k }$ 的椭球的集合。**集合 $S$ 没有最小元**：对于任何包含点 $v _ { 1 } , \ldots , v _ { k }$ 的椭球，我们可以找到另一个包含这些点且与之不可比的椭球，例如$\mathcal {E} _ {1}$和$\mathcal {E} _ {2}$。**集合 $S$ 有极小元**：一个椭球是极小的，如果它包含这些点，但没有更小的椭球包含它们，例如$\mathcal {E} _ {2}$就是其中之一。图 2.18 展示了 $\mathbf { R } ^ { 2 }$ 中 $k = 2$ 的一个例子。

  
![[数学书/凸优化/images/7cf77ecd1a8705e28c715e3d3f6c2e717402f63ceb246c66f8f59db8adc4ef08.jpg]]  

图 2.18 $\mathbf { R } ^ { 2 }$ 中以原点为中心（显示为下方的点）并包含显示为上方的点的三个椭球。椭球 $\mathcal { E } _ { 1 }$ 不是极小的，因为存在包含这些点且更小的椭球（例如 $\xi _ { 3 }$）。$\xi _ { 3 }$ 由于同样的原因也不是极小的。椭球 $\xi _ { 2 }$ 是极小的，因为没有其他（以原点为中心的）椭球包含这些点且被包含在 $\xi _ { 2 }$ 中。

# 2.5 分离超平面与支撑超平面

# 2.5.1 分离超平面定理

在本节中，我们将描述一个稍后重要的思想：使用超平面或仿射函数来分离不相交的凸集。基本结果是**分离超平面定理**：**假设 $C$ 和 $D$ 是非空不相交凸集，即 $C \cap D = \emptyset$。那么存在 $a \neq 0$ 和 $b$ 使得 $a ^ { T } x \leq b$ 对于所有 $x \in C$ 成立，且 $a ^ { T } x \geq b$ 对于所有 $x \in D$ 成立。** 换句话说，仿射函数 $a ^ { \mathrm { T } } x - b$ 在 $C$ 上非正，在 $D$ 上非负。超平面 $\{ x \mid a ^ { \prime } x = b \}$ 被称为集合 $C$ 和 $D$ 的**分离超平面**，或者说它分离了集合 $C$ 和 $D$。这如图 2.19 所示。

![[数学书/凸优化/images/cfb648836e79ce61b82eb257af7fbf4daa009924c3406b793162ee699804d865.jpg]]  

图 2.19 超平面 $\{ x \mid a ^ { \prime } x = b \}$ 分离了不相交凸集 $C$ 和 $D$。仿射函数 $\boldsymbol { a } ^ { T } \boldsymbol { x } - \boldsymbol { b }$ 在 $C$ 上非正，在 $D$ 上非负。

# 分离超平面定理的证明

==这里我们考虑一个特殊情况，并将证明推广到一般情况留作练习（练习 2.22）。注意此一般化证明！！！==我们假设 $C$ 和 $D$ 之间的（欧几里得）距离，定义为

$$

\operatorname {d i s t} (C, D) = \inf  \left\{\| u - v \| _ {2} \mid u \in C, v \in D \right\},

$$

![[数学书/凸优化/images/87553c15939da66fa2bc66de0bbd5fc3346a3d3029af2855612a187ef0a0c229.jpg]]  

图 2.20 两个凸集之间分离超平面的构造。点 $c \in C$ 和 $d \in D$ 是两个集合中彼此最接近的一对点。分离超平面正交于并平分 $c$ 和 $d$ 之间的线段。


并且存在点 $c \in C$ 和 $d \in D$ 达到最小距离，即 $\| c - d \| _ { 2 } = \mathbf { d i s t } ( C , D )$。（例如，当 $C$ 和 $D$ 是闭的且其中一个集合有界时，这些条件满足。）

定义
$$

a = d - c, \qquad b = \frac {\| d \| _ {2} ^ {2} - \| c \| _ {2} ^ {2}}{2}.

$$
构造仿射函数

$$

f (x) = a ^ {T} x - b = (d - c) ^ {T} (x - (1 / 2) (d + c))

$$

我们将证明**在 $C$ 上非正，在 $D$ 上非负（f（x）的构造方式决定了正负关系，不可能颠倒过来）**，即超平面 $\{ x \mid a ^ { \prime } x = b \}$ 分离了 $C$ 和 $D$。这个超平面垂直于 $c$ 和 $d$ 之间的线段，并通过其中点 ***（x=(1 / 2) (d + c)  ）*** 位于超平面上可以看出，如图 2.20 所示。

  
证明（反证法）：
我们首先证明 $f$ 在 $D$ 上非负。$f$ 在 $C$ 上非正的证明是类似的（或者通过交换 $C$ 和 $D$ 并考虑 $- f$ 得出）。假设存在一个点 $u \in D$ 使得  
$$

f (u) = \left(d - c\right) ^ {T} \left(u - (1 / 2) (d + c)\right) <   0. \tag {2.16}

$$
我们可以将 $f ( u )$ 表示为
$$

f (u) = \left(d - c\right) ^ {T} (u - d + (1 / 2) (d - c)) = \left(d - c\right) ^ {T} (u - d) + (1 / 2) \| d - c \| _ {2} ^ {2}.

$$
我们看到 (2.16) ，模长非负，意味着 $( d - c ) ^ { T } ( u - d ) < 0$。现在我们观察到
$$

\frac{d}{dt}\| d + t(u - d) - c\|_{2}^{2}\bigg|_{t = 0} = 2(d - c)^{T}(u - d) <   0,

$$
所以对于某个小的 $t > 0$，且 $t \leq 1$，我们有
$$

\left\| d + t (u - d) - c \right\| _ {2} <   \left\| d - c \right\| _ {2},

$$
即，点 $d + t ( u - d )$ 比 $d$ 更接近 $c$。由于 $D$ 是凸的且包含 $d$ 和 $u$，我们有 $d + t ( u - d ) \in D$。但这是不可能的，因为 $d$ 被假设为 $D$ 中最接近 $C$ 的点。▯


**例 2.19 仿射集与凸集的分离。** 假设 $C$ 是凸的，$D$ 是仿射的，即 $D = \{ F u + g \mid \text{ 对于所有} u \in \mathbf { R } ^ { m } \}$，其中 $F \in \mathbf { R } ^ { n \times m }$。假设 $C$ 和 $D$ 不相交，那么根据分离超平面定理，存在 $a \neq 0$ 和 $b$ 使得 $a ^ { T } x \leq b$ 对于所有 $x \in C$ 成立，且 $a ^ { T } x \geq b$ 对于所有 $x \in D$ 成立。

现在 $a ^ { T } x \geq b$ 对于所有 $x \in D$ 成立意味着 $a ^ { T } F u \geq b - a ^ { T } g$ 对于所有 $u \in \mathbf { R } ^ { m }$ 成立。但线性函数在 $\mathbf { R } ^ { m }$ 上有下界仅当它的系数矩阵为零，所以我们得出结论 $a ^ { T } F = 0$（因此，$b \leq a ^ { T } \overset { } { \cdot } g$）。

因此我们得出结论：**一定存在 $a \neq 0$ 使得 $F ^ { T } a = 0$ 且 $a ^ { T } x \leq a ^ { T } g$ 对于所有 $x \in C$ 成立。**

# 严格分离

==2026.3.12==
  

我们上面构造的分离超平面满足更强的条件：$a ^ { T } x \ < \ b$ 对于所有 $x \in C$ 成立，且 $a ^ { \mathrm { T } } x > b$ 对于所有 $x \in D$ 成立。这被称为集合 $C$ 和 $D$ 的**严格分离**。==简单的例子表明，一般来说，不相交的凸集不一定能被超平面严格分离（即使集合是闭的；参见练习 2.23）。注意此反例！！！==然而，在许多特殊情况下，可以建立严格分离。
  

**例 2.20 点与闭凸集的严格分离。** 设 $C$ 是一个闭凸集，且 $x _ { 0 } \notin { \cal { C } }$。那么存在一个超平面严格分离 $x _ { 0 }$ 和 $C$。

证明：
![[数学书/凸优化/附件/Pasted image 20260312195647.png|677]]
为了看到这一点，注意对于某个 $\epsilon > 0$，两个集合 $C$ 和 $B ( x _ { 0 } , \epsilon )$ 不相交。根据分离超平面定理，存在 $a \neq 0$ 和 $b$ 使得 $a ^ { T } x \leq b$ 对于 $x \in C$ 成立，且 $a ^ { T } x \geq b$ 对于 $x \in B ( x _ { 0 } , \epsilon )$ 成立。

使用 $B ( x _ { 0 } , \epsilon ) = \{ x _ { 0 } + u \mid \| u \| _ { 2 } \leq \epsilon \}$，第二个条件可以表示为
$$

a ^ {T} \left(x _ {0} + u\right) \geq b \text { for all } \| u \| _ {2} \leq \epsilon .

$$
  
使左边最小的 $u$ 是 $u = - \epsilon a / \| a \| _ { 2 }$（方向相反，模长为$\epsilon$，此时内积最小）；使用这个值我们有
$$

a ^ {T} x _ {0} - \epsilon \| a \| _ {2} \geq b.

$$

因此仿射函数
$$

f (x) = a ^ {T} x - b - \epsilon \| a \| _ {2} / 2

$$

在 $C$ 上为负，在 $x _ { 0 }$ 处为正.▯


现在尝试证明我们之前已经提出过的一个命题：
*一个闭凸集是所有包含它的半空间的交集。*
确实，设 $C$ 是闭凸的，并设 $S$ 是所有包含 $C$ 的半空间的交集。显然 $x \in C \Rightarrow x \in S$。为了证明逆命题，假设存在 $x \in S$（$x$一定位于包含$C$的半空间内），$x \not \in C$。根据严格分离结果，存在一个超平面严格分离 $x$ 和 $C$，即，存在一个包含 $C$ 但不包含 $_ { x }$ 的半空间。换句话说，$x$有可能位于包含$C$的半空间外，自相矛盾。▯

# 分离超平面定理的逆定理

分离超平面定理的逆命题（即，分离超平面的存在意味着 $C$ 和 $D$ 不相交）**并不成立**，除非对 $C$ 或 $D$ 施加额外的约束，甚至超出凸性。作为一个简单的反例，考虑 $C = D = \{ 0 \} \subseteq \mathbf { R }$。这里超平面 $x = 0$ 分离了 $C$ 和 $D$。

*分离超平面本身的定义允许等于符号，导致逆命题并不一定成立。*

通过对 $C$ 和 $D$ 添加条件，可以推导出各种逆分离定理。作为一个非常简单的例子，假设 $C$ 和 $D$ 是凸集，其中 $C$ 是开的，并且存在一个仿射函数 $f$，它在 $C$ 上非正，在 $D$ 上非负。那么 $C$ 和 $D$ 不相交。（为了看到这一点，我们首先注意到 $f$ 在 $C$ 上必须为负：因为如果 $f$ 在 $C$ 的某点为零，那么 $f$ 会在该点附近取正值（*开集本身带来的特性*），这是一个矛盾。因此 $C$ 和 $D$ 必须不相交，因为 $f$ 在 $C$ 上为负，在 $D$ 上非负。）将这个逆命题与分离超平面定理结合起来，我们得到以下结果：**任何两个凸集 $C$ 和 $D$，其中至少有一个是开的，它们不相交当且仅当存在一个分离超平面。**


**例 2.21 严格线性不等式的择一定理（Theorem of alternatives for strict linear inequalities）。** 考虑如下的严格线性不等式系统：

$$

A x \prec b. \tag {2.17}

$$
其解集为下面集合的交集

$$

C = \left\{b - A x \mid x \in \mathbf {R} ^ {n} \right\}, \qquad D = \mathbf {R} _ {+ +} ^ {m} = \left\{y \in \mathbf {R} ^ {m} \mid y \succ 0 \right\}

$$
那么，该系统无解的充要条件为$C$和$D$不相交。

集合 $D$ 是开的；$C$ 是一个仿射集。因此，根据开集的分离超平面逆定理推论，$C$ 和 $D$ 不相交的充要条件为：存在一个分离超平面，即一个非零的 $\lambda \in \mathbf { R } ^ { m }$ 和 $\boldsymbol { \mu } \in \mathbf { R }$ 使得 $\lambda ^ { \prime } y \leq \mu$ 在 $C$ 上成立，且 $\lambda ^ { \prime } \boldsymbol { y } \geq \mu$ 在 $D$ 上成立。

这些条件中的每一个都可以简化。第一个意味着 $\lambda ^ { T } ( b - A x ) \leq \mu$ 对于所有 $_ { x }$ 成立。这蕴含着（根据例 2.19）$A ^ { T } \lambda = 0$ 且 $\lambda ^ { T } b \leq \mu$。第二个不等式意味着 $\lambda ^ { \prime } \boldsymbol { y } \geq \mu$ 对于所有 $y \succ 0$ 成立。这等价于 $\mu \leq 0$ 且 $\lambda \succeq 0$，$\lambda \neq 0$。

  综上所述，我们发现严格不等式系统 (2.17) 不可行当且仅当存在 $\lambda \in \mathbf { R } ^ { m }$ 使得

$$

\lambda \neq 0, \quad \lambda \succeq 0, \quad A ^ {T} \lambda = 0, \quad \lambda^ {T} b \leq 0. \tag {2.18}

$$

这也是变量 $\lambda \in \mathbf { R } ^ { m }$ 中的一个线性不等式和线性方程组。我们说 (2.17) 和 (2.18) 构成一对**择一**：对于任何数据 $A$ 和 $b$，它们中恰好有一个是可解的。

==2026.3.12==

# 2.5.2 支撑超平面

  

假设 $C \subseteq \mathbf { R } ^ { n }$，且 $x _ { 0 }$ 是其边界 $\mathbf { b d } C$ 中的一个点，即，

  

$$

x _ {0} \in \operatorname {b d} C = \operatorname {c l} C \backslash \operatorname {i n t} C.

$$

  

如果 $a \neq 0$ 满足 $a ^ { \scriptscriptstyle T } x \le a ^ { \scriptscriptstyle T } x _ { 0 }$ 对于所有 $x \in C$ 成立，那么超平面 $\{ x \mid a ^ { \prime } x = a ^ { \prime } x _ { 0 } \}$ 被称为在点 $x _ { 0 }$ 处对 $C$ 的**支撑超平面**。这等价于说

  

![[数学书/凸优化/images/6eb9023b4bf6738a9aa9556b805c95d12ea97b65cd0751dc51d05cadabe4e16d.jpg]]  

图 2.21 超平面 $\{ x \mid a ^ { \prime } x = a ^ { \prime } x _ { 0 } \}$ 在 $x _ { 0 }$ 处支撑 $C$

  

点 $x _ { 0 }$ 和集合 $C$ 被超平面 $\{ x \mid a ^ { \prime } x = a ^ { \prime } x _ { 0 } \}$ 分离。几何解释是超平面 $\{ x \mid a ^ { \mathcal { '} } x = a ^ { \mathcal { '} } x _ { 0 } \}$ 在 $x _ { 0 }$ 处与 $C$ 相切，且半空间 $\{ x \mid a ^ { '} x \leq a ^ { ' } x _ { 0 } \}$ 包含 $C$。这如图 2.21 所示。

  

一个称为**支撑超平面定理**的基本结果指出，对于任何非空凸集 $C$ （不等于后面提到的内部为空），以及任何 $x _ { 0 } \in \mathbf { b d } C$，存在一个在 $x _ { 0 }$ 处对 $C$ 的支撑超平面。支撑超平面定理很容易从分离超平面定理证明。我们区分两种情况。如果 $C$ 的内部非空，结果立即通过将分离超平面定理应用于集合 $\{ x _ { 0 } \}$ 和 $\mathbf { i n t } C$ 得出。如果 $C$ 的内部是空的，那么 $C$ 必须位于一个维数小于 $n$ 的仿射集中（存在相对内部），任何包含该仿射集的超平面都包含 $C$ 和 $x _ { 0 }$，并且是一个（平凡的）支撑超平面。

  

支撑超平面定理也有一个部分逆命题：如果一个集合是闭的，有非空内部，并且在边界上的每一点都有支撑超平面，那么它是凸的。（参见练习 2.27。）

证明不复杂，反证法即可，不要绘制具体非凸集图像禁锢思想。凸-->∃中间点不属于集合-->集合非空+集合为闭集-->存在以该点为中心的一个领域都不在集合中-->线段上存在边界-->经过线段内的点的支撑超平面只可能是经过经过这两点的超平面--->这个超平面一定包含集合的内部点（集合非空）--->内部点的一个小领域依旧属于集合-->这个小领域一定未被超平面划分到同侧。

  ==2026.3.24==

# 2.6 对偶锥与广义不等式

  

# 2.6.1 对偶锥

  

设 $K$ 是一个锥。集合

  

$$

K ^ {*} = \left\{y \mid x ^ {T} y \geq 0 \text { for all } x \in K \right\} \tag {2.19}

$$

  

被称为 $K$ 的**对偶锥**。顾名思义，$K ^ { * }$ 是一个锥，并且总是凸的，即使原始锥 $K$ 不是（参见练习 2.31）。

对于任意$y_{1},y_{2}$∈$K^*$，那么任意$\theta_{1},\theta_{2}\geq0$，都满足$x ^ {T} \theta_{1} y_{1} \geq 0 \text { for all } x \in K$；$x ^ {T} \theta_{2} y_{2} \geq 0 \text { for all } x \in K$，因此$x ^ {T} (\theta_{1} y_{1}+\theta_{2} y_{2} )\geq 0 \text { for all } x \in K$ ，即$\theta_{1} y_{1}+\theta_{2} y_{2}$也属于$K^*$.
因此，$K^*$是一个凸锥。

  

几何上，$y \in K ^ { * }$ 当且仅当 $- y$ 是在原点支撑 $K$ 的超平面的法向量。这如图 2.22 所示。

  

![[数学书/凸优化/images/a5890b3dcbe796bedc7999b8c4341c890b4f7e1e16c190b19cd433d5f56b9712.jpg]]

  

![[数学书/凸优化/images/8e9e2eb0549c199cf05c7bce154cca22496a0f44c3856d37830881edb6f95fb1.jpg]]  

图 2.22 左。具有内向法向量 $y$ 的半空间包含锥 $K$，所以 $y \in K ^ { * }$。右。具有内向法向量 $z$ 的半空间不包含 $K$，所以 $z \not \in K ^ { * }$。

  

**例 2.23 非负象限。** 锥 $\mathbf { R } _ { + } ^ { n }$ 是自对偶的：

  

$$

x ^ {T} y \geq 0 \text { for all } x \succeq 0 \iff y \succeq 0.

$$

  

我们称这样的锥为**自对偶**的。

  

**例 2.24 半正定锥。** **在对称 $n \times n$ 矩阵集合 $\mathbf { S } ^ { n }$ 上**，我们使用标准内积 $\begin{array} { r } { \mathbf { t r } ( X Y ) = \sum _ { i , j = 1 } ^ { n } X _ { i j } Y _ { i j } } \end{array}$ （参见 §A.1.1）。半正定锥 $\mathbf { S } _ { + } ^ { n }$ 是自对偶的，即，对于 $X$，$Y \in \mathbf { S } ^ { n }$，

  

$$

\operatorname {t r} (X Y) \geq 0 \text { for all } X \succeq 0 \iff Y \succeq 0.

$$

  

我们将证明这个事实。

  

假设 $Y \not \in { \mathbf { S } } _ { + } ^ { n }$。那么存在 $q \in \mathbf { R } ^ { n }$ 使得

  

$$

q ^ {T} Y q = \mathbf {t r} (q q ^ {T} Y) <   0.

$$

  

因此半正定矩阵 $X = q q ^ { T }$ 满足 $\mathbf { t r } ( X Y ) < 0$；由此得出 $Y \not \in ( \mathbf { S } _ { + } ^ { n } ) ^ { * }$。

  

现在假设 $\begin{array} { r } { X = \sum _ { i = 1 } ^ { n } \lambda _ { i } q _ { i } q _ { i } ^ { T } } \end{array}$。 由于$X$，$Y \in { \bf S } _ { + } ^ { n }$，我们可以将 $X$ 用其特征值分解表示为 $\lambda _ { i } \geq 0$，$i = 1 , \ldots , n$。那么我们有

  

$$
\mathbf{tr}(Y X) = \mathbf{tr}\left(Y \sum_{i=1}^{n} \lambda_{i} q_{i} q_{i}^{T}\right) = \sum_{i=1}^{n} \lambda_{i} q_{i}^{T} Y q_{i} \geq 0.
$$

这表明 $Y \in (\mathbf{S}_{+}^{n})^{*}$。

**例 2.25 范数锥的对偶。** 设 $|| \cdot ||$ 是 $\mathbf{R}^{n}$ 上的一个范数。关联锥 $K = \{(x, t) \in \mathbf{R}^{n+1} \mid ||x|| \leq t\}$ 的对偶是由对偶范数定义的锥，即

$$
K^{*} = \{(u, v) \in \mathbf{R}^{n+1} \mid \| u \| _ {*} \leq v \},
$$

其中对偶范数由 $\| u \| _ { * } = \operatorname*{sup} \{ u ^ { T } x \mid \| x \| \leq 1 \}$ 给出（见 (A.1.6)）。

为了证明这个结果，我们需要证明

$$
x ^ {T} u + t v \geq 0 \text { 对于所有 } \| x \| \leq t \Longleftrightarrow \| u \| _ {*} \leq v. \tag {2.20}
$$

让我们从证明 $(u, v)$ 的右侧条件蕴含左侧条件开始。假设 $\| u \| _ { * } \leq v$，且对于某个 $t > 0$ 有 $\| x \| \leq t$。（如果 $t = 0$，则 $x$ 必须为零，显然 $u ^ { T } x + v t \geq 0$。）应用对偶范数的定义，以及 $\| - x / t \| \leq 1$ 的事实，我们有

$$
u ^ {T} (- x / t) \leq \| u \| _ {*} \leq v,
$$

因此 $u ^ { T } x + v t \geq 0$。

接下来我们证明 (2.20) 中的左侧条件蕴含 (2.20) 中的右侧条件。假设 $\left\| u \right\| _ { * } > v$，即右侧条件不成立。那么根据对偶范数的定义，存在一个 $x$ 满足 $\| x \| \leq 1$ 且 $x ^ { T } u > v$。取 $t = 1$，我们有

$$
 (- x)^ {T} u + v <   0,
$$

这与 (2.20) 中的左侧条件矛盾（因为$(-x,1)$也在范数锥内，$\|x\|=\|-x\|$）。

对偶锥满足以下几个性质：

• $K ^ { * }$ 是闭的且凸的，对偶锥一定是凸锥。  
• $K _ { 1 } \subseteq K _ { 2 }$ 蕴含 $K _ { 2 } ^ { * } \subseteq K _ { 1 } ^ { * }$。  
• 如果 $K$ 有非空内部，则 $K ^ { * }$ 是尖的（尖用于描述锥的特性，定义：x属于锥，那么-x一定不属于锥，除非原点）。  
• 如果 $K$ 的闭包是尖的，则 $K ^ { * }$ 有非空内部（例如，一条射线的点的集合的对偶集就是一个半空间，半空间不是尖的）。  
• $K ^ { * * }$ 是 $K$ 的凸包的闭包。（因此如果 $K$ 是凸且闭的，则 $K ^ { * * } = K$。）tip：K本身必须是一个锥

![[数学书/凸优化/附件/8a97b468625ffbebe58f89ec5f1d88da.jpg]]

==2026.3.24==
（见习题 2.31。）这些性质表明，如果 $K$ 是一个正常锥，那么它的对偶 $K ^ { * }$ 也是正常锥，并且 $K ^ { * * } = K$。
tip:正常锥的定义——闭（close），凸（convex），尖（point），非空（solid）

## 2.6.2 对偶广义不等式

现在假设凸锥 $K$ 是正常的，因此它导出一个广义不等式 $\preceq _ { K }$。那么它的对偶锥 $K ^ { * }$ 也是正常的，因此也导出一个广义不等式。我们将广义不等式 $\preceq _ { K ^ { * } }$ 称为广义不等式 $\preceq _ { K }$ 的对偶。

关联广义不等式及其对偶的一些重要性质是：

• $x \preceq _ { K } y$ 当且仅当对于所有 $\lambda \succeq _ { K ^ { * } } 0$ 有 $\lambda ^ { T } x \le \lambda ^ { T } y$。  
证明：
$x \preceq _ { K } y$
$y-x\in K$
$\lambda \succeq _ { K ^ { * } } 0$
$\lambda\in K^*$
$\lambda^T(y-x)\geq 0$
$\lambda^Ty\geq \lambda^Tx$
反向证明同理

• $x \prec _ { K } y$ 当且仅当对于所有 $\lambda \succeq _ { K ^ { * } } 0$，$\lambda \neq 0$ 有 $\lambda ^ { T } x < \lambda ^ { T } y$。

由于 $K = K ^ { * * }$，与 $\preceq _ { K ^ { * } }$ 关联的对偶广义不等式是 $\preceq _ { K }$，所以如果交换广义不等式及其对偶，这些性质仍然成立。作为一个具体例子，我们有 $\lambda \preceq _ { K ^ { * } } \mu$ 当且仅当对于所有 $x \succeq _ { K } 0$ 有 $\lambda ^ { T } x \leq \mu ^ { T } x$。

**例 2.26 线性严格广义不等式的择一定理。** 假设 $K \subseteq \mathbf { R } ^ { m }$ 是一个正常锥。考虑严格广义不等式

$$
A x \prec_ {K} b, \tag {2.21}
$$

其中 $x \in \mathbf { R } ^ { n }$。

我们将为这个不等式推导一个择一定理。假设它是不可行的，即仿射集 $\{ b - A x \mid x \in \mathbf { R } ^ { n } \}$ 与开凸集 $\operatorname {int} K$ 不相交。那么存在一个分离超平面，即一个非零的 $\lambda \in \mathbf { R } ^ { m }$ 和 $\mu \in \mathbf { R }$，使得对于所有 $x$ 有 $\lambda ^ { T } ( b - A x ) \leq \mu$，并且对于所有 $y \in \mathbf {int} K$ 有 $\lambda ^ { \mathrm { { \scriptscriptstyle T } } } y \geq \mu$。第一个条件蕴含 $A ^ { T } \lambda = 0$ 和 $\lambda ^ { T } b \leq \mu$。第二个条件蕴含对于所有 $y \in K$ 有 $\lambda ^ { \prime } \boldsymbol { y } \geq \mu$，这推出 $\lambda \in K ^ { * }$ 且 $\mu \leq 0$ 时发生。

综合起来，我们发现如果 (2.21) 不可行，则存在 $\lambda$ 使得

$$
\lambda \neq 0, \quad \lambda \succeq_ {K ^ {*}} 0, \quad A ^ {T} \lambda = 0, \quad \lambda^ {T} b \leq 0. \tag {2.22}
$$

现在我们证明逆命题：如果 (2.22) 成立，则不等式系统 (2.21) 不可能是可行的。假设两个不等式系统都成立。那么我们有 $\lambda ^ { T } ( b - A x ) > 0$，因为 $\lambda \neq 0$，$\lambda \succeq _ { K ^ { * } } 0$，且 $b - A x \ \succ _ { K } \ 0$。但利用 $A ^ { \mathrm { T } } \lambda = 0$，我们发现 $\lambda ^ { T } ( b - A x ) = \lambda ^ { T } b \leq 0$，这是一个矛盾。

因此，不等式系统 (2.21) 和 (2.22) 是择一的：对于任何数据 $A$，$b$，它们中恰好有一个是可行的。（这推广了特殊情况 $K = { \bf R } _ { + } ^ { m }$ 下的择一关系 (2.17), (2.18)。）

## 2.6.3 通过对偶不等式刻画最小元和极小元

我们可以使用对偶广义不等式来刻画集合 $S \subseteq \mathbf { R } ^ { m }$（可能是非凸的）关于由正常锥 $K$ 导出的广义不等式的最小元和极小元。

### 最小元的对偶刻画

我们首先考虑最小元的刻画：$x$ 是 $S$ 关于广义不等式 $\preceq _ { K }$ 的最小元（任意$x\neq z \in S$，$z-x\in \operatorname{int}(K)$）当且仅当对于所有 $\lambda \succ _ { K ^ { * } } 0$，$x$ 是 $\lambda ^ { T } z$ 在 $z \in S$ 上的唯一最小元。从几何上看，这意味着对于任何 $\lambda \succ _ { K ^ { * } } 0$，超平面

$$
\left\{z \mid \lambda^ {T} (z - x) = 0 \right\}
$$

是在 $x$ 处严格支撑 $S$ 的超平面（$\lambda\in K^*$意味着$\lambda$一定是$K$的支撑超平面的法向量。）。（所谓严格支撑超平面，是指该超平面仅在点 $x$ 处与 $S$ 相交。）注意，集合 $S$ 的凸性不是必需的。如图 2.23 所示。

证明思路：$\lambda^T(z-x)> 0$
为了证明这个结果，假设 $x$ 是 $S$ 的最小元，即对于所有 $z \in S$ 有 $x \preceq _ { K } z$，并设 $\lambda \succ _ { K ^ { * } } 0$。令 $z \in S$，$z \neq x$。由于 $x$ 是 $S$ 的最小元，我们有 $z - x \succeq _ { K } 0$。由 $\lambda \succ _ { K ^ { * } } 0$ 和 $z - x \succeq _ { K } 0$，$z - x \neq 0$，我们得出结论 $\lambda ^ { T } ( z - x ) > 0$。由于 $z$ 是 $S$ 中任意不等于 $x$ 的元素，这表明 $x$ 是 $\lambda ^ { T } z$ 在 $z \in S$ 上的唯一最小化元。
反之，假设对于所有 $\lambda \succ _ { K ^ { * } } 0$，$x$ 是 $\lambda ^ { T } z$ 在 $z \in S$ 上的唯一最小化元，但 $x$ 不是 $S$ 的最小元。那么存在 $z \in S$ 满足 $z \not \subseteq \kappa \ x$。由于 $z - x \not \subseteq \kappa \ : 0$，存在 $\tilde { \lambda } \succeq _ { K ^ { * } } 0$ 使得 $\bar { \lambda } ^ { T } ( z - x ) < 0$。因此，对于 $\lambda \succ _ { K ^ { * } } 0$ 且在 $\lambda$ 的邻域内，有 $\lambda ^ { T } ( z - x ) < 0$。这与 $x$ 是 $\lambda ^ { T } z$ 在 $S$ 上的唯一最小化元的假设矛盾。

![[数学书/凸优化/images/5a002484c37d8d9837830d25dfd1fdb95b2c587adba6522b687840639066320e.jpg]]  
**图 2.23 最小元的对偶刻画。** 点 $x$ 是集合 $S$ 关于 $\mathbf { R } _ { + } ^ { 2 }$ 的最小元。这等价于：对于每个 $\lambda \succ 0$，超平面 $\{ z \mid \lambda ^ { T } ( z - x ) = 0 \}$ 在 $x$ 处严格支撑 $S$，即，将 $S$ 置于一侧，并且仅在 $x$ 处接触它。

### 极小元的对偶刻画

我们现在转向极小元的类似刻画。这里必要条件和充分条件之间存在差距。如果存在 $\lambda \succ _ { K ^ { * } } 0$ 且 $x$ 在 $z \in S$ 上最小化 $\lambda ^ { T } z$，那么 $x$ 是极小元。如图 2.24 所示。

为了证明这一点，假设 $\lambda \succ _ { K ^ { * } } 0$，且 $x$ 在 $S$ 上最小化 $\lambda ^ { T } z$，但 $x$ 不是极小元，即存在 $z \in S$，$z \neq x$，且 $z \preceq _ { K } x$。那么 $\lambda ^ { T } ( x - z ) > 0$，这与我们假设 $x$ 是 $\lambda ^ { T } z$ 在 $S$ 上的最小化元矛盾。

逆命题在一般情况下不成立：一个点 $x$ 可以是 $S$ 中的极小元，但不是任何 $\lambda$ 下 $\lambda ^ { T } z$ 在 $z \in S$ 上的最小化元，如图 2.25 所示。该图表明凸性在逆命题中起着重要作用，这是正确的。如果集合 $S$ 是凸的，我们可以说，对于任何极小元 $x$，存在一个非零的 $\lambda \succeq _ { K ^ { * } } 0$，使得 $x$ 在 $z \in S$ 上最小化 $\lambda ^ { T } z$。

为了证明这一点，**假设 $x$ 是极小元，这意味着 $( ( x - K ) \setminus \{ x \} ) \cap S = \emptyset$。** 将分离超平面定理应用于凸集 $( x - K ) \setminus \{ x \}$ 和 $S$，我们得出结论：存在 $\lambda \neq 0$ 和 $\mu$，使得对于所有 $y \in K$ 有 $\lambda ^ { \prime } ( x - y ) \leq \mu$，并且对于所有 $z \in S$ 有 $\lambda ^ { T } z \ge \mu$。从第一个不等式我们得出结论 $\lambda \succeq _ { K ^ { * } } 0$。由于 $x \in S$ 且 $x \in x - K$，我们有 $\lambda ^ { T } x = \mu$，所以第二个不等式蕴含 $\mu$ 是 $\lambda ^ { T } z$ 在 $S$ 上的最小值。因此，$x$ 是 $\lambda ^ { T } z$ 在 $S$ 上的最小化元，其中 $\lambda \neq 0$，$\lambda \succeq _ { K ^ { * } } 0$。

这个逆定理不能加强到 $\lambda \succ _ { K ^ { * } } 0$。例子表明，一个点 $x$ 可以是凸集 $S$ 的极小点，但不是任何 $\lambda \succ _ { K ^ { * } } 0$ 下 $\lambda ^ { T } z$ 在 $S$ 上的最小化元。（见图 2.26，左。）同样，对于任何 $\lambda \succeq _ { K ^ { * } } 0$，$\lambda ^ { T } z$ 在 $z \in S$ 上的最小化元也不一定是极小元（见图 2.26，右。）

![[数学书/凸优化/images/03b08d9468543ee545706cb30f2df0d8d90d4d90a7f3f8e8302c49416d6dc3fb.jpg]]  
**图 2.24** 一个集合 $S \subseteq \mathbf { R } ^ { 2 }$。它关于 $\mathbf { R } _ { + } ^ { 2 }$ 的极小点集显示为其（左下）边界的较暗部分。$\lambda _ { 1 } ^ { T } z$ 在 $S$ 上的最小化元是 $x _ { 1 }$，并且由于 $\lambda _ { 1 } \succ 0$，它是极小元。$\lambda _ { 2 } ^ { T } z$ 在 $S$ 上的最小化元是 $x _ { 2 }$，它是 $S$ 的另一个极小点，因为 $\lambda _ { 2 } \succ 0$。

![[数学书/凸优化/images/a3c95c0f3f4946fdfa421cc8469483762774b6dc24d72d6c4a4826c84ab89e34.jpg]]  
**图 2.25** 点 $x$ 是 $S \subseteq \mathbf { R } ^ { 2 }$ 关于 $\mathbf { R } _ { + } ^ { 2 }$ 的极小元。然而，不存在 $\lambda$ 使得 $x$ 在 $z \in S$ 上最小化 $\lambda ^ { T } z$。

![[数学书/凸优化/images/60f9a967e9d3c7a705085944855ea067f308bdf59876c6d799a3a2130b4de594.jpg]]

![[数学书/凸优化/images/02838d8a909a6b61f863baee540a17fcff8aa825f27fbf8e9efa73db95a89214.jpg]]  
**图 2.26** 左。点 $x _ { 1 } \in S _ { 1 }$ 是极小元，但不是任何 $\lambda \succ 0$ 下 $\lambda ^ { T } z$ 在 $S _ { 1 }$ 上的最小化元。（然而，对于 $\lambda = ( 1 , 0 )$，它确实在 $z \in S _ { 1 }$ 上最小化了 $\lambda ^ { T } z$。）右。点 $x _ { 2 } \in S _ { 2 }$ 不是极小元，但它确实对于 $\lambda = ( 0 , 1 ) \succeq 0$ 在 $z \in S _ { 2 }$ 上最小化了 $\lambda ^ { T } z$。

**例 2.27 帕累托最优生产前沿。** 我们考虑一种需要 $n$ 种资源（如劳动力、电力、天然气、水）来制造的产品。该产品可以通过多种方式制造或生产。对于每种生产方法，我们关联一个资源向量 $x \in \mathbf { R } ^ { n }$，其中 $x _ { i }$ 表示生产该方法为制造产品所消耗的资源 $_ i$ 的数量。我们假设 $x _ { i } \geq 0$（即资源被生产方法消耗）并且资源是有价值的（因此使用更少的任何资源是更优的）。

生产集 $P \subseteq \mathbf { R } ^ { n }$ 定义为对应于某种生产方法的所有资源向量 $x$ 的集合。

资源向量是 $P$ 的极小元（关于分量不等式）的生产方法被称为帕累托最优或有效的。$P$ 的极小元集合被称为有效生产前沿。

我们可以给出帕累托最优性的一个简单解释。我们说一种资源向量为 $x$ 的生产方法优于另一种资源向量为 $y$ 的生产方法，如果对于所有 $_ i$ 有 $x _ { i } \ \leq y _ { i }$，并且对于某个 $_ i$ 有 $x _ { i } ~ < ~ y _ { i }$。换句话说，如果一种生产方法使用的每种资源都不多于另一种方法，并且对于至少一种资源，实际上使用得更少，那么它就优于另一种方法。这对应于 $x \preceq y$，$x \neq y$。那么我们可以说：如果不存在更好的生产方法，那么一种生产方法是帕累托最优或有效的。

我们可以通过最小化

$$
\lambda^ {T} x = \lambda_ {1} x _ {1} + \dots + \lambda_ {n} x _ {n}
$$

在生产向量集合 $P$ 上，使用任何满足 $\lambda \succ_{R^n_{+}} 0$ 的 $\lambda$，来找到帕累托最优生产方法（即极小资源向量）。

这里向量 $\lambda$ 有一个简单的解释：$\lambda _ { i }$ 是资源 i 的价格。通过最小化 $P$ 上的 $\lambda ^ { T } x$，我们正在寻找总体上最便宜的生产方法（对于资源价格 $\lambda _ { i }$）。只要价格是正的，所得到的生产方法保证是有效的。

这些思想如图 2.27 所示。

![[数学书/凸优化/images/f2ec7cc1447ccbde7bbd88d3c46f6cd6227ed0dde5387d19841ec4ad568d0856.jpg]]  
**图 2.27** 生产一种需要劳动力和燃料的产品，其生产集 $P$ 显示为阴影区域。两条深色曲线显示了有效生产前沿。点 $x _ { 1 }$、$x _ { 2 }$ 和 $x _ { 3 }$ 是有效的。点 $x _ { 4 }$ 和 $x _ { 5 }$ 不是（特别是因为 $x _ { 2 }$ 对应一种使用燃料不多且劳动力更少的生产方法）。点 $x _ { 1 }$ 也是价格向量 $\lambda$（为正）下的最小成本生产方法。**点 $x _ { 2 }$ 是有效的，但不能通过最小化任何价格向量 $\lambda \succeq 0$ 下的总成本 $\lambda ^ { T } x$ 来找到。**（因为$P$是凹的，必要性不成立）