---
fontfamily: "libertine"
mainfont: "GFS Artemisa"
title: "General Relativity"
author: [Tae Geun Kim]
date: 2018-08-30
subject: "Markdown"
keywords: [Markdown, Example]
subtitle: "By precise approach"
titlepage: true
...


\newpage\null\thispagestyle{empty}\newpage

# Preliminaries

## Manifolds

### 1. Topological Manifolds

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Def 1.1 \hs Topological Manifolds}]
  A \textit{manifold} $M$ of dimension $n$ is a topological space with the following properties.
  \begin{enumerate}
    \item $M$ is Hausdorff
    \item $M$ is locally Euclidean of dimension $n$
    \item $M$ has a countable basis of open sets
  \end{enumerate}
\end{tcolorbox}

**Why?**

* **Hausdorff** : In Hausdorff space, convergent sequences converge to only one point.
If you want to do calculus, you should need Hausdorff space.

* **Locally Euclidean** : This is the main reason that why we require manifolds.

* **Countable Basis** : We need *partition of unity* to bring many properties of Euclidean space.
For Hausdorff space, existence of partition of unity require *paracompactness*.
And paracompactness follows from *second countability*. It is same as have countable basis.

#### 1.1 Supplement

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Thm 1.1.1 \hs Paracompact $\simeq$ Partition of unity}]
  Let $(X, \tau)$ be a topological space that is $T_1$ (all points are closed). Then the following are equivalent:
  \begin{itemize}
    \item $(X,\tau)$ is paracompact and Hausdorff
    \item Every open cover of $(X, \tau)$ admits a subordinate partition of unity
  \end{itemize}
\end{tcolorbox}

To prove this, we need a wide background knowledge.

\vs

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Def 1.1.2 \hs Hausdorff}]
  Given points $x$ and $y$ of $S$, if $x\neq y$, then there exist open neighborhoods $U$ of $x$ and $V$ of $y$ in $S$
  that are disjoint: such that $U \cap V = \emptyset$.
\end{tcolorbox}

\vs

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Def 1.1.3 \hs Locally finite cover}]
  Let $(X, \tau)$ be a topological space.

  An open cover $\Mbk{U_i \subset X}_{i\in I}$ of $X$ is called \textit{locally finite} if $\forall x \in X$,
  there exists a neighbourhood $U_x \supset \Mbk{x}$ such that it intersects only finitely many elements of the cover,
  hence such that $U_x \cap U_i \neq \emptyset$ for only a finite number of $i\in I$.
\end{tcolorbox}

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Def 1.1.4 \hs Refinement of open covers}]
  Let $(X, \tau)$ be a topological space, and let $\Mbk{U_i \subset X}_{i \in I}$ be a open cover.
  Then a \textit{refinement} of this open cover is a set of open subsets $\Mbk{V_j \subset X}_{j\in J}$
  which is still an open cover in itself and such that for each $j\in J$ there exists an $i \in I$ with $V_j \subset U_i$.
\end{tcolorbox}

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Def 1.1.5 \hs Paracompact topological space}]
  A topological space $(X, \tau)$ is called \textit{paracompact} if every open cover of $X$
  has a refinement by a locally finite open cover.
\end{tcolorbox}

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Def 1.1.6 \hs Partition of unity}]
  Let $(X, \tau)$ be a topological space, and let $\Mbk{U_i \subset X}_{i\in I}$ be an open cover.
  Then a \textit{partition of unity} subordinate to the cover is

  \begin{itemize}
    \item a set $\Mbk{f_i}_{i \in I}$ of continuous functions
    \begin{equation*}
      f_i : X \rightarrow [0, 1]
    \end{equation*}
    (where $[0,1] \subset \mathbb{R}$ is equipped with the subspace topology of the real numbers
    $\mathbb{R}$ regarded as the 1D Euclidean space equipped with its metric topology)
  \end{itemize}
  such that with
  \begin{equation*}
    Supp(f_i) := Cl\Sbk{f_i^{-1}((0,1])}
  \end{equation*}
  denoting the support of $f_i$ (the topological closure of the
  subset of points on which it does not vanish) then

  \begin{enumerate}[1)]
    \item $\underset{i \in I}{\forall} (Supp(f_i) \subset U_i)$
    \item $\Mbk{Supp(f_i) \subset X}_{i\in I}$ is a locally finite cover
    \item $\underset{x \in X}{\forall} \Sbk{\sum_{i \in I}f_i(x) = 1}$
  \end{enumerate}
\end{tcolorbox}

\newpage

![Gaussian Partition of Unity](gaussian_pou.png)

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Prop 1.1.7 \hs Paracompact - Partition of unity}]
  If $(X, \tau)$ is a paracompact topological space, then for every open cover $\Mbk{U_i \subset X}_{i\in I}$
  there is a subordinate partition of unity.
\end{tcolorbox}

Proof will be given later.

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Lem 1.1.8 \hs Natural Refinement}]
  Let $(X, \tau)$ be a topological space, $\Mbk{U_i \subset X}_{i \in I}$ be an open cover
  and $\Sbk{\phi : J \rightarrow I, ~ \Mbk{V_j \subset X}_{j\in J}}$ be a refinement to a locally finite cover.
  Then, for $\Mbk{W_i \subset X}_{i \in I}$ with
  \begin{equation*}
    W_i \equiv \Mbk{\bigcup_{j \in \phi^{-1}(\Mbk{i})} V_j}
  \end{equation*}
  is still a refinement of $\Mbk{U_i \in X}_{i \in I}$ to a locally finite cover.
\end{tcolorbox}

\begin{tcolorbox}[colback=red!5!white,colframe=red!50!white, title=\textbf{Proof for 1.1.8 }]
  First we know, for $V$, $V_j \subset U_{\phi(j)=i}$.
  Conversely, $\forall j \in \phi^{-1}(\Mbk{i}), \; V_j \subset U_i$.
  Thus, $W_i \in \bigcup_{j\in\phi^{-1}(\Mbk{i})} V_j \subset U_i$.
  \newline

  Second, since $\Mbk{V_j \subset X}_{j \in J}$ are locally finite,
  $\exists ~\mathcal{U}_x \supset \Mbk{x}$ and a finite subset $K \subset J$ such that

  \begin{equation*}
    \underset{j \in J \backslash K}{\forall}\Sbk{
      \mathcal{U}_x \cap V_j = \emptyset}
  \end{equation*}

  (locally finite: $\mathcal{U}_x \cap V_j \neq \emptyset$ for just finite number of $j \in J$)

  Then we can get by construction,

  \begin{equation*}
    \underset{i \in I\backslash \phi(K)}{\forall}\Sbk{\mathcal{U}_x \cap W_i = \emptyset}
  \end{equation*}

  Since $\phi(K)$ is still finite, we can find the number of $i$ such that $\mathcal{U}_x \cap W_i = \emptyset$ is also finite.
  (If for $i \in K',~$ $\mathcal{U}_x \cap W_i = \emptyset$ then $K'$ should be subset of $\phi(K)$.)
  \newline

  Therefore $\Mbk{W_i \in X}_{i \in I}$ is locally finite.
\end{tcolorbox}

\vs

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Lem 1.1.9 \hs Shrinking Lemma}]
  Let $X$ be a topological space which is normal and let $\Mbk{U_i \subset X}_{i\in I}$ be a locally finite open cover.
  Assuming the axiom of choice then:
  \newline

  There exists another open cover $\Mbk{V_i \subset X}_{i \in I}$ such that the topological closure
  $Cl(V_i)$ of its elements is contained in the original patches:

  \begin{equation*}
    \underset{i \in I}{\forall}\Sbk{V_i \subset Cl(V_i) \subset U_i}
  \end{equation*}
\end{tcolorbox}

\newpage

Now, suggest some fundamental topological concepts to prove prop 1.1.7.

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Def 1.1.10 \hs Normal Spaces ($\mathbf{T_4}$)}]
  A topological space $X$ is \textit{normal} if for every two closed disjoint subsets $A,B \subset X$, there are neighborhoods $U \supset A$, $~ V \supset B$ such that $U \cap V = \emptyset$.
\end{tcolorbox}

\vs

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Prop 1.1.11 \hs $\mathbf{T_4}$ in terms of topological closure}]
  $X$ is normal iff for all closed subsets $C \subset X$ with open neighborhood $U \supset C$ there exists a smaller open neighborhood $V\supset C$ whose topological closure $Cl(V)$ is still contained in $U$:
  $$ C \subset V \subset Cl(V) \subset U$$
\end{tcolorbox}

\begin{tcolorbox}[colback=white!5!white,colframe=red!50!white, title=\textbf{Proof for Prop 1.1.11 }]
  Suppose that $(X, \tau)$ is $T_4$.
  Consider closed subset $C \subset U$ where $U$ is open neighborhood of $C$. It implies
  $$ C \cap X\backslash U = \emptyset $$
  Since $U$ is open, $X \backslash U$ is closed. Because of normal space, there are open neighborhoods $V,W$ such that $C \subset V$, $~ X\backslash U \subset W$ and $V \cap W = \emptyset$. Because of last term, we can find $V \subset X \backslash W \subset U$.
  Since $X \backslash W$ is closed, we can find next relation :
  $$ C \subset V \subset Cl(V) \subset X \backslash W \subset U$$

  In the other direction, suppose that $\forall$ open neighborhood $U$ of closed subset $C$,
  there are smaller open neighborhood with $C \subset V \subset Cl(V) \subset U$.
  Now, consider disjoint closed subset $C_1, C_2 \subset X$.
  $C_1 \cap C_2 = \emptyset$ implies $C_1 \subset X\backslash C_2$.
  Since $X \backslash C_2$ is open neighborhood of $C_1$, there exists smaller open neighborhood $V$ such that
  $$ C_1 \subset V \subset Cl(V) \subset X \backslash C_2$$
  And it also implies $X\backslash Cl(V)$ is open neighborhood of $C_2$ where $V \cap X\backslash Cl(V) = \emptyset$.

  Therefore $X$ is $T_4$.
\end{tcolorbox}

\newpage

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Def 1.1.12 \hs Urysohn function}]
  Let $X$ be a topological space, and let $A,B \subset$ X be disjoint closed subsets. Then an \textit{Urysohn function} for this situation is a continuous function $$f: X\rightarrow [0,1]$$ to the closed interval equipped with its Euclidean metric topology, such that
  $$ f(A) = \Mbk{0} ~ \text{and} ~ f(B) = \Mbk{1} $$
\end{tcolorbox}

\vs

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Prop 1.1.13 \hs Urysohn's Lemma}]
  Let $X$ be a normal topological space, and let $A, B \subset X$ be two disjoint closed subsets of $X$. Then there exists an \textit{Urysohn function}.
\end{tcolorbox}

This lemma has several **big** applications:

* **Urysohn Metrization Thm**: *If $X$ is a normal space with a countable basis, then we can use the abundance of continuous functions from $X$ to $[0,1]$ to assign numerical coordinates to the points of $X$ and obtain an embedding of $X$ into $\R^{\omega}$. From this we see that every second countable normal space is a metric space.*

* **Tietze Extension Thm**: *Suppose $A$ is a subset of a space $X$ and $f: A \rightarrow [0,1]$ is a continuous function. If $X$ is normal and $A$ is closed in $X$, then we can find a continuous function from $X$ to $[0,1]$ that is an extension of $f$.*

* **Embedding manifolds in $\mathbb{R}^n$**: Using Urysohn's lemma to develop the tool called *partitions of unity*, we can obtain the following theoerem:
  *Each compact $n$-manifold is homeomorphic to a subspace of some $\R^n$.*

Then let's start to prove *Urysohn's lemma*.

\newpage

\begin{tcolorbox}[colback=white!5!white,colframe=red!50!white, title=\textbf{Proof for Urysohn's lemma}]

$(\Leftarrow)$ Suppose $f(A) = \Mbk{0}, ~ f(B) = \Mbk{1}$ for all closed subset $A,B \subset X$.
Then $A \subset f^{-1}\Sbk{[0,\frac{1}{2})}$ and $D \subset f^{-1}\Sbk{(\frac{1}{2}, 1]}$.
We can find these two sets are open and disjoint.\footnote[1]{this will be exercise.} Thus, $X$ is $T_4$.
\newline

$(\Rightarrow)$ Suppose that $X$ is $T_4$ and consider two disjoint closed sets $A,B \subset X$. Claim there is \textit{Urysohn function}. To prove this, we should construct continuous function such that $f(A) = \Mbk{0},~ f(B) = \Mbk{1}$. (Maybe it's a little bit tricky.)

Since $X$ is $T_4$, we can find open neighborhood for any closed subsets of $X$ such that satisfies \textit{prop 1.1.11}. Then we can think next idea :
\newline

Let $\Mbk{U_p}_{p\in [0,1] \cap \mathbb{Q}}$ be a collection of open sets such that

$$ U_1 = X\backslash B, ~ A \subset U_0 \subset Cl(U_0) \subset U_1$$

For convenience, denote $Q = [0,1] \cap \mathbb{Q}$. Since $Q$ is countable, we can enumerate it as

$$ Q = \Mbk{p_n | n\in \mathbb{N}}$$

To be more clear, we are going to define by induction a collection $\Mbk{U_p | p \in Q}$ of open subsets with the property:

$$ p < q ~ \Rightarrow ~ Cl(U_p) \subset U_q$$

By definition of $U_p$, we know above property is satisfied when $p=0,~q=1$. Since $Cl(U_0)$ is also subset of $X$, by \textit{prop 1.1.11}, we can construct $\Mbk{U_p}_{p\in Q}$ completely. Also add some conditions ( $p \in (-\infty,0)\cap \mathbb{Q} ~\Rightarrow~ U_p = \emptyset$, $~ p \in (1, \infty) \cap \mathbb{Q} ~\Rightarrow~ U_p = X$ ), then we can extend our collection to whole $\mathbb{Q}$. Now, we can define new set:

$$ \mathbb{Q}(x) \equiv \Mbk{p\in \mathbb{Q} | x \in U_p}$$

Then we can find $\mathbb{Q}(x)$ has lower bound $0$.\footnote[2]{this will be exercise}
Since $\mathbb{Q}(x)$ has a greatest lower bound, we can define $f: X \rightarrow [0,1]$ by

$$ f(x) = \inf \mathbb{Q}(x) = \inf \Mbk{p \in \mathbb{Q} | x \in U_p}$$

If we show $f$ satisfies ( \textit{\textcircled{1} $0\leq f(x) \leq 1$, \textcircled{2} $f$ is Urysohn function for $A,B$, \newline
\textcircled{3} $x \in Cl(U_p) \Rightarrow f(x) \leq p$, \textcircled{4} $x \notin U_p \Rightarrow f(x) \geq p$, \textcircled{5} $f$ is continuous} ) then proof is complete.

\end{tcolorbox}

\newpage

\begin{tcolorbox}[colback=white!5!white,colframe=red!50!white, title=\textbf{Proof for Urysohn's lemma} (Continued)]

\textcircled{1} $0 \leq f(x) \leq 1$

: It's trivial because of next property :
$$ f(x) =
\begin{cases}
1 & \forall p > 1 \\
\text{can't define} & \forall p < 0
\end{cases}
$$

\textcircled{2} $f$ \textit{is Urysohn function for $A, B$.}

: Since $A \subset U_0$, $~ \forall x \in A,~f(x) = 0$ and $B = X \backslash U_1$, $~\forall x \in B, ~ f(x) = \inf \Mbk{(1,\infty) \cap \mathbb{Q}}= 1$.
\newline

\textcircled{3} \textit{If $x \in Cl(U_p)$, then $f(x) \leq p$}

: Suppose $x \in Cl(U_p)$, then $x \in Cl(U_p) \subset U_q, ~ \forall q \in \mathbb{Q}, \; q > p$.
Thus,
$$(p, \infty) \cap \mathbb{Q} \subset \mathbb{Q}(x) ~\Rightarrow~ \inf \mathbb{Q}(x) \leq p$$

\textcircled{4} \textit{If $x \notin U_p$, then $f(x) \geq p$}

: Suppose $x \notin U_p$, then $x \notin U_q,~ \forall q \leq p$. Thus,
$$ (-\infty, p] \cap \mathbb{Q}(x) = \emptyset ~ \Rightarrow ~ p \leq \inf \mathbb{Q}(x)$$

\textcircled{5} \textit{$f$ is continuous.}

: Suppose $U = (a,b) \in \mathbb{R}$ such that $(a,b) \cap [0,1] \neq \emptyset$.
Claim $f^{-1}(U)$ is open. Suppose $x \in f^{-1}(U)$. It means $f(x) \in U = (a,b)$. Since $U$ is open, there are $p, q \in \mathbb{Q}$ such that $a < p < f(x) < q < b$. By \textcircled{3}, \textcircled{4}, we know $x \in U_q \backslash Cl(U_p)$ and $f(U_q\backslash Cl(U_p)) \subset (a,b)$.\footnote[3]{this will be exercise.}

Thus, we can find $\forall x \in f^{-1}(U)$, there are $p, q \in \mathbb{Q}$ such that $x \in U_q \backslash Cl(U_p) \subset f^{-1}(U)$. Since $U_q \backslash Cl(U_p)$ is open, $f^{-1}(U)$ is open.
Therefore, $f$ is continuous.
\newline

Proof is complete.
\end{tcolorbox}

Now, we can prove *prop 1.1.7*.

# Appendix

## A. Topology

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Def A.1 \hs Topological Space}]

A \textit{topology} on a set $X$ is a subset $\mathcal{T}$ of the power set $\mathcal{P}(X)$ with the following properties:

\begin{enumerate}[1.]
  \item $\emptyset \in \mathcal{T}$ and $X \in \mathcal{T}$
  \item Unions of elements of $\mathcal{T}$ belong to $\mathcal{T}$
  $$ U_i \in \mathcal{T} ~ \text{for all} ~ i \in I~\Longrightarrow ~ \bigcup_{i\in I} U_i \in \mathcal{T}$$
  \item Intersections of finitely many elements of $\mathcal{T}$ belong to $\mathcal{T}$. For finite set $I$,
  $$ U_i \in \mathcal{T} ~ \text{for all} ~ i \in I~\Longrightarrow ~ \bigcap_{i\in I} U_i \in \mathcal{T}$$
\end{enumerate}

A \textit{topological space} is a set $X$ together with a topology $\mathcal{T}$ on $X$. For a topological space $(X, \mathcal{T})$ \textit{open subsets} and their complements \textit{closed subsets} of $X$.

\end{tcolorbox}

\vs

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Example A.2}]
  \begin{enumerate}[1)]
    \item Let $X$ be a set. Then $\mathcal{T} = \Mbk{\emptyset, X}$, is a topology on $X$,
    called the \textit{trivial topology}. This is a smallest topology.
    \item The power set $\mathcal{P}(X)$ of a set $X$, is a topology on $X$,
    called the \textit{discrete topology}. This is a largest topology.
  \end{enumerate}
\end{tcolorbox}

\vs 

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Def A.3 \hs Basis}]
  Let $\mathcal{T}$ be a topology on a set $X$. A subset $\mathcal{B} \subseteq \mathcal{T}$
  is called a \textit{basis} for $\mathcal{T}$ if every element of $\mathcal{T}$ is a union of elements of $\mathcal{B}$.
\end{tcolorbox}

\vs

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Prop A.4 \hs Basis (Comfortable Definition)}]
  A subset $\mathcal{B}$ of a topology $\mathcal{T}$ on a set $X$ is a basis of $\mathcal{T}$
  iff, for every $U \in \mathcal{T}$ and $x \in U$, there is a $V \in \mathcal{B}$ with $x \in V \subseteq U$.
\end{tcolorbox}

Proof is trivial.

\vs

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Def A.5 \hs Neighborhood}]
  Let $X$ be a topological space, $x \in X$. Then $U \subseteq X$ is called a
  \textit{neighborhood} of $x$ when there is an open set $x \in V \subseteq U$.
  We denote by $\mathcal{U}(x)$ the set of all neighborhoods of $x$.
\end{tcolorbox}

\vs

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Def A.6 \hs Neighborhood Basis}]
  Let $X$ be a topological space and $x \in X$. Then we call a subset $\mathcal{B}(x) \subseteq \mathcal{U}(x)$
  a \textit{neighborhood basis} or \textit{local basis} of $x$
  if for every neighborhood $U$ of $x$, there is a $V \in \mathcal{B}(x)$ with $V \subseteq U$.
\end{tcolorbox}

\vs

\begin{tcolorbox}[colback=white!5!white,colframe=white!60!blue, title=\textbf{Def A.7 \hs Countability}]
  Let $X$ be a topological space.
  \begin{itemize}
    \item $X$ satisfies the \textit{first countability axiom} and is called \textit{countable} if every point
    in $X$ admits a countable neighborhood basis.
    \item $X$ satisfies the \textit{second countability axiom} and is called \textit{second countable} if
    the topology of $X$ admits a countable basis.
  \end{itemize}
\end{tcolorbox}

# Reference

\begin{itemize}
\item Ballmann, Werner, and Walker Stern. \textit{Introduction to Geometry and Topology}. Birkh\"auser, 2018.
\end{itemize}