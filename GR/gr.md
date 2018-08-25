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

### 1) Topological Manifolds

\begin{tcolorbox}[colback=white!5!white,colframe=white!75!black, title=\textbf{Def 1.1: } Topological Manifolds]
  A \textit{manifold} $M$ of dimension $n$ is a topological space with the following properties.
  \begin{enumerate}
    \item $M$ is Hausdorff
    \item $M$ is locally Euclidean of dimension $n$
    \item $M$ has a countable basis of open sets
  \end{enumerate}
\end{tcolorbox}

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

