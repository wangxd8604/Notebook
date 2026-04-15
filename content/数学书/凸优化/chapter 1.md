---
{"publish":true,"title":"chapter 1","description":"一句话概述内容，方便 SEO 和分享预览","created":"2026-04-15","modified":"2026-04-15T20:33:32.999+08:00","cssclasses":""}
---



# Chapter 1

# Introduction

In this introduction we give an overview of mathematical optimization, focusing on the special role of convex optimization. The concepts introduced informally here will be covered in later chapters, with more care and technical detail.

# 1.1 Mathematical optimization

A mathematical optimization problem, or just optimization problem, has the form

$$
\begin{array}{l l} \text {m i n i m i z e} & f _ {0} (x) \\ \text {s u b j e c t t o} & f _ {i} (x) \leqslant b, \quad i = 1, \dots , m. \end{array} \tag {1.1}
$$

Here the vector ${ \boldsymbol x } = ( x _ { 1 } , \dots , x _ { n } )$ is the optimization variable of the problem, the function $f _ { 0 } : \mathbf { R } ^ { n }  \mathbf { R }$ is the objective function, the functions $f _ { i } : \mathbf { R } ^ { n }  \mathbf { R }$ , $i = 1 , \ldots , m$ , are the (inequality) constraint functions, and the constants $b _ { 1 } , \ldots , b _ { m }$ are the limits, or bounds, for the constraints. A vector $x ^ { \star }$ is called optimal, or a solution of the problem (1.1), if it has the smallest objective value among all vectors that satisfy the constraints: for any $z$ with $f _ { 1 } ( z ) \leq b _ { 1 } , \ldots , f _ { m } ( z ) \leq b _ { m }$ , we have $f _ { 0 } ( z ) \geq f _ { 0 } ( x ^ { \star } )$ .

We generally consider families or classes of optimization problems, characterized by particular forms of the objective and constraint functions. As an important example, the optimization problem (1.1) is called a linear program if the objective and constraint functions $f _ { 0 } , \ldots , f _ { m }$ are linear, i.e., satisfy

$$
f _ {i} (\alpha x + \beta y) = \alpha f _ {i} (x) + \beta f _ {i} (y) \tag {1.2}
$$

for all $x , \ y \in \mathbf { R } ^ { \pi }$ and all $\alpha , ~ \beta \in \mathbf { R }$ . If the optimization problem is not linear, it is called a nonlinear program.

This book is about a class of optimization problems called convex optimization problems. A convex optimization problem is one in which the objective and constraint functions are convex, which means they satisfy the inequality

$$
f _ {i} (\alpha x + \beta y) \leq \alpha f _ {i} (x) + \beta f _ {i} (y) \tag {1.3}
$$

for all $x , \ y \in \mathbf { R } ^ { \pi }$ and all $\alpha , ~ \beta \in \mathbf { R }$ with $\alpha + \beta = 1$ , $\alpha \geq 0$ , $\beta \geq 0$ . Comparing (1.3) and (1.2), we see that convexity is more general than linearity: inequality replaces the more restrictive equality, and the inequality must hold only for certain values of $\alpha$ and $\beta$ . Since any linear program is therefore a convex optimization problem, we can consider convex optimization to be a generalization of linear programming.

# 1.1.1 Applications

The optimization problem (1.1) is an abstraction of the problem of making the best possible choice of a vector in $\mathbf { R } ^ { n }$ from a set of candidate choices. The variable $x$ represents the choice made; the constraints $f _ { i } ( x ) \leq b _ { i }$ represent firm requirements or specifications that limit the possible choices, and the objective value $f _ { 0 } ( x )$ represents the cost of choosing $x$ . (We can also think of $- f _ { 0 } ( x )$ as representing the value, or utility, of choosing $x$ .) A solution of the optimization problem (1.1) corresponds to a choice that has minimum cost (or maximum utility), among all choices that meet the firm requirements.

In portfolio optimization, for example, we seek the best way to invest some capital in a set of $n$ assets. The variable $x _ { i }$ represents the investment in the $i$ th asset, so the vector $\boldsymbol { x } \in \mathbf { R } ^ { n }$ describes the overall portfolio allocation across the set of assets. The constraints might represent a limit on the budget (i.e., a limit on the total amount to be invested), the requirement that investments are nonnegative (assuming short positions are not allowed), and a minimum acceptable value of expected return for the whole portfolio. The objective or cost function might be a measure of the overall risk or variance of the portfolio return. In this case, the optimization problem (1.1) corresponds to choosing a portfolio allocation that minimizes risk, among all possible allocations that meet the firm requirements.

Another example is device sizing in electronic design, which is the task of choosing the width and length of each device in an electronic circuit. Here the variables represent the widths and lengths of the devices. The constraints represent a variety of engineering requirements, such as limits on the device sizes imposed by the manufacturing process, timing requirements that ensure that the circuit can operate reliably at a specified speed, and a limit on the total area of the circuit. A common objective in a device sizing problem is the total power consumed by the circuit. The optimization problem (1.1) is to find the device sizes that satisfy the design requirements (on manufacturability, timing, and area) and are most power efficient.

In data fitting, the task is to find a model, from a family of potential models, that best fits some observed data and prior information. Here the variables are the parameters in the model, and the constraints can represent prior information or required limits on the parameters (such as nonnegativity). The objective function might be a measure of misfit or prediction error between the observed data and the values predicted by the model, or a statistical measure of the unlikeliness or implausibility of the parameter values. The optimization problem (1.1) is to find the model parameter values that are consistent with the prior information, and give the smallest misfit or prediction error with the observed data (or, in a statistical

framework, are most likely).

An amazing variety of practical problems involving decision making (or system design, analysis, and operation) can be cast in the form of a mathematical optimization problem, or some variation such as a multicriterion optimization problem. Indeed, mathematical optimization has become an important tool in many areas. It is widely used in engineering, in electronic design automation, automatic control systems, and optimal design problems arising in civil, chemical, mechanical, and aerospace engineering. Optimization is used for problems arising in network design and operation, finance, supply chain management, scheduling, and many other areas. The list of applications is still steadily expanding.

For most of these applications, mathematical optimization is used as an aid to a human decision maker, system designer, or system operator, who supervises the process, checks the results, and modifies the problem (or the solution approach) when necessary. This human decision maker also carries out any actions suggested by the optimization problem, e.g., buying or selling assets to achieve the optimal portfolio.

A relatively recent phenomenon opens the possibility of many other applications for mathematical optimization. With the proliferation of computers embedded in products, we have seen a rapid growth in embedded optimization. In these embedded applications, optimization is used to automatically make real-time choices, and even carry out the associated actions, with no (or little) human intervention or oversight. In some application areas, this blending of traditional automatic control systems and embedded optimization is well under way; in others, it is just starting. Embedded real-time optimization raises some new challenges: in particular, it requires solution methods that are extremely reliable, and solve problems in a predictable amount of time (and memory).

# 1.1.2 Solving optimization problems

A solution method for a class of optimization problems is an algorithm that computes a solution of the problem (to some given accuracy), given a particular problem from the class, i.e., an instance of the problem. Since the late 1940s, a large effort has gone into developing algorithms for solving various classes of optimization problems, analyzing their properties, and developing good software implementations. The effectiveness of these algorithms, i.e., our ability to solve the optimization problem (1.1), varies considerably, and depends on factors such as the particular forms of the objective and constraint functions, how many variables and constraints there are, and special structure, such as sparsity. (A problem is sparse if each constraint function depends on only a small number of the variables).

Even when the objective and constraint functions are smooth (for example, polynomials) the general optimization problem (1.1) is surprisingly difficult to solve. Approaches to the general problem therefore involve some kind of compromise, such as very long computation time, or the possibility of not finding the solution. Some of these methods are discussed in §1.4.

There are, however, some important exceptions to the general rule that most optimization problems are difficult to solve. For a few problem classes we have

effective algorithms that can reliably solve even large problems, with hundreds or thousands of variables and constraints. Two important and well known examples, described in §1.2 below (and in detail in chapter 4), are least-squares problems and linear programs. It is less well known that convex optimization is another exception to the rule: Like least-squares or linear programming, there are very effective algorithms that can reliably and efficiently solve even large convex problems.

# 1.2 Least-squares and linear programming

In this section we describe two very widely known and used special subclasses of convex optimization: least-squares and linear programming. (A complete technical treatment of these problems will be given in chapter 4.)

# 1.2.1 Least-squares problems

A least-squares problem is an optimization problem with no constraints (i.e., $m =$ 0) and an objective which is a sum of squares of terms of the form $a _ { i } ^ { \scriptscriptstyle T } x - b _ { i }$ :

$$
\text {m i n i m i z e} \quad f _ {0} (x) = \| A x - b \| _ {2} ^ {2} = \sum_ {i = 1} ^ {k} \left(a _ {i} ^ {T} x - b _ {i}\right) ^ {2}. \tag {1.4}
$$

Here $A \in \mathbf { R } ^ { k \times n }$ (with $k \geq n$ ), $a _ { i } ^ { \scriptscriptstyle T }$ are the rows of $A$ , and the vector $x \in \mathbf { R } ^ { \pi }$ is the optimization variable.

# Solving least-squares problems

The solution of a least-squares problem (1.4) can be reduced to solving a set of linear equations,

$$
(A ^ {T} A) x = A ^ {T} b,
$$

so we have the analytical solution $x = ( A ^ { T } A ) ^ { - 1 } A ^ { T } b$ . For least-squares problems we have good algorithms (and software implementations) for solving the problem to high accuracy, with very high reliability. The least-squares problem can be solved in a time approximately proportional to $n ^ { 2 } k$ , with a known constant. A current desktop computer can solve a least-squares problem with hundreds of variables, and thousands of terms, in a few seconds; more powerful computers, of course, can solve larger problems, or the same size problems, faster. (Moreover, these solution times will decrease exponentially in the future, according to Moore’s law.) Algorithms and software for solving least-squares problems are reliable enough for embedded optimization.

In many cases we can solve even larger least-squares problems, by exploiting some special structure in the coefficient matrix $A$ . Suppose, for example, that the matrix $A$ is sparse, which means that it has far fewer than $k n$ nonzero entries. By exploiting sparsity, we can usually solve the least-squares problem much faster than order $n ^ { 2 } k$ . A current desktop computer can solve a sparse least-squares problem

with tens of thousands of variables, and hundreds of thousands of terms, in around a minute (although this depends on the particular sparsity pattern).

For extremely large problems (say, with millions of variables), or for problems with exacting real-time computing requirements, solving a least-squares problem can be a challenge. But in the vast majority of cases, we can say that existing methods are very effective, and extremely reliable. Indeed, we can say that solving least-squares problems (that are not on the boundary of what is currently achievable) is a (mature) technology, that can be reliably used by many people who do not know, and do not need to know, the details.

# Using least-squares

The least-squares problem is the basis for regression analysis, optimal control, and many parameter estimation and data fitting methods. It has a number of statistical interpretations, e.g., as maximum likelihood estimation of a vector $x$ , given linear measurements corrupted by Gaussian measurement errors.

Recognizing an optimization problem as a least-squares problem is straightforward; we only need to verify that the objective is a quadratic function (and then test whether the associated quadratic form is positive semidefinite). While the basic least-squares problem has a simple fixed form, several standard techniques are used to increase its flexibility in applications.

In weighted least-squares, the weighted least-squares cost

$$
\sum_ {i = 1} ^ {k} w _ {i} (a _ {i} ^ {T} x - b _ {i}) ^ {2},
$$

where $w _ { 1 } , \ldots , w _ { k }$ are positive, is minimized. (This problem is readily cast and solved as a standard least-squares problem.) Here the weights $w _ { i }$ are chosen to reflect differing levels of concern about the sizes of the terms $a _ { i } ^ { \scriptscriptstyle T } x - b _ { i }$ , or simply to influence the solution. In a statistical setting, weighted least-squares arises in estimation of a vector $x$ , given linear measurements corrupted by errors with unequal variances.

Another technique in least-squares is regularization, in which extra terms are added to the cost function. In the simplest case, a positive multiple of the sum of squares of the variables is added to the cost function:

$$
\sum_ {i = 1} ^ {k} (a _ {i} ^ {T} x - b _ {i}) ^ {2} + \rho \sum_ {i = 1} ^ {n} x _ {i} ^ {2},
$$

where $\rho > 0$ . (This problem too can be formulated as a standard least-squares problem.) The extra terms penalize large values of $x$ , and result in a sensible solution in cases when minimizing the first sum only does not. The parameter $\rho$ i s chosen bfunction $\scriptstyle \sum _ { i = 1 } ^ { k } ( a _ { i } ^ { T } x - b _ { i } ) ^ { 2 }$ the right trade-off bsmall, while keeping $\textstyle \sum _ { i = 1 } ^ { n } x _ { i } ^ { 2 }$ aking the original objective not too big. Regularization comes up in statistical estimation when the vector $x$ to be estimated is given a prior distribution.

Weighted least-squares and regularization are covered in chapter 6; their statistical interpretations are given in chapter 7.

# 1.2.2 Linear programming

Another important class of optimization problems is linear programming, in which the objective and all constraint functions are linear:

$$
\begin{array}{l l} \text {m i n i m i z e} & c ^ {T} x \\ \text {s u b j e c t t o} & a _ {i} ^ {T} x <   b _ {i}, \quad i = 1, \end{array} \tag {1.5}
$$

Here the vectors $c , a _ { 1 } , \ldots , a _ { m } \in \mathbf { R } ^ { n }$ and scalars $b _ { 1 } , \dotsc , - b _ { m } \in \mathbf { R }$ are problem parameters that specify the objective and constraint functions.

# Solving linear programs

There is no simple analytical formula for the solution of a linear program (as there is for a least-squares problem), but there are a variety of very effective methods for solving them, including Dantzig’s simplex method, and the more recent interiorpoint methods described later in this book. While we cannot give the exact number of arithmetic operations required to solve a linear program (as we can for leastsquares), we can establish rigorous bounds on the number of operations required to solve a linear program, to a given accuracy, using an interior-point method. The complexity in practice is order $n ^ { 2 } m$ (assuming $m \geq n$ ) but with a constant that is less well characterized than for least-squares. These algorithms are quite reliable, although perhaps not quite as reliable as methods for least-squares. We can easily solve problems with hundreds of variables and thousands of constraints on a small desktop computer, in a matter of seconds. If the problem is sparse, or has some other exploitable structure, we can often solve problems with tens or hundreds of thousands of variables and constraints.

As with least-squares problems, it is still a challenge to solve extremely large linear programs, or to solve linear programs with exacting real-time computing requirements. But, like least-squares, we can say that solving (most) linear programs is a mature technology. Linear programming solvers can be (and are) embedded in many tools and applications.

# Using linear programming

Some applications lead directly to linear programs in the form (1.5), or one of several other standard forms. In many other cases the original optimization problem does not have a standard linear program form, but can be transformed to an equivalent linear program (and then, of course, solved) using techniques covered in detail in chapter 4.

As a simple example, consider the Chebyshev approximation problem:

$$
\text {m i n i m i z e} \quad \max  _ {i = 1, \dots , k} \left| a _ {i} ^ {T} x - b _ {i} \right|. \tag {1.6}
$$

Here $\boldsymbol { x } \in \mathbf { R } ^ { n }$ is the variable, and $a _ { 1 } , \ldots , a _ { k } \in \mathbf { R } ^ { n }$ , $b _ { 1 } , \dotsc , b _ { k } \in \mathbf { R }$ are parameters that specify the problem instance. Note the resemblance to the least-squares problem (1.4). For both problems, the objective is a measure of the size of the terms $a _ { i } ^ { 2 } x - b _ { i }$ . In least-squares, we use the sum of squares of the terms as objective, whereas in Chebyshev approximation, we use the maximum of the absolute values.

One other important distinction is that the objective function in the Chebyshev approximation problem (1.6) is not differentiable; the objective in the least-squares problem (1.4) is quadratic, and therefore differentiable.

The Chebyshev approximation problem (1.6) can be solved by solving the linear program

$$
\begin{array}{l} \begin{array}{l l} \text {m i n i m i z e} & t \\ \text {s u b j e c t t o} & a _ {i} ^ {T} x - t \leq b _ {i}, \quad i = 1, \dots , k \end{array} \tag {1.7} \\ - a _ {i} ^ {T} x - t \leq - b _ {i}, \quad i = 1, \dots , k, \\ \end{array}
$$

with variables $x \in \mathbf { R } ^ { n }$ and $t \in \textbf { R }$ . (The details will be given in chapter 6.) Since linear programs are readily solved, the Chebyshev approximation problem is therefore readily solved.

Anyone with a working knowledge of linear programming would recognize the Chebyshev approximation problem (1.6) as one that can be reduced to a linear program. For those without this background, though, it might not be obvious that the Chebyshev approximation problem (1.6), with its nondifferentiable objective, can be formulated and solved as a linear program.

While recognizing problems that can be reduced to linear programs is more involved than recognizing a least-squares problem, it is a skill that is readily acquired, since only a few standard tricks are used. The task can even be partially automated; some software systems for specifying and solving optimization problems can automatically recognize (some) problems that can be reformulated as linear programs.

# 1.3 Convex optimization

A convex optimization problem is one of the form

$$
\begin{array}{l l} \text {m i n i m i z e} & f _ {0} (x) \\ \text {s u b j e c t t o} & f (x) <   b, \quad i = 1, \dots , m \end{array} \tag {1.8}
$$

$$
\text {s u b j e c t} f _ {i} (x) \leq b _ {i}, \quad i = 1, \dots , m,
$$

where the functions $f _ { 0 } , \ldots , f _ { m } : \mathbf { R } ^ { n }  \mathbf { R }$ are convex, i.e., satisfy

$$
f _ {i} (\alpha x + \beta y) \leq \alpha f _ {i} (x) + \beta f _ {i} (y)
$$

for all $x , y \in \mathbf { R } ^ { \pi }$ and all $\alpha , ~ \beta \in \mathbf { R }$ with $\alpha + \beta = 1$ , $\alpha \geq 0$ , $\beta \geq 0$ . The least-squares problem (1.4) and linear programming problem (1.5) are both special cases of the general convex optimization problem (1.8).

# 1.3.1 Solving convex optimization problems

There is in general no analytical formula for the solution of convex optimization problems, but (as with linear programming problems) there are very effective methods for solving them. Interior-point methods work very well in practice, and in some cases can be proved to solve the problem to a specified accuracy with a number of

operations that does not exceed a polynomial of the problem dimensions. (This is covered in chapter 11.)

We will see that interior-point methods can solve the problem (1.8) in a number of steps or iterations that is almost always in the range between 10 and 100. Ignoring any structure in the problem (such as sparsity), each step requires on the order of

$$
\max  \{n ^ {3}, n ^ {2} m, F \}
$$

operations, where $F ^ { \dagger }$ is the cost of evaluating the first and second derivatives of the objective and constraint functions $f _ { 0 } , \ldots , f _ { m }$ .

Like methods for solving linear programs, these interior-point methods are quite reliable. We can easily solve problems with hundreds of variables and thousands of constraints on a current desktop computer, in at most a few tens of seconds. By exploiting problem structure (such as sparsity), we can solve far larger problems, with many thousands of variables and constraints.

We cannot yet claim that solving general convex optimization problems is a mature technology, like solving least-squares or linear programming problems. Research on interior-point methods for general nonlinear convex optimization is still a very active research area, and no consensus has emerged yet as to what the best method or methods are. But it is reasonable to expect that solving general convex optimization problems will become a technology within a few years. And for some subclasses of convex optimization problems, for example second-order cone programming or geometric programming (studied in detail in chapter 4), it is fair to say that interior-point methods are approaching a technology.

# 1.3.2 Using convex optimization

Using convex optimization is, at least conceptually, very much like using leastsquares or linear programming. If we can formulate a problem as a convex optimization problem, then we can solve it efficiently, just as we can solve a least-squares problem efficiently. With only a bit of exaggeration, we can say that, if you formulate a practical problem as a convex optimization problem, then you have solved the original problem.

There are also some important differences. Recognizing a least-squares problem is straightforward, but recognizing a convex function can be difficult. In addition, there are many more tricks for transforming convex problems than for transforming linear programs. Recognizing convex optimization problems, or those that can be transformed to convex optimization problems, can therefore be challenging. The main goal of this book is to give the reader the background needed to do this. Once the skill of recognizing or formulating convex optimization problems is developed, you will find that surprisingly many problems can be solved via convex optimization.

The challenge, and art, in using convex optimization is in recognizing and formulating the problem. Once this formulation is done, solving the problem is, like least-squares or linear programming, (almost) technology.

# 1.4 Nonlinear optimization

Nonlinear optimization (or nonlinear programming) is the term used to describe an optimization problem when the objective or constraint functions are not linear, but not known to be convex. Sadly, there are no effective methods for solving the general nonlinear programming problem (1.1). Even simple looking problems with as few as ten variables can be extremely challenging, while problems with a few hundreds of variables can be intractable. Methods for the general nonlinear programming problem therefore take several different approaches, each of which involves some compromise.

# 1.4.1 Local optimization

In local optimization, the compromise is to give up seeking the optimal $x$ , which minimizes the objective over all feasible points. Instead we seek a point that is only locally optimal, which means that it minimizes the objective function among feasible points that are near it, but is not guaranteed to have a lower objective value than all other feasible points. A large fraction of the research on general nonlinear programming has focused on methods for local optimization, which as a consequence are well developed.

Local optimization methods can be fast, can handle large-scale problems, and are widely applicable, since they only require differentiability of the objective and constraint functions. As a result, local optimization methods are widely used in applications where there is value in finding a good point, if not the very best. In an engineering design application, for example, local optimization can be used to improve the performance of a design originally obtained by manual, or other, design methods.

There are several disadvantages of local optimization methods, beyond (possibly) not finding the true, globally optimal solution. The methods require an initial guess for the optimization variable. This initial guess or starting point is critical, and can greatly affect the objective value of the local solution obtained. Little information is provided about how far from (globally) optimal the local solution is. Local optimization methods are often sensitive to algorithm parameter values, which may need to be adjusted for a particular problem, or family of problems.

Using a local optimization method is trickier than solving a least-squares problem, linear program, or convex optimization problem. It involves experimenting with the choice of algorithm, adjusting algorithm parameters, and finding a good enough initial guess (when one instance is to be solved) or a method for producing a good enough initial guess (when a family of problems is to be solved). Roughly speaking, local optimization methods are more art than technology. Local optimization is a well developed art, and often very effective, but it is nevertheless an art. In contrast, there is little art involved in solving a least-squares problem or a linear program (except, of course, those on the boundary of what is currently possible).

An interesting comparison can be made between local optimization methods for nonlinear programming, and convex optimization. Since differentiability of the ob-

jective and constraint functions is the only requirement for most local optimization methods, formulating a practical problem as a nonlinear optimization problem is relatively straightforward. The art in local optimization is in solving the problem (in the weakened sense of finding a locally optimal point), once it is formulated. In convex optimization these are reversed: The art and challenge is in problem formulation; once a problem is formulated as a convex optimization problem, it is relatively straightforward to solve it.

# 1.4.2 Global optimization

In global optimization, the true global solution of the optimization problem (1.1) is found; the compromise is efficiency. The worst-case complexity of global optimization methods grows exponentially with the problem sizes $n$ and $m$ ; the hope is that in practice, for the particular problem instances encountered, the method is far faster. While this favorable situation does occur, it is not typical. Even small problems, with a few tens of variables, can take a very long time (e.g., hours or days) to solve.

Global optimization is used for problems with a small number of variables, where computing time is not critical, and the value of finding the true global solution is very high. One example from engineering design is worst-case analysis or verification of a high value or safety-critical system. Here the variables represent uncertain parameters, that can vary during manufacturing, or with the environment or operating condition. The objective function is a utility function, i.e., one for which smaller values are worse than larger values, and the constraints represent prior knowledge about the possible parameter values. The optimization problem (1.1) is the problem of finding the worst-case values of the parameters. If the worst-case value is acceptable, we can certify the system as safe or reliable (with respect to the parameter variations).

A local optimization method can rapidly find a set of parameter values that is bad, but not guaranteed to be the absolute worst possible. If a local optimization method finds parameter values that yield unacceptable performance, it has succeeded in determining that the system is not reliable. But a local optimization method cannot certify the system as reliable; it can only fail to find bad parameter values. A global optimization method, in contrast, will find the absolute worst values of the parameters, and if the associated performance is acceptable, can certify the system as safe. The cost is computation time, which can be very large, even for a relatively small number of parameters. But it may be worth it in cases where the value of certifying the performance is high, or the cost of being wrong about the reliability or safety is high.

# 1.4.3 Role of convex optimization in nonconvex problems

In this book we focus primarily on convex optimization problems, and applications that can be reduced to convex optimization problems. But convex optimization also plays an important role in problems that are not convex.

# Initialization for local optimization

One obvious use is to combine convex optimization with a local optimization method. Starting with a nonconvex problem, we first find an approximate, but convex, formulation of the problem. By solving this approximate problem, which can be done easily and without an initial guess, we obtain the exact solution to the approximate convex problem. This point is then used as the starting point for a local optimization method, applied to the original nonconvex problem.

# Convex heuristics for nonconvex optimization

Convex optimization is the basis for several heuristics for solving nonconvex problems. One interesting example we will see is the problem of finding a sparse vector $x$ (i.e., one with few nonzero entries) that satisfies some constraints. While this is a difficult combinatorial problem, there are some simple heuristics, based on convex optimization, that often find fairly sparse solutions. (These are described in chapter 6.)

Another broad example is given by randomized algorithms, in which an approximate solution to a nonconvex problem is found by drawing some number of candidates from a probability distribution, and taking the best one found as the approximate solution. Now suppose the family of distributions from which we will draw the candidates is parametrized, e.g., by its mean and covariance. We can then pose the question, which of these distributions gives us the smallest expected value of the objective? It turns out that this problem is sometimes a convex problem, and therefore efficiently solved. (See, e.g., exercise 11.23.)

# Bounds for global optimization

Many methods for global optimization require a cheaply computable lower bound on the optimal value of the nonconvex problem. Two standard methods for doing this are based on convex optimization. In relaxation, each nonconvex constraint is replaced with a looser, but convex, constraint. In Lagrangian relaxation, the Lagrangian dual problem (described in chapter 5) is solved. This problem is convex, and provides a lower bound on the optimal value of the nonconvex problem.

# 1.5 Outline

The book is divided into three main parts, titled Theory, Applications, and Algorithms.

# 1.5.1 Part I: Theory

In part I, Theory, we cover basic definitions, concepts, and results from convex analysis and convex optimization. We make no attempt to be encyclopedic, and skew our selection of topics toward those that we think are useful in recognizing

and formulating convex optimization problems. This is classical material, almost all of which can be found in other texts on convex analysis and optimization. We make no attempt to give the most general form of the results; for that the reader can refer to any of the standard texts on convex analysis.

Chapters 2 and 3 cover convex sets and convex functions, respectively. We give some common examples of convex sets and functions, as well as a number of convex calculus rules, i.e., operations on sets and functions that preserve convexity. Combining the basic examples with the convex calculus rules allows us to form (or perhaps more importantly, recognize) some fairly complicated convex sets and functions.

In chapter 4, Convex optimization problems, we give a careful treatment of optimization problems, and describe a number of transformations that can be used to reformulate problems. We also introduce some common subclasses of convex optimization, such as linear programming and geometric programming, and the more recently developed second-order cone programming and semidefinite programming.

Chapter 5 covers Lagrangian duality, which plays a central role in convex optimization. Here we give the classical Karush-Kuhn-Tucker conditions for optimality, and a local and global sensitivity analysis for convex optimization problems.

# 1.5.2 Part II: Applications

In part II, Applications, we describe a variety of applications of convex optimization, in areas like probability and statistics, computational geometry, and data fitting. We have described these applications in a way that is accessible, we hope, to a broad audience. To keep each application short, we consider only simple cases, sometimes adding comments about possible extensions. We are sure that our treatment of some of the applications will cause experts to cringe, and we apologize to them in advance. But our goal is to convey the flavor of the application, quickly and to a broad audience, and not to give an elegant, theoretically sound, or complete treatment. Our own backgrounds are in electrical engineering, in areas like control systems, signal processing, and circuit analysis and design. Although we include these topics in the courses we teach (using this book as the main text), only a few of these applications are broadly enough accessible to be included here.

The aim of part II is to show the reader, by example, how convex optimization can be applied in practice.

# 1.5.3 Part III: Algorithms

In part III, Algorithms, we describe numerical methods for solving convex optimization problems, focusing on Newton’s algorithm and interior-point methods. Part III is organized as three chapters, which cover unconstrained optimization, equality constrained optimization, and inequality constrained optimization, respectively. These chapters follow a natural hierarchy, in which solving a problem is reduced to solving a sequence of simpler problems. Quadratic optimization problems (including, e.g., least-squares) form the base of the hierarchy; they can be

solved exactly by solving a set of linear equations. Newton’s method, developed in chapters 9 and 10, is the next level in the hierarchy. In Newton’s method, solving an unconstrained or equality constrained problem is reduced to solving a sequence of quadratic problems. In chapter 11, we describe interior-point methods, which form the top level of the hierarchy. These methods solve an inequality constrained problem by solving a sequence of unconstrained, or equality constrained, problems.

Overall we cover just a handful of algorithms, and omit entire classes of good methods, such as quasi-Newton, conjugate-gradient, bundle, and cutting-plane algorithms. For the methods we do describe, we give simplified variants, and not the latest, most sophisticated versions. Our choice of algorithms was guided by several criteria. We chose algorithms that are simple (to describe and implement), but also reliable and robust, and effective and fast enough for most problems.

Many users of convex optimization end up using (but not developing) standard software, such as a linear or semidefinite programming solver. For these users, the material in part III is meant to convey the basic flavor of the methods, and give some ideas of their basic attributes. For those few who will end up developing new algorithms, we think that part III serves as a good introduction.

# 1.5.4 Appendices

There are three appendices. The first lists some basic facts from mathematics that we use, and serves the secondary purpose of setting out our notation. The second appendix covers a fairly particular topic, optimization problems with quadratic objective and one quadratic constraint. These are nonconvex problems that nevertheless can be effectively solved, and we use the results in several of the applications described in part II.

The final appendix gives a brief introduction to numerical linear algebra, concentrating on methods that can exploit problem structure, such as sparsity, to gain efficiency. We do not cover a number of important topics, including roundoff analysis, or give any details of the methods used to carry out the required factorizations. These topics are covered by a number of excellent texts.

# 1.5.5 Comments on examples

In many places in the text (but particularly in parts II and III, which cover applications and algorithms, respectively) we illustrate ideas using specific examples. In some cases, the examples are chosen (or designed) specifically to illustrate our point; in other cases, the examples are chosen to be ‘typical’. This means that the examples were chosen as samples from some obvious or simple probability distribution. The dangers of drawing conclusions about algorithm performance from a few tens or hundreds of randomly generated examples are well known, so we will not repeat them here. These examples are meant only to give a rough idea of algorithm performance, or a rough idea of how the computational effort varies with problem dimensions, and not as accurate predictors of algorithm performance. In particular, your results may vary from ours.

# 1.5.6 Comments on exercises

Each chapter concludes with a set of exercises. Some involve working out the details of an argument or claim made in the text. Others focus on determining, or establishing, convexity of some given sets, functions, or problems; or more generally, convex optimization problem formulation. Some chapters include numerical exercises, which require some (but not much) programming in an appropriate high level language. The difficulty level of the exercises is mixed, and varies without warning from quite straightforward to rather tricky.

# 1.6 Notation

Our notation is more or less standard, with a few exceptions. In this section we describe our basic notation; a more complete list appears on page 697.

We use $\mathbf { R }$ to denote the set of real numbers, $\mathbf { R } _ { + }$ to denote the set of nonnegative real numbers, and $\mathbf { R } _ { + + }$ to denote the set of positive real numbers. The set of real $n$ -vectors is denoted $\mathbf { R } ^ { n }$ , and the set of real $m \times n$ matrices is denoted $\mathbf { R } ^ { m \times n }$ . We delimit vectors and matrices with square brackets, with the components separated by space. We use parentheses to construct column vectors from comma separated lists. For example, if $a , \ b , \ c \in \mathbf { R }$ , we have

$$
(a, b, c) = \left[ \begin{array}{l} a \\ b \\ c \end{array} \right] = \left[ \begin{array}{l l l} a & b & c \end{array} \right] ^ {T},
$$

which is an element of $\mathbf { R } ^ { 3 }$ . The symbol 1 denotes a vector all of whose components are one (with dimension determined from context). The notation $x _ { i }$ can refer to the $i$ th component of the vector $x$ , or to the ith element of a set or sequence of vectors $x _ { 1 } , x _ { 2 } , \dotsc$ . The context, or the text, makes it clear which is meant.

We use $\mathbf { S } ^ { k }$ to denote the set of symmetric $k \times k$ matrices, $\mathbf { S } _ { + } ^ { k }$ to denote the set of symmetric positive semidefinite $k \times k$ matrices, and $\mathbf { S } _ { + + } ^ { k }$ to denote the set of symmetric positive definite $k \times k$ matrices. The curled inequality symbol $\succeq$ (and its strict form $\succ$ ) is used to denote generalized inequality: between vectors, it represents componentwise inequality; between symmetric matrices, it represents matrix inequality. With a subscript, the symbol $\preceq _ { K }$ (or $\prec _ { K }$ ) denotes generalized inequality with respect to the cone $K$ (explained in §2.4.1).

Our notation for describing functions deviates a bit from standard notation, but we hope it will cause no confusion. We use the notation $f : \mathbf { R } ^ { p }  \mathbf { R } ^ { q }$ to mean that $f$ is an $\mathbf { R } ^ { q }$ -valued function on some subset of $\mathbf { R } ^ { p }$ , specifically, its domain, which we denote $\operatorname { d o m } f$ . We can think of our use of the notation $f : \mathbf { R } ^ { p }  \mathbf { R } ^ { q }$ as a declaration of the function type, as in a computer language: $f : \mathbf { R } ^ { p }  \mathbf { R } ^ { q }$ means that the function $f$ takes as argument a real $p$ -vector, and returns a real $q$ -vector. The set $\operatorname { d o m } f$ , the domain of the function $f$ , specifies the subset of $\mathbf { R } ^ { p }$ of points $x$ for which $f ( x )$ is defined. As an example, we describe the logarithm function as $\log : \mathbf { R }  \mathbf { R }$ , with $\mathbf { d o m } \log = \mathbf { R } _ { + + }$ . The notation $\log : \mathbf { R }  \mathbf { R }$ means that

the logarithm function accepts and returns a real number; $\mathbf { d o m } \log = \mathbf { R } _ { + + }$ means that the logarithm is defined only for positive numbers.

We use $\mathbf { R } ^ { n }$ as a generic finite-dimensional vector space. We will encounter several other finite-dimensional vector spaces, e.g., the space of polynomials of a variable with a given maximum degree, or the space $\mathbf { S } ^ { k }$ of symmetric $k \times k$ matrices. By identifying a basis for a vector space, we can always identify it with $\mathbf { R } ^ { n }$ (where $n$ is its dimension), and therefore the generic results, stated for the vector space $\mathbf { R } ^ { n }$ , can be applied. We usually leave it to the reader to translate general results or statements to other vector spaces. For example, any linear function $f : \mathbf { R } ^ { n }  \mathbf { R }$ can be represented in the form $f ( x ) = c ^ { T } x$ , where $c \in \mathbf { R } ^ { \pi }$ . The corresponding statement for the vector space $\mathbf { S } ^ { k }$ can be found by choosing a basis and translating. This results in the statement: any linear function $f : \mathbf { S } ^ { k }  \mathbf { R }$ can be represented in the form $f ( X ) = \mathbf { t r } ( C X )$ , where $C \in \mathbf { S } ^ { k }$ .

# Bibliography

Least-squares is a very old subject; see, for example, the treatise written (in Latin) by Gauss in the 1820s, and recently translated by Stewart [Gau95]. More recent work includes the books by Lawson and Hanson [LH95] and Bj¨orck [Bj¨o96]. References on linear programming can be found in chapter 4.

There are many good texts on local methods for nonlinear programming, including Gill, Murray, and Wright [GMW81], Nocedal and Wright [NW99], Luenberger [Lue84], and Bertsekas [Ber99].

Global optimization is covered in the books by Horst and Pardalos [HP94], Pinter [Pin95], and Tuy [Tuy98]. Using convex optimization to find bounds for nonconvex problems is an active research topic, and addressed in the books above on global optimization, the book by Ben-Tal and Nemirovski [BTN01, §4.3], and the survey by Nesterov, Wolkowicz, and Ye [NWY00]. Some notable papers on this subject are Goemans and Williamson [GW95], Nesterov [Nes00, Nes98], Ye [Ye99], and Parrilo [Par03]. Randomized methods are discussed in Motwani and Raghavan [MR95].

Convex analysis, the mathematics of convex sets, functions, and optimization problems, is a well developed subfield of mathematics. Basic references include the books by Rockafellar [Roc70], Hiriart-Urruty and Lemar´echal [HUL93, HUL01], Borwein and Lewis [BL00], and Bertsekas, Nedi´c, and Ozdaglar [Ber03]. More references on convex analysis can be found in chapters 2–5.

Nesterov and Nemirovski [NN94] were the first to point out that interior-point methods can solve many convex optimization problems; see also the references in chapter 11. The book by Ben-Tal and Nemirovski [BTN01] covers modern convex optimization, interiorpoint methods, and applications.

Solution methods for convex optimization that we do not cover in this book include subgradient methods [Sho85], bundle methods [HUL93], cutting-plane methods [Kel60, EM75, GLY96], and the ellipsoid method [Sho91, BGT81].

The idea that convex optimization problems are tractable is not new. It has long been recognized that the theory of convex optimization is far more straightforward (and complete) than the theory of general nonlinear optimization. In this context Rockafellar stated, in his 1993 SIAM Review survey paper [Roc93],

In fact the great watershed in optimization isn’t between linearity and nonlinearity, but convexity and nonconvexity.

The first formal argument that convex optimization problems are easier to solve than general nonlinear optimization problems was made by Nemirovski and Yudin, in their 1983 book Problem Complexity and Method Efficiency in Optimization [NY83]. They showed that the information-based complexity of convex optimization problems is far lower than that of general nonlinear optimization problems. A more recent book on this topic is Vavasis [Vav91].

The low (theoretical) complexity of interior-point methods is integral to modern research in this area. Much of the research focuses on proving that an interior-point (or other) method can solve some class of convex optimization problems with a number of operations that grows no faster than a polynomial of the problem dimensions and log(1/ǫ), where $\epsilon > 0$ is the required accuracy. (We will see some simple results like these in chapter 11.) The first comprehensive work on this topic is the book by Nesterov and Nemirovski [NN94]. Other books include Ben-Tal and Nemirovski [BTN01, lecture 5] and Renegar [Ren01]. The polynomial-time complexity of interior-point methods for various convex optimization problems is in marked contrast to the situation for a number of nonconvex optimization problems, for which all known algorithms require, in the worst case, a number of operations that is exponential in the problem dimensions.

Convex optimization has been used in many applications areas, too numerous to cite here. Convex analysis is central in economics and finance, where it is the basis of many results. For example the separating hyperplane theorem, together with a no-arbitrage assumption, is used to deduce the existence of prices and risk-neutral probabilities (see, e.g., Luenberger [Lue95, Lue98] and Ross [Ros99]). Convex optimization, especially our ability to solve semidefinite programs, has recently received particular attention in automatic control theory. Applications of convex optimization in control theory can be found in the books by Boyd and Barratt [BB91], Boyd, El Ghaoui, Feron, and Balakrishnan [BEFB94], Dahleh and Diaz-Bobillo [DDB95], El Ghaoui and Niculescu [EN00], and Dullerud and Paganini [DP00]. A good example of embedded (convex) optimization is model predictive control, an automatic control technique that requires the solution of a (convex) quadratic program at each step. Model predictive control is now widely used in the chemical process control industry; see Morari and Zafirou [MZ89]. Another applications area where convex optimization (and especially, geometric programming) has a long history is electronic circuit design. Research papers on this topic include Fishburn and Dunlop [FD85], Sapatnekar, Rao, Vaidya, and Kang [SRVK93], and Hershenson, Boyd, and Lee [HBL01]. Luo [Luo03] gives a survey of applications in signal processing and communications. More references on applications of convex optimization can be found in chapters 4 and 6–8.

High quality implementations of recent interior-point methods for convex optimization problems are available in the LOQO [Van97] and MOSEK [MOS02] software packages, and the codes listed in chapter 11. Software systems for specifying optimization problems include AMPL [FGK99] and GAMS [BKMR98]. Both provide some support for recognizing problems that can be transformed to linear programs.

# 第一章

# 引言

在本引言中，我们将概述数学优化，特别关注凸优化的特殊作用。这里非正式介绍的概念将在后续章节中更仔细、更技术性地进行阐述。

# 1.1 数学优化

一个数学优化问题，或简称为优化问题，具有以下形式

$$
\begin{array}{l l} \text {最小化} & f _ {0} (x) \\ \text {约束条件} & f _ {i} (x) \leqslant b, \quad i = 1, \dots , m. \end{array} \tag {1.1}
$$

这里向量 ${ \boldsymbol x } = ( x _ { 1 } , \dots , x _ { n } )$ 是问题的优化变量，函数 $f _ { 0 } : \mathbf { R } ^ { n }  \mathbf { R }$ 是目标函数，函数 $f _ { i } : \mathbf { R } ^ { n }  \mathbf { R }$ ， $i = 1 , \ldots , m$ ，是（不等式）约束函数，常数 $b _ { 1 } , \ldots , b _ { m }$ 是约束的界限或边界。一个向量 $x ^ { \star }$ 被称为最优的，或问题 (1.1) 的解，如果它在所有满足约束的向量中具有最小的目标值：对于任何满足 $f _ { 1 } ( z ) \leq b _ { 1 } , \ldots , f _ { m } ( z ) \leq b _ { m }$ 的 $z$ ，我们有 $f _ { 0 } ( z ) \geq f _ { 0 } ( x ^ { \star } )$ 。

我们通常考虑优化问题的族或类，这些类由目标函数和约束函数的特定形式来表征。作为一个重要的例子，如果目标函数和约束函数 $f _ { 0 } , \ldots , f _ { m }$ 是线性的，即满足

$$
f _ {i} (\alpha x + \beta y) = \alpha f _ {i} (x) + \beta f _ {i} (y) \tag {1.2}
$$

对于所有 $x , \ y \in \mathbf { R } ^ { \pi }$ 和所有 $\alpha , ~ \beta \in \mathbf { R }$ ，则优化问题 (1.1) 被称为线性规划。如果优化问题不是线性的，则称为非线性规划。

本书是关于一类称为凸优化问题的优化问题。凸优化问题是指目标函数和约束函数都是凸的，这意味着它们满足不等式

$$
f _ {i} (\alpha x + \beta y) \leq \alpha f _ {i} (x) + \beta f _ {i} (y) \tag {1.3}
$$

对于所有 $x , \ y \in \mathbf { R } ^ { \pi }$ 和所有满足 $\alpha + \beta = 1$ ， $\alpha \geq 0$ ， $\beta \geq 0$ 的 $\alpha , ~ \beta \in \mathbf { R }$ 。比较 (1.3) 和 (1.2)，我们看到凸性比线性更一般：不等式取代了更严格的等式，并且该不等式仅需对某些 $\alpha$ 和 $\beta$ 值成立。由于任何线性规划因此都是凸优化问题，我们可以将凸优化视为线性规划的推广。

# 1.1.1 应用

优化问题 (1.1) 是从一组候选选择中做出最佳向量选择的抽象。变量 $x$ 代表所做的选择；约束 $f _ { i } ( x ) \leq b _ { i }$ 代表限制可能选择的硬性要求或规格，目标值 $f _ { 0 } ( x )$ 代表选择 $x$ 的成本。（我们也可以将 $- f _ { 0 } ( x )$ 视为选择 $x$ 的价值或效用。）优化问题 (1.1) 的解对应于在所有满足硬性要求的选择中具有最小成本（或最大效用）的选择。

例如，在投资组合优化中，我们寻求在 $n$ 种资产中投资某些资本的最佳方式。变量 $x _ { i }$ 代表对第 $i$ 种资产的投资，因此向量 $\boldsymbol { x } \in \mathbf { R } ^ { n }$ 描述了跨资产集的整体投资组合配置。约束可能代表预算限制（即总投资额的限制）、投资非负的要求（假设不允许卖空）以及整个投资组合预期回报的最低可接受值。目标或成本函数可能是整个投资组合回报的风险或方差的度量。在这种情况下，优化问题 (1.1) 对应于在所有满足硬性要求的可能配置中选择最小化风险的投资组合配置。

另一个例子是电子设计中的器件尺寸确定，即选择电子电路中每个器件的宽度和长度。这里的变量代表器件的宽度和长度。约束代表各种工程要求，例如制造工艺对器件尺寸的限制、确保电路能以指定速度可靠运行的时序要求，以及电路总面积限制。器件尺寸确定问题中常见的目标是电路消耗的总功率。优化问题 (1.1) 是找到满足设计要求（关于可制造性、时序和面积）且功率效率最高的器件尺寸。

在数据拟合中，任务是从一组潜在模型中找到一个最能拟合观测数据和先验信息的模型。这里的变量是模型中的参数，约束可以代表先验信息或对参数的要求限制（例如非负性）。目标函数可能是观测数据与模型预测值之间的失配或预测误差的度量，或者是参数值的不可能性或不可信度的统计度量。优化问题 (1.1) 是找到与先验信息一致且与观测数据失配或预测误差最小（或在统计框架下最可能）的模型参数值。

涉及决策制定（或系统设计、分析和操作）的各种实际问题都可以以数学优化问题或其某种变体（如多准则优化问题）的形式来表述。事实上，数学优化已成为许多领域的重要工具。它广泛应用于工程领域，如电子设计自动化、自动控制系统以及土木、化学、机械和航空航天工程中出现的最优设计问题。优化用于网络设计和运营、金融、供应链管理、调度以及许多其他领域出现的问题。应用列表仍在稳步扩大。

对于大多数这些应用，数学优化被用作人类决策者、系统设计者或系统操作员的辅助工具，他们监督过程、检查结果，并在必要时修改问题（或解决方法）。这位人类决策者还执行优化问题建议的任何操作，例如，买卖资产以实现最优投资组合。

一个相对较新的现象为数学优化的许多其他应用开辟了可能性。随着嵌入产品的计算机的普及，我们看到了嵌入式优化的快速增长。在这些嵌入式应用中，优化用于自动做出实时选择，甚至执行相关操作，而无需（或很少）人工干预或监督。在一些应用领域，传统自动控制系统与嵌入式优化的融合已经深入；在其他领域，则刚刚开始。嵌入式实时优化带来了一些新的挑战：特别是，它需要极其可靠且在可预测的时间（和内存）内解决问题的求解方法。

# 1.1.2 求解优化问题

对于一类优化问题的求解方法是一种算法，给定该类中的一个特定问题（即问题的一个实例），它能计算出该问题的解（达到给定的精度）。自 20 世纪 40 年代末以来，人们投入了大量精力开发用于求解各类优化问题的算法，分析其性质，并开发良好的软件实现。这些算法的有效性，即我们求解优化问题 (1.1) 的能力，差异很大，并取决于诸如目标函数和约束函数的具体形式、变量和约束的数量以及特殊结构（如稀疏性）等因素。（如果每个约束函数仅依赖于少数变量，则问题是稀疏的）。

即使目标函数和约束函数是光滑的（例如多项式），一般优化问题 (1.1) 的求解也出奇地困难。因此，解决一般问题的方法涉及某种妥协，例如非常长的计算时间，或者可能找不到解。其中一些方法将在 §1.4 中讨论。

然而，对于大多数优化问题难以求解的一般规则，有一些重要的例外。对于少数几类问题，我们拥有有效的算法，可以可靠地求解甚至大型问题，包含数百或数千个变量和约束。两个重要且众所周知的例子是 §1.2 下面（以及第 4 章详细描述）的最小二乘问题和线性规划。不太为人所知的是，凸优化是另一个例外：与最小二乘或线性规划类似，存在非常有效的算法，可以可靠且高效地求解甚至大型凸问题。

# 1.2 最小二乘和线性规划

在本节中，我们描述凸优化中两个非常著名且广泛使用的特殊子类：最小二乘和线性规划。（这些问题的完整技术处理将在第 4 章给出。）

# 1.2.1 最小二乘问题

最小二乘问题是一个没有约束（即 $m =$ 0）且目标是 $a _ { i } ^ { \scriptscriptstyle T } x - b _ { i }$ 形式项的平方和的优化问题：

$$
\text {最小化} \quad f _ {0} (x) = \| A x - b \| _ {2} ^ {2} = \sum_ {i = 1} ^ {k} \left(a _ {i} ^ {T} x - b _ {i}\right) ^ {2}. \tag {1.4}
$$

这里 $A \in \mathbf { R } ^ { k \times n }$ （其中 $k \geq n$ ）， $a _ { i } ^ { \scriptscriptstyle T }$ 是 $A$ 的行，向量 $x \in \mathbf { R } ^ { \pi }$ 是优化变量。

# 求解最小二乘问题

最小二乘问题 (1.4) 的解可以简化为求解一组线性方程，

$$
(A ^ {T} A) x = A ^ {T} b,
$$

因此我们有解析解 $x = ( A ^ { T } A ) ^ { - 1 } A ^ { T } b$ 。对于最小二乘问题，我们有良好的算法（和软件实现）来高精度、高可靠性地求解问题。最小二乘问题的求解时间大约与 $n ^ { 2 } k$ 成正比，具有已知常数。当前的台式计算机可以在几秒钟内求解具有数百个变量和数千项的最小二乘问题；更强大的计算机当然可以求解更大的问题，或更快地求解相同规模的问题。（此外，根据摩尔定律，这些求解时间在未来将呈指数级下降。）求解最小二乘问题的算法和软件足够可靠，可用于嵌入式优化。

在许多情况下，我们可以通过利用系数矩阵 $A$ 中的一些特殊结构来求解更大的最小二乘问题。例如，假设矩阵 $A$ 是稀疏的，这意味着它的非零条目远少于 $k n$ 个。通过利用稀疏性，我们通常可以比 $n ^ { 2 } k$ 阶快得多地求解最小二乘问题。当前的台式计算机可以在一分钟左右求解具有数万个变量和数十万项的稀疏最小二乘问题（尽管这取决于具体的稀疏模式）。

对于极其庞大的问题（例如，具有数百万个变量），或具有苛刻实时计算要求的问题，求解最小二乘问题可能是一个挑战。但在绝大多数情况下，我们可以说现有方法非常有效且极其可靠。事实上，我们可以说求解最小二乘问题（那些不在当前可实现边界上的问题）是一项（成熟的）技术，可以被许多不了解且不需要了解细节的人可靠地使用。

# 使用最小二乘

最小二乘问题是回归分析、最优控制以及许多参数估计和数据拟合方法的基础。它具有多种统计解释，例如，作为在存在高斯测量误差的情况下，给定线性测量值对向量 $x$ 的最大似然估计。

识别一个优化问题为最小二乘问题是直接的；我们只需要验证目标函数是二次函数（然后测试相关的二次型是否半正定）。虽然基本最小二乘问题具有简单的固定形式，但几种标准技术被用来增加其在应用中的灵活性。

在加权最小二乘中，最小化加权最小二乘成本

$$
\sum_ {i = 1} ^ {k} w _ {i} (a _ {i} ^ {T} x - b _ {i}) ^ {2},
$$

其中 $w _ { 1 } , \ldots , w _ { k }$ 为正。（这个问题很容易转化为标准最小二乘问题并求解。）这里权重 $w _ { i }$ 被选择以反映对项 $a _ { i } ^ { \scriptscriptstyle T } x - b _ { i }$ 大小的不同关注程度，或仅仅是为了影响解。在统计设置中，当给定被具有不等方差的误差破坏的线性测量值来估计向量 $x$ 时，会出现加权最小二乘。

最小二乘中的另一种技术是正则化，其中将额外的项添加到成本函数中。在最简单的情况下，将变量的平方和的正倍数添加到成本函数中：

$$
\sum_ {i = 1} ^ {k} (a _ {i} ^ {T} x - b _ {i}) ^ {2} + \rho \sum_ {i = 1} ^ {n} x _ {i} ^ {2},
$$

其中 $\rho > 0$ 。（这个问题也可以表述为标准最小二乘问题。）额外的项惩罚 $x$ 的大值，并在仅最小化第一个和不能得到合理解的情况下产生合理的解。参数 $\rho$ 被选择以在使原始目标函数 $\scriptstyle \sum _ { i = 1 } ^ { k } ( a _ { i } ^ { T } x - b _ { i } ) ^ { 2 }$ 不太大的同时，保持 $\textstyle \sum _ { i = 1 } ^ { n } x _ { i } ^ { 2 }$ 较小，从而在两者之间取得正确的权衡。当要估计的向量 $x$ 被赋予先验分布时，正则化出现在统计估计中。

加权最小二乘和正则化在第 6 章中介绍；它们的统计解释在第 7 章中给出。

# 1.2.2 线性规划

另一类重要的优化问题是线性规划，其中目标和所有约束函数都是线性的：

$$
\begin{array}{l l} \text {最小化} & c ^ {T} x \\ \text {约束条件} & a _ {i} ^ {T} x <   b _ {i}, \quad i = 1, \end{array} \tag {1.5}
$$

这里向量 $c , a _ { 1 } , \ldots , a _ { m } \in \mathbf { R } ^ { n }$ 和标量 $b _ { 1 } , \dotsc , - b _ { m } \in \mathbf { R }$ 是指定目标函数和约束函数的问题参数。

# 求解线性规划

对于线性规划的解，没有像最小二乘问题那样的简单解析公式，但有多种非常有效的方法来求解它们，包括丹齐格的单纯形法，以及本书后面描述的更近期的内点法。虽然我们不能给出求解线性规划所需的精确算术运算次数（就像对最小二乘那样），但我们可以使用内点法建立求解线性规划达到给定精度所需运算次数的严格界限。实际复杂度是 $n ^ { 2 } m$ 阶（假设 $m \geq n$ ），但其常数不如最小二乘那样特征明确。这些算法相当可靠，尽管可能不如最小二乘方法那么可靠。我们可以在小型台式计算机上轻松求解具有数百个变量和数千个约束的问题，只需几秒钟。如果问题是稀疏的，或者具有其他可利用的结构，我们通常可以求解具有数万或数十万个变量和约束的问题。

与最小二乘问题一样，求解极其庞大的线性规划，或求解具有苛刻实时计算要求的线性规划，仍然是一个挑战。但是，与最小二乘类似，我们可以说求解（大多数）线性规划是一项成熟的技术。线性规划求解器可以（并且已经）嵌入到许多工具和应用中。

# 使用线性规划

一些应用直接导致形式为 (1.5) 的线性规划，或几种其他标准形式之一。在许多其他情况下，原始优化问题不具有标准线性规划形式，但可以使用第 4 章详细描述的技术转化为等价的线性规划（然后当然可以求解）。

作为一个简单的例子，考虑切比雪夫逼近问题：

$$
\text {最小化} \quad \max  _ {i = 1, \dots , k} \left| a _ {i} ^ {T} x - b _ {i} \right|. \tag {1.6}
$$

这里 $\boldsymbol { x } \in \mathbf { R } ^ { n }$ 是变量， $a _ { 1 } , \ldots , a _ { k } \in \mathbf { R } ^ { n }$ ， $b _ { 1 } , \dotsc , b _ { k } \in \mathbf { R }$ 是指定问题实例的参数。注意与最小二乘问题 (1.4) 的相似性。对于这两个问题，目标都是项 $a _ { i } ^ { 2 } x - b _ { i }$ 大小的度量。在最小二乘中，我们使用项的平方和作为目标，而在切比雪夫逼近中，我们使用绝对值的最大值。

另一个重要区别是切比雪夫逼近问题 (1.6) 中的目标函数不可微；最小二乘问题 (1.4) 中的目标是二次的，因此是可微的。

切比雪夫逼近问题 (1.6) 可以通过求解线性规划来求解

$$
\begin{array}{l} \begin{array}{l l} \text {最小化} & t \\ \text {约束条件} & a _ {i} ^ {T} x - t \leq b _ {i}, \quad i = 1, \dots , k \end{array} \tag {1.7} \\ - a _ {i} ^ {T} x - t \leq - b _ {i}, \quad i = 1, \dots , k, \\ \end{array}
$$

变量为 $x \in \mathbf { R } ^ { n }$ 和 $t \in \textbf { R }$ 。（细节将在第 6 章给出。）由于线性规划易于求解，因此切比雪夫逼近问题也易于求解。

任何具备线性规划工作知识的人都会认识到切比雪夫逼近问题 (1.6) 可以简化为线性规划。然而，对于那些没有这种背景的人来说，可能并不明显具有不可微目标的切比雪夫逼近问题 (1.6) 可以表述并作为线性规划求解。

虽然识别可以简化为线性规划的问题比识别最小二乘问题更复杂，但这是一种很容易获得的技能，因为只使用了少数标准技巧。这项任务甚至可以部分自动化；一些用于指定和求解优化问题的软件系统可以自动识别（某些）可以重新表述为线性规划的问题。

# 1.3 凸优化

凸优化问题是形式如下的问题

$$
\begin{array}{l l} \text {最小化} & f _ {0} (x) \\ \text {约束条件} & f (x) <   b, \quad i = 1, \dots , m \end{array} \tag {1.8}
$$

$$
\text {约束条件} f _ {i} (x) \leq b _ {i}, \quad i = 1, \dots , m,
$$

其中函数 $f _ { 0 } , \ldots , f _ { m } : \mathbf { R } ^ { n }  \mathbf { R }$ 是凸的，即满足

$$
f _ {i} (\alpha x + \beta y) \leq \alpha f _ {i} (x) + \beta f _ {i} (y)
$$

对于所有 $x , y \in \mathbf { R } ^ { \pi }$ 和所有满足 $\alpha + \beta = 1$ ， $\alpha \geq 0$ ， $\beta \geq 0$ 的 $\alpha , ~ \beta \in \mathbf { R }$ 。最小二乘问题 (1.4) 和线性规划问题 (1.5) 都是广义凸优化问题 (1.8) 的特例。

# 1.3.1 求解凸优化问题

一般来说，凸优化问题没有解析解公式，但（与线性规划问题一样）存在非常有效的方法来求解它们。内点法在实践中效果很好，并且在某些情况下可以被证明能以不超过问题维数的多项式的运算次数将问题求解到指定的精度。（这将在第 11 章中介绍。）

我们将看到，内点法可以在几乎总是介于 10 到 100 之间的步数或迭代次数内求解问题 (1.8)。忽略问题中的任何结构（如稀疏性），每一步大约需要

$$
\max  \{n ^ {3}, n ^ {2} m, F \}
$$

次运算，其中 $F ^ { \dagger }$ 是评估目标函数和约束函数 $f _ { 0 } , \ldots , f _ { m }$ 的一阶和二阶导数的成本。

与求解线性规划的方法类似，这些内点法相当可靠。我们可以在当前的台式计算机上轻松求解具有数百个变量和数千个约束的问题，最多只需几十秒。通过利用问题结构（如稀疏性），我们可以求解更大的问题，具有数千个变量和约束。

我们还不能声称求解一般凸优化问题是一项像求解最小二乘或线性规划问题那样的成熟技术。用于一般非线性凸优化的内点法研究仍然是一个非常活跃的研究领域，关于什么是最好的方法或方法尚未达成共识。但可以合理预期，求解一般凸优化问题将在几年内成为一项技术。而对于凸优化问题的某些子类，例如二阶锥规划或几何规划（在第 4 章详细研究），可以说内点法正在接近一项技术。

# 1.3.2 使用凸优化

使用凸优化在概念上非常类似于使用最小二乘或线性规划。如果我们可以将一个问题表述为凸优化问题，那么我们就可以高效地求解它，就像我们可以高效地求解最小二乘问题一样。略带夸张地说，如果你将一个实际问题表述为凸优化问题，那么你就已经解决了原始问题。

也存在一些重要的区别。识别最小二乘问题是直接的，但识别凸函数可能很困难。此外，用于转化凸问题的技巧比用于转化线性规划的多得多。因此，识别凸优化问题或可以转化为凸优化问题的问题可能具有挑战性。本书的主要目标是让读者具备完成此任务所需的背景知识。一旦掌握了识别或表述凸优化问题的技能，你会发现令人惊讶的许多问题可以通过凸优化来解决。

使用凸优化的挑战和艺术在于识别和表述问题。一旦完成表述，求解问题就像最小二乘或线性规划一样，（几乎）是一项技术。

# 1.4 非线性优化

非线性优化（或非线性规划）是用于描述当目标函数或约束函数不是线性但未知是否为凸时的优化问题的术语。遗憾的是，没有有效的方法来求解一般非线性规划问题 (1.1)。即使是只有十个变量的简单问题也可能极具挑战性，而具有几百个变量的问题可能无法求解。因此，用于一般非线性规划问题的方法采取了几种不同的途径，每种途径都涉及某种妥协。

# 1.4.1 局部优化

在局部优化中，妥协是放弃寻找在所有可行点中最小化目标的最优 $x$ 。相反，我们寻找一个仅是局部最优点，这意味着它在附近的可行点中最小化目标函数，但不能保证其目标值低于所有其他可行点。大部分关于一般非线性规划的研究都集中在局部优化方法上，因此这些方法得到了很好的发展。

局部优化方法可以很快，可以处理大规模问题，并且适用范围广，因为它们只需要目标函数和约束函数的可微性。因此，局部优化方法被广泛应用于那些找到好的点（即使不是最好的点）也有价值的应用中。例如，在工程设计中，局部优化可用于改进最初通过手动或其他设计方法获得的设计的性能。

局部优化方法有几个缺点，除了（可能）找不到真正的全局最优解之外。这些方法需要优化变量的初始猜测。这个初始猜测或起点至关重要，并且可以极大地影响获得的局部解的目标值。关于局部解距离（全局）最优有多远的信息很少。局部优化方法通常对算法参数值敏感，这些参数值可能需要针对特定问题或问题族进行调整。

使用局部优化方法比求解最小二乘问题、线性规划或凸优化问题更复杂。它涉及尝试选择算法、调整算法参数以及找到足够好的初始猜测（当要求解一个实例时）或产生足够好的初始猜测的方法（当要求解一系列问题时）。粗略地说，局部优化方法更像是艺术而非技术。局部优化是一门发展完善的艺术，通常非常有效，但它仍然是一门艺术。相比之下，求解最小二乘问题或线性规划几乎不涉及艺术（当然，除了那些处于当前可实现边界的问题）。

非线性规划的局部优化方法与凸优化之间可以做一个有趣的比较。由于大多数局部优化方法只需要目标函数和约束函数的可微性，因此将实际问题表述为非线性优化问题相对简单。局部优化中的艺术在于问题表述之后求解问题（在找到局部最优点的弱意义上）。在凸优化中，这些是相反的：艺术和挑战在于问题表述；一旦问题被表述为凸优化问题，求解它就相对简单了。

# 1.4.2 全局优化

在全局优化中，找到优化问题 (1.1) 的真正全局解；妥协的是效率。全局优化方法的最坏情况复杂度随着问题规模 $n$ 和 $m$ 呈指数增长；希望在实践中，对于遇到的特定问题实例，该方法要快得多。虽然这种有利情况确实会发生，但并不典型。即使是只有几十个变量的小问题，也可能需要很长时间（例如，数小时或数天）来求解。

全局优化用于变量数量少、计算时间不关键且找到真正全局解的价值非常高的问题。工程设计中的一个例子是高价值或安全关键系统的最坏情况分析或验证。这里的变量代表不确定参数，这些参数可能在制造过程中、或随环境或操作条件而变化。目标函数是一个效用函数，即较小值比较值更差的函数，约束代表关于参数可能值的先验知识。优化问题 (1.1) 是找到参数最坏值的问题。如果最坏情况值是可接受的，我们可以将系统认证为安全或可靠（关于参数变化）。

局部优化方法可以快速找到一组不良的参数值，但不能保证是绝对最坏的。如果局部优化方法找到产生不可接受性能的参数值，它就成功地确定了系统不可靠。但局部优化方法不能将系统认证为可靠；它只能未能找到不良参数值。相比之下，全局优化方法将找到参数的绝对最坏值，如果相关性能可接受，则可以将系统认证为安全。代价是计算时间，即使对于相对较少的参数，也可能非常长。但在认证性能的价值很高，或关于可靠性或安全性的错误成本很高的情况下，这可能是值得的。

# 1.4.3 凸优化在非凸问题中的作用

本书主要关注凸优化问题，以及可以简化为凸优化问题的应用。但凸优化在非凸问题中也扮演着重要角色。

## 局部优化的初始化

一个明显的用途是将凸优化与局部优化方法结合。从一个非凸问题出发，我们首先找到该问题的一个近似但凸的表述。通过求解这个近似问题（这可以轻松完成且无需初始猜测），我们得到近似凸问题的精确解。然后，将这个点用作应用于原始非凸问题的局部优化方法的起始点。

## 非凸优化的凸启发式方法

凸优化是解决非凸问题的几种启发式方法的基础。我们将看到的一个有趣例子是寻找满足某些约束的稀疏向量 $x$（即非零项很少的向量）。虽然这是一个困难的组合问题，但存在一些基于凸优化的简单启发式方法，通常能找到相当稀疏的解。（这些方法在第6章中描述。）

另一个广泛的例子是随机算法，其中通过从概率分布中抽取一定数量的候选解，并将找到的最佳解作为近似解，来找到非凸问题的近似解。现在假设我们将从中抽取候选解的概率分布族是参数化的，例如，由其均值和协方差参数化。那么我们可以提出这样的问题：这些分布中哪一个能给出目标函数的最小期望值？事实证明，这个问题有时是一个凸问题，因此可以高效求解。（参见，例如，练习11.23。）

1. **参数化分布族**：  
   例如，考虑高斯分布族，由其均值 $\mu$ 和协方差 $\Sigma$ 参数化。
2. **优化分布参数**：  
   问题变为：寻找最优的 $(\mu, \Sigma)$，使得从分布 $p(x; \mu, \Sigma)$ 中抽取的随机解 $x$ 的**期望目标值** $\mathbb{E}[f(x)]$ 最小。
3. **凸化**：  
   在某些条件下，这个关于 $(\mu, \Sigma)$ 的优化问题是**凸的**，因此可以用凸优化方法高效求解。

## 全局优化的界

许多全局优化方法需要一个可以廉价计算的非凸问题最优值的下界。实现这一点的两种标准方法基于凸优化。在松弛法中，每个非凸约束被替换为一个更宽松但凸的约束。在拉格朗日松弛法中，求解拉格朗日对偶问题（在第5章中描述）。这个问题是凸的，并提供了非凸问题最优值的一个下界。

# 1.5 大纲

本书分为三个主要部分，标题为理论、应用和算法。

## 1.5.1 第一部分：理论

在第一部分“理论”中，我们涵盖了凸分析和凸优化的基本定义、概念和结果。我们并不试图做到面面俱到，而是将主题选择偏向于我们认为在识别和表述凸优化问题中有用的内容。这是经典材料，几乎都可以在其他凸分析和优化教材中找到。我们并不试图给出结果的最一般形式；为此，读者可以参考任何凸分析的标准教材。

第2章和第3章分别涵盖凸集和凸函数。我们给出了一些凸集和凸函数的常见例子，以及许多凸演算规则，即保持凸性的集合和函数运算。将基本例子与凸演算规则相结合，使我们能够形成（或者更重要的是，识别）一些相当复杂的凸集和凸函数。

在第4章“凸优化问题”中，我们仔细处理了优化问题，并描述了许多可用于重新表述问题的变换。我们还介绍了凸优化的一些常见子类，如线性规划和几何规划，以及最近发展的二阶锥规划和半定规划。

第5章涵盖拉格朗日对偶性，它在凸优化中起着核心作用。这里我们给出了最优性的经典Karush-Kuhn-Tucker条件，以及凸优化问题的局部和全局灵敏度分析。

## 1.5.2 第二部分：应用

在第二部分“应用”中，我们描述了凸优化在各个领域的各种应用，如概率与统计、计算几何和数据拟合。我们希望以一种易于广大读者理解的方式描述这些应用。为了保持每个应用的简洁性，我们只考虑简单情况，有时会添加关于可能扩展的评论。我们确信，我们对某些应用的处理会让专家感到不适，我们在此提前向他们致歉。但我们的目标是快速地向广大读者传达应用的风味，而不是给出优雅、理论严谨或完整的处理。我们自己的背景是电气工程，涉及控制系统、信号处理、电路分析和设计等领域。虽然我们在教授的课程中（使用本书作为主要教材）包含了这些主题，但只有少数这些应用具有足够的普适性，可以包含在此处。

第二部分的目的是通过示例向读者展示凸优化如何在实践中应用。

## 1.5.3 第三部分：算法

在第三部分“算法”中，我们描述了求解凸优化问题的数值方法，重点介绍牛顿算法和内点法。第三部分分为三章，分别涵盖无约束优化、等式约束优化和不等式约束优化。这些章节遵循一个自然的层次结构，其中求解一个问题被简化为求解一系列更简单的问题。二次优化问题（包括，例如，最小二乘）构成了该层次结构的基础；它们可以通过求解一组线性方程来精确求解。在第9章和第10章中发展的牛顿法是该层次结构的下一级。在牛顿法中，求解无约束或等式约束问题被简化为求解一系列二次问题。在第11章中，我们描述了内点法，它们构成了该层次结构的顶层。这些方法通过求解一系列无约束或等式约束问题来解决不等式约束问题。

总的来说，我们只涵盖了少数几种算法，并省略了整类优秀的方法，如拟牛顿法、共轭梯度法、束方法和割平面法。对于我们确实描述的方法，我们给出简化的变体，而不是最新、最复杂的版本。我们选择算法的标准有几个。我们选择那些简单（易于描述和实现）、可靠且稳健、对于大多数问题足够有效和快速的算法。

许多凸优化用户最终会使用（但不开发）标准软件，例如线性或半定规划求解器。对于这些用户，第三部分的材料旨在传达方法的基本风味，并给出它们基本属性的一些概念。对于那些最终将开发新算法的少数人，我们认为第三部分是一个很好的入门。

## 1.5.4 附录

有三个附录。第一个列出了我们使用的一些数学基本事实，并起到次要作用，即阐明我们的符号。

第二个附录涵盖了一个相当特殊的主题，即具有二次目标和一次二次约束的优化问题。这些是非凸问题，但可以有效求解，我们在第二部分描述的多个应用中使用了这些结果。

最后一个附录简要介绍了数值线性代数，重点关注可以**利用问题结构**（如稀疏性）来提高效率的方法。我们没有涵盖许多重要主题，包括舍入误差分析，也没有给出执行所需分解的方法的任何细节。这些主题在许多优秀教材中都有涵盖。

## 1.5.5 关于示例的评论

在正文的许多地方（但特别是在第二部分和第三部分，分别涵盖应用和算法），我们使用具体示例来说明思想。在某些情况下，示例是专门选择（或设计）来说明我们的观点；在其他情况下，示例被选择为“典型”的。这意味着示例是从某个明显或简单的概率分布中抽取的样本。从几十或几百个随机生成的示例中得出关于算法性能的结论的危险是众所周知的，因此我们在此不再赘述。这些示例仅旨在给出算法性能的粗略概念，或计算工作量如何随问题维度变化的粗略概念，而不是作为算法性能的准确预测器。特别是，您的结果可能与我们的结果不同。

## 1.5.6 关于练习的评论

每章以一组练习结束。有些练习涉及推导正文中某个论点或主张的细节。其他练习侧重于确定或证明某些给定集合、函数或问题的凸性；或更一般地说，凸优化问题的表述。有些章节包括数值练习，这些练习需要在适当的高级语言中进行一些（但不多）编程。练习的难度水平参差不齐，并且在没有警告的情况下从相当简单到相当棘手不等。

# 1.6 符号

我们的符号或多或少是标准的，但有一些例外。在本节中，我们描述我们的基本符号；更完整的列表出现在第697页。

我们使用 $\mathbf { R }$ 表示实数集，$\mathbf { R } _ { + }$ 表示非负实数集，$\mathbf { R } _ { + + }$ 表示正实数集。实 $n$ 维向量的集合记为 $\mathbf { R } ^ { n }$，实 $m \times n$ 矩阵的集合记为 $\mathbf { R } ^ { m \times n }$。我们用方括号界定向量和矩阵，组件之间用空格分隔。我们使用圆括号从逗号分隔的列表中构造列向量。例如，如果 $a , \ b , \ c \in \mathbf { R }$，我们有

$$
(a, b, c) = \left[ \begin{array}{l} a \\ b \\ c \end{array} \right] = \left[ \begin{array}{l l l} a & b & c \end{array} \right] ^ {T},
$$

这是 $\mathbf { R } ^ { 3 }$ 中的一个元素。符号 1 表示所有分量都为1的向量（维度由上下文决定）。符号 $x _ { i }$ 可以指向量 $x$ 的第 $i$ 个分量，也可以指向量集合或序列 $x _ { 1 } , x _ { 2 } , \dotsc$ 的第 $i$ 个元素。上下文或正文会明确指的是哪一个。

我们使用 $\mathbf { S } ^ { k }$ 表示对称 $k \times k$ 矩阵的集合，$\mathbf { S } _ { + } ^ { k }$ 表示对称半正定 $k \times k$ 矩阵的集合，$\mathbf { S } _ { + + } ^ { k }$ 表示对称正定 $k \times k$ 矩阵的集合。卷曲的不等号 $\succeq$（及其严格形式 $\succ$）用于表示广义不等式：在向量之间，它表示分量不等式；在对称矩阵之间，它表示矩阵不等式。带有下标时，符号 $\preceq _ { K }$（或 $\prec _ { K }$）表示关于锥 $K$ 的广义不等式（在§2.4.1中解释）。

我们描述函数的符号与标准符号略有不同，但我们希望不会引起混淆。我们使用符号 $f : \mathbf { R } ^ { p }  \mathbf { R } ^ { q }$ 表示 $f$ 是定义在 $\mathbf { R } ^ { p }$ 的某个子集上的 $\mathbf { R } ^ { q }$ 值函数，具体来说，是其定义域，我们记为 $\operatorname { d o m } f$。我们可以将我们对符号 $f : \mathbf { R } ^ { p }  \mathbf { R } ^ { q }$ 的使用视为函数类型的声明，就像在计算机语言中一样：$f : \mathbf { R } ^ { p }  \mathbf { R } ^ { q }$ 意味着函数 $f$ 接受一个实 $p$ 维向量作为参数，并返回一个实 $q$ 维向量。集合 $\operatorname { d o m } f$，即函数 $f$ 的定义域，指定了 $\mathbf { R } ^ { p }$ 中使得 $f ( x )$ 有定义的点 $x$ 的子集。例如，我们将对数函数描述为 $\log : \mathbf { R }  \mathbf { R }$，且 $\mathbf { d o m } \log = \mathbf { R } _ { + + }$。符号 $\log : \mathbf { R }  \mathbf { R }$ 意味着对数函数接受并返回一个实数；$\mathbf { d o m } \log = \mathbf { R } _ { + + }$ 意味着对数仅对正数有定义。

我们使用 $\mathbf { R } ^ { n }$ 作为通用的有限维向量空间。我们将遇到其他几个有限维向量空间，例如，具有给定最高次数的变量的多项式空间，或对称 $k \times k$ 矩阵的空间 $\mathbf { S } ^ { k }$。通过为向量空间选择一个基，我们总是可以将其与 $\mathbf { R } ^ { n }$ 等同（其中 $n$ 是其维数），因此，针对向量空间 $\mathbf { R } ^ { n }$ 陈述的通用结果可以应用。我们通常让读者将一般结果或陈述翻译到其他向量空间。例如，任何线性函数 $f : \mathbf { R } ^ { n }  \mathbf { R }$ 可以表示为 $f ( x ) = c ^ { T } x$ 的形式，其中 $c \in \mathbf { R } ^ { \pi }$。对于向量空间 $\mathbf { S } ^ { k }$ 的相应陈述可以通过选择基并翻译得到。这导致以下陈述：任何线性函数 $f : \mathbf { S } ^ { k }  \mathbf { R }$ 可以表示为 $f ( X ) = \mathbf { t r } ( C X )$ 的形式，其中 $C \in \mathbf { S } ^ { k }$。


补充内容：
关于Appendix 2：

### 问题
$$
\begin{aligned}
\min_{x, y} \quad & x^2 - y^2 \\
\text{s.t.} \quad & x^2 + y^2 \leq 1
\end{aligned}
$$
![[数学书/凸优化/附件/Pasted image 20260207223248.png]]
### 1. **几何直观**
- **目标函数** $f(x, y) = x^2 - y^2$ 是一个**双曲抛物面**（马鞍面），沿 $x$ 方向开口向上，沿 $y$ 方向开口向下。
- **约束** $x^2 + y^2 \leq 1$ 是一个**单位圆盘**（凸集）。
- 问题是在单位圆盘上寻找马鞍面的最小值。

---

### 2. **拉格朗日函数法**
引入拉格朗日乘子 $\lambda \geq 0$：
$$
\mathcal{L}(x, y, \lambda) = x^2 - y^2 + \lambda (x^2 + y^2 - 1)
$$

**KKT 条件**：
1. $\frac{\partial \mathcal{L}}{\partial x} = 2x + 2\lambda x = 2x(1 + \lambda) = 0$
2. $\frac{\partial \mathcal{L}}{\partial y} = -2y + 2\lambda y = 2y(-1 + \lambda) = 0$
3. $\lambda \geq 0$
4. $x^2 + y^2 \leq 1$
5. $\lambda (x^2 + y^2 - 1) = 0$（互补松弛条件）

---

### 3. **分情况讨论**
#### **情况 1**：$\lambda = 0$
- 由 (1) 得 $2x = 0 \Rightarrow x = 0$
- 由 (2) 得 $-2y = 0 \Rightarrow y = 0$
- 此时 $x^2 + y^2 = 0 < 1$，满足约束。
- 目标值：$f(0, 0) = 0$

#### **情况 2**：$\lambda > 0$
互补松弛条件要求 $x^2 + y^2 = 1$（约束紧致）。

- 由 (1)：$2x(1 + \lambda) = 0 \Rightarrow x = 0$（因为 $\lambda > 0$ 时 $1 + \lambda \neq 0$）
- 由 (2)：$2y(-1 + \lambda) = 0 \Rightarrow y = 0$ 或 $\lambda = 1$
  - 若 $y = 0$，则 $x^2 + 0^2 = 1 \Rightarrow x = \pm 1$，但 $x = 0$ 矛盾，舍去。
  - 若 $\lambda = 1$，则 (1) 给出 $x = 0$，代入 $x^2 + y^2 = 1$ 得 $y = \pm 1$。

此时解为 $(x, y) = (0, \pm 1)$，目标值 $f(0, \pm 1) = 0^2 - (\pm 1)^2 = -1$。

---

### 4. **比较候选解**
- $(0, 0)$：目标值 $0$
- $(0, 1)$：目标值 $-1$
- $(0, -1)$：目标值 $-1$

**最小值**为 $-1$，在点 $(0, \pm 1)$ 处取得。

---

### 5. **验证**
- 在单位圆边界上，目标函数 $f(x, y) = x^2 - y^2 = x^2 - (1 - x^2) = 2x^2 - 1$。
- 当 $x = 0$ 时，$f = -1$；当 $x = \pm 1$ 时，$f = 1$。
- 在圆盘内部，$f(x, y) \geq -1$ 吗？  
  因为 $x^2 \geq 0$，$y^2 \leq 1$，所以 $f = x^2 - y^2 \geq 0 - 1 = -1$，且等号在 $(0, \pm 1)$ 处成立。

---

### 6. **更一般的解法（半定规划松弛）**
对于一般二次问题，可以写成：
$$
\min_{x} \quad x^T P x \quad \text{s.t.} \quad x^T Q x \leq 1
$$
令 $X = xx^T$，则 $x^T P x = \operatorname{tr}(P X)$，约束变为 $\operatorname{tr}(Q X) \leq 1$，并增加约束 $X \succeq 0$ 和 $\operatorname{rank}(X) = 1$。  
去掉秩约束后得到凸的半定规划松弛，对于这种单约束问题通常是紧的。

---

### 总结
- 这个例子虽然非凸，但通过 **KKT 条件** 可以解析求解。
- 最小值在**约束边界**上取得（$\lambda > 0$）。
- 更一般的二次约束二次规划（QCQP）可以用**半定规划松弛**高效求解。
