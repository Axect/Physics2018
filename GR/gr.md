---
title: "General Relativity"
author: [Tae Geun Kim]
date: 2018-08-24
subject: "Markdown"
keywords: [Markdown, Example]
subtitle: "By precise approach"
titlepage: true
...


\newpage\null\thispagestyle{empty}\newpage

# Preliminaries

## Manifolds

### 1. Topological Manifolds

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Def 1.1 } Topological Manifolds]
  A \textit{manifold} $M$ of dimension $n$ is a topological space with the following properties.
  \begin{enumerate}
    \item $M$ is Hausdorff
    \item $M$ is locally Euclidean of dimension $n$
    \item $M$ has a countable basis of open sets
  \end{enumerate}
\end{tcolorbox}

**Why?**

* Hausdorff : In Hausdorff space, convergent sequences converge to only one point.
If you want to do calculus, you should need Hausdorff space.

* Locally Euclidean : This is the main reason that why we require manifolds.

* Countable Basis : We need **partition of unity** to bring many properties of Euclidean space.
For Hausdorff space, existence of partition of unity require **paracompactness**.
And paracompactness follows from **second countability**. It is same as have countable basis.

#### 1.1 Supplement

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Thm 1.1.1 } Paracompact $\simeq$ Partition of unity]
  Let $(X, \tau)$ be a topological space that is $T_1$ (all points are closed). Then the following are equivalent:
  \begin{enumerate}[I.]
    \item $(X,\tau)$ is paracompact and Hausdorff
    \item Every open cover of $(X, \tau)$ admits a subordinate partition of unity
  \end{enumerate}
\end{tcolorbox}

To prove this, we need a wide background knowledge.

\vs

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Def 1.1.2 } Hausdorff]
  Given points $x$ and $y$ of $S$, if $x\neq y$, then there exist open neighborhoods $U$ of $x$ and $V$ of $y$ in $S$
  that are disjoint: such that $U \cap V = \emptyset$.
\end{tcolorbox}

\vs

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Def 1.1.3 } Locally finite cover]
  Let $(X, \tau)$ be a topological space.

  An open cover $\Mbk{U_i \subset X}_{i\in I}$ of $X$ is called \textit{locally finite} if $\forall x \in X$,
  there exists a neighbourhood $U_x \supset \Mbk{x}$ such that it intersects only finitely many elements of the cover,
  hence such that $U_x \cap U_i \neq \emptyset$ for only a finite number of $i\in I$.
\end{tcolorbox}

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Def 1.1.4 } Refinement of open covers]
  Let $(X, \tau)$ be a topological space, and let $\Mbk{U_i \subset X}_{i \in I}$ be a open cover.
  Then a \textit{refinement} of this open cover is a set of open subsets $\Mbk{V_j \subset X}_{j\in J}$
  which is still an open cover in itself and such that for each $j\in J$ there exists an $i \in I$ with $V_j \subset U_i$.
\end{tcolorbox}

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Def 1.1.5 } Paracompact topological space]
  A topological space $(X, \tau)$ is called \textit{paracompact} if every open cover of $X$
  has a refinement by a locally finite open cover.
\end{tcolorbox}

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Def 1.1.6 } Partition of unity]
  Let $(X, \tau)$ be a topological space, and let ${U_i \subset X}_{i\in I}$ be an open cover.
  Then a \textit{partition of unity} subordinate to the cover is

  \begin{itemize}
    \item a set $\Mbk{f_i}_{i \in I}$ of continuous functions
    \begin{equation*}
      f_i : X \rightarrow [0, 1]
    \end{equation*}
  \end{itemize}
\end{tcolorbox}

\pagebreak

### 2) Differentiable Manifolds

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Def 2.1: } $C^\infty$ - Compatible]
  We say $U, \varphi$ and $V, \psi$ are $C^\infty$\textit{-compatible} if $U \cap V$ nonempty implies
  $\varphi \circ \psi^{-1}$ and $\psi \circ \varphi^{-1}$ to be \textit{diffeomorphisms} of the open subsets
  $\varphi(U\cap V)$ and $\psi(U \cap V)$ of $\R^n$.
\end{tcolorbox}

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Def 2.2: } Differentiable Structure]
  A \textit{differentiable or $C^\infty$ (or smooth) structure} on a topological manifold $M$ is a family
  $\mathcal{U} = \Mbk{U_\alpha, \varphi_\alpha}$ of coordinate neighborhoods such that

  \begin{enumerate}
    \item the $U_\alpha$ cover $M$,
    \item $\forall \alpha,\beta$ the neighborhoods $U_\alpha, \varphi_\alpha$ and $U_\beta, \varphi_\beta$ are $C^\infty$-compatible,
    \item any coordinate neighborhood $V,\psi$ compatible with every $U_\alpha, \varphi_\alpha \in \mathcal{U}$ is itself in $\mathcal{U}$
  \end{enumerate}
\end{tcolorbox}

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Def 2.3: } Differentiable Manifold]
  A $C^\infty$ \textit{manifold} is a topological manifold together with a $C^\infty$ -differentiable structure.
\end{tcolorbox}

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Thm 2.4: } Uniqueness with Hausdorff]
  Let $M$ be a Hausdorff space with a countable basis of open sets. If $\Mbk{V_\beta, \psi_\beta}$ is a covering
  of $M$ by $C^\infty$-compatible coordinate neighborhoods, then there is a unique $C^\infty$ structure on $M$ containing
  these coordinate neighborhoods.
\end{tcolorbox}

### 3) Lie Group

We know $\mathbb{R}^n$ is $C^\infty$-manifold & Abelian group with component-wise addition as group operation.
And we can find next two maps are differentiable :

$$
\begin{gathered}
  (x,y) \rightarrow x + y \\
  x \rightarrow -x
\end{gathered}
$$

Then we can generalize these facts.

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Def 3.1: } Lie Group]
  $G$ is a Lie group provided that the mapping of $G \times G \rightarrow G$ defined by $(x,y) \mapsto x \cdot y$
  where $\cdot$ is group operation of $G$  and the mapping of $G\rightarrow G$ defined by $x \mapsto x^{-1}$ are both $C^\infty$ mappings.
\end{tcolorbox}

### 3) Vector Field and One parameter group

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Def 2.1: } Vector Field]
  A Vector field $X$ on $M$ is a function assigning to each point $p$ of $M$ a vector $X_p \in T_p(M)$

  \begin{equation*}
    X: M \rightarrow T(M) = \bigcup_{p\in M} T_p(M)
  \end{equation*}
\end{tcolorbox}

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Def 2.2:} One Parameter Group]




# 2. Differentiation

## 2.1 Tensor fields and congruences

### 1) Supplement for Vector

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Def 1.1: } Tangent Space]
  We define the \textit{tangentspace} $T_p(M)$ to be the set of all mappings $X_p: C^\infty(p) \rightarrow \mathbb{R}$ satisfying the two conditions
  \begin{enumerate}
    \item
    \item
  \end{enumerate}
  with the vector space operations in $T_p(M)$ defined by
  \begin{enumerate}
    \item
    \item
  \end{enumerate}
\end{tcolorbox}

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Thm 1.2}]
  Let $F: M \rightarrow N$ be a $C^\infty$ map of manifolds for $p \in M$.
  Then there are two homomorphisms such that
  \begin{align*}
    F^*&: \HS \text{ defined by } F^*(f) =  \\
    F_*&: \HS \text{ defined by } F_*(X_p)f =
  \end{align*}
  When $F: M \rightarrow M$ is identity then $F^*, F_*$ are isomorphism.
\end{tcolorbox}

\textit{\underline{pf}}

\pagebreak

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Cor 1.4}]
  If $F: M \rightarrow N$ is a diffeomorphism of $M$ onto an open set $U \subset N$
  and $p \in M$, then $F_*: T_p(M) \rightarrow T_{F(p)}(N)$ is an isomorphism onto.
\end{tcolorbox}

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Note: } Coordinate reps of vector]
  \begin{align*}
    X_pf &= \frac{d}{dt}\Bbk{f \circ \gamma (t)} \\
         &= \\
         &=
  \end{align*}

  Since we know $F_*(u)f = u(f\circ F)$,

  \begin{equation*}
    \frac{\partial}{\partial x^i}(f\circ \varphi^{-1}) =
  \end{equation*}

  Therefore

  \begin{equation*}
    \therefore ~ X_p = X_p^i E_{ip}
  \end{equation*}
\end{tcolorbox}

\pagebreak
