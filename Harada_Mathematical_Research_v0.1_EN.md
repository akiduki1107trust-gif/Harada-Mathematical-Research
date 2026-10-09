# Harada Mathematical Research: Original-Construction Candidates, Spectral Frameworks, and Open Proof Problems

## A Preliminary Technical Disclosure — Version 0.1 (PUBLIC-DISCLOSURE READY WORKING PAPER)

**Author:** **Shigehisa Harada** (原田重壽)  
**Affiliation:** Independent Researcher  
**Draft prepared:** 9 October 2026 (Japan Standard Time)  
**Public disclosure record:** Date and time of the first successful public GitHub commit containing this file (see repository commit history; not the draft date).  
**Repository:** https://github.com/akiduki1107trust-gif/Harada-Mathematical-Research  
**Publication identifier (DOI):** Not assigned in this version  
**Document status:** Research communication, **not peer reviewed**; claims labeled explicitly below.

> **Scope of disclosure.** This report records particular mathematical definitions, operator formulas, construction candidates, intermediate calculations, and proof obligations formulated within an independent research program. It does **not** claim a proof of the Riemann hypothesis, a resolution of P versus NP, a completed physical theory of everything, or a newly established aperiodic monotile. The report documents the state of the author's research at preparation time. It does not establish that any proposed construction is historically first or mathematically correct merely by assigning a name or publication date.

## Abstract

We describe five lines of ongoing mathematical and mathematical-physics research: (i) arithmetic operators associated with prime-power data and localized Weil positivity; (ii) a proposed spectral/regularization program called the *Harada Universal Mandala* (HUM); (iii) spectral-zeta and perturbative questions for the noncommutative harmonic oscillator; (iv) a tentative pair/repair/cut framework (PHR-LTC) for constraint and proof complexity; and (v) a self-similar planar curve defined by a 57-degree, eight-map iterated function system (FS57), together with a separate 8-adic symbolic construction. We give sufficiently explicit formulas to make these research objects identifiable and distinguish standard mathematical identities from proposed new results. Particular finite-dimensional identities and an elementary primitivity calculation are included as reproducible examples. The central links to global positivity, exact spectral special values, universal polynomial-time algorithms, and a single aperiodic monotile remain open. Comparisons with relevant prior publications are provided, but the literature review is not exhaustive. For provenance, cite the version-specific repository commit (and a DOI if later issued), not the document-preparation date.

**Keywords:** explicit formula; Weil positivity; prime powers; spectral operators; spectral zeta; noncommutative harmonic oscillator; proof complexity; iterated function systems; substitution sequences; aperiodic tilings; research provenance.

---

## 1. Statement classification, provenance, and priority

Claims in this communication are classified as follows:

| Label | Meaning in this report |
|---|---|
| **ESTABLISHED / STANDARD** | An elementary identity proved in this report or a result already present in published literature; the relevant origin is distinguished from the current formulation. |
| **INTERNAL PASS — AUDIT PENDING** | Recorded as proved in the author's earlier research notes, but no independently checked complete proof/certified computation is supplied here. This is **not** a claim of refereed validity. |
| **CHECK** | Numerical evidence, partially verified calculation, conditional extension, or incomplete independent audit. |
| **OPEN** | No complete proof, general construction, or unconditional conclusion is available here. |
| **RETRACTED / NO-GO** | A previously proposed statement withdrawn, or an obstruction specific to a clearly delimited model. |

**Priority protocol.** Public access to a specified version can document that specific content's public availability no later than its archived release. A Git commit's author date and committer date are not independent, unalterable timestamps. The actual public-disclosure timestamp is supplied by the successful GitHub commit; a version-specific archive DOI can be added if later issued. **Priority of a conjecture, construction, and proof are distinct**, and none implies an assessment of novelty without searching earlier literature.

**Research provenance.** This account has been assembled from dated research handoff notes, including RH notes through CP-RH-EXT-10CA (9 October 2026), HUM notes (September 2026), NCHO notes (27 September 2026), and FS57 notes (30 September 2026). These notes are summaries, not verbatim exports of all past conversations. AI tools were used for exploration and drafting. Such assistance is not independent verification, peer review, or authorship of a mathematical proof.

## 2. Arithmetic operators and a localized Weil-positivity program

### 2.1. A prime-valuation representation

On finitely supported sequences indexed by positive integers, let $V_p$ be the diagonal prime-valuation operator

$$
V_p|n\rangle=v_p(n)|n\rangle,
\qquad
H_{\mathrm{HBP}}=\sum_{p\ \mathrm{prime}}(\log p)V_p.
$$

For each basis vector, only finitely many summands are nonzero and the fundamental theorem of arithmetic gives

$$
\boxed{H_{\mathrm{HBP}}|n\rangle=(\log n)|n\rangle.}
$$

**Status: ESTABLISHED / STANDARD arithmetic identity.** Its use as an organizing operator within HBP is a research choice, not a proof of RH. Further work concerns von Mangoldt weights, the full explicit formula, and localized positivity operators. Earlier work on Weil's positivity criterion and Li's criterion must be credited [1].

### 2.2. A concrete finite-support operator at $L=\log 3$

Let $L=\log3$, and consider test functions supported in $(-L,L)$. With a fixed choice of Fourier transform and zero-extension convention, write

$$
S_hf(x)=\begin{cases}f(x-h),&x-h\in(-L,L),\\0,&\text{otherwise},\end{cases}
\qquad A_h=\tfrac12(S_h+S_h^*).
$$

Set

$$
\mu_0=\gamma+\frac{\pi}{2}+3\log2+\log\pi,
\qquad
c_n=\frac{2\Lambda(n)}{\sqrt n},
$$

$$
J_L=\sum_{\log n<2L}c_n A_{\log n},
\qquad
Q_L=A_0-\mu_0 I-J_L.
$$

Here $A_0$ denotes the *Archimedean quadratic-form operator*, not the shift $A_h$ evaluated at $h=0$; this overloaded notation is retained from the research notebooks and should be replaced by $A_{\mathrm{arch}}$ in a final formal manuscript. More explicitly, it is associated with the Fourier multiplier

$$
a_0(t)=\operatorname{Re}\psi\!\left(\tfrac14+\tfrac{it}{2}\right)-\psi\!\left(\tfrac14\right),
\qquad
\langle f,A_{\mathrm{arch}}f\rangle=\frac1{2\pi}\int_{\mathbb R}a_0(t)|\widehat f(t)|^2\,dt.
$$

To avoid the notation collision, **henceforth set $Q_L=A_{\mathrm{arch}}-\mu_0I-J_L$**. With strict inequality $\log n<2L=\log9$, the active prime powers are exactly

$$
\boxed{n\in\{2,3,4,5,7,8\};\qquad n=9\text{ is excluded at the boundary}.}
$$

In particular $\Lambda(8)=\log2$, not $3\log2$. The candidate *pole-neutral* subspace is characterized by

$$
\langle f,\cosh(x/2)\rangle=0,
\qquad\langle f,\sinh(x/2)\rangle=0.
$$

The precise equality of the proposed quadratic form with a normalized Weil explicit-formula expression still requires a full domain, constant, boundary, and pole-term audit (**CHECK**). A finite window cannot by itself settle the global criterion.

### 2.3. The unresolved positive-Schur certificate

Decompose the test-function space into a finite Legendre-mode core and an orthogonal tail, write

$$
Q_L=\begin{pmatrix}A&B\\B^*&C\end{pmatrix},
\qquad U=\binom{U_0}{U_1}
$$

where $U$ represents the two pole-neutral constraints. If $C\ge \delta I>0$ with suitable operator domains and bounded cross terms, the constrained KKT operator formally reduces to the Schur block

$$
\mathcal S=
\begin{pmatrix}
A-BC^{-1}B^*&U_0-BC^{-1}U_1\\
U_0^*-U_1^*C^{-1}B^*&-U_1^*C^{-1}U_1
\end{pmatrix}.
$$

A complete proof requires certified bounds on the tail inverse, controlled residuals, and exact inertia on both parity sectors. Past internal experiments suggested a tail lower bound above $0.46$ with 400 modes, but **no independent interval certificate is attached**: **CHECK**. The main task—positivity on the pole-neutral space at $L=\log3$—is **OPEN**, as is uniform extension to all support scales. **The Riemann hypothesis is not proved.**

**Potentially distinctive focus for future comparison:** the specific HBP valuation representation combined with this pole-neutral, energy-weighted finite-core/tail KKT certification architecture. These ingredients must be compared against prior localized Weil operators and numerical proof methods before claiming originality.

## 3. Harada Universal Mandala (HUM): a spectral research program

HUM proposes organizing regularization, spectral geometries, and dimensional reduction within a common mathematical research program. It is **not** presented as an established theory of everything, and the use of spectral-action techniques is not itself new [2].

### 3.1. Bare/regularized distinction

For parameters where the expression converges, a candidate regulated kernel is

$$
\mathcal Z_{\mathrm{reg}}(s;\mu,\tau)
=\frac1{\Gamma(s)}\int_0^\infty t^{s-1}
\sum_n a_n\exp\!\left(-\mu^2t-\frac{\lambda_n}{\tau^2t}\right)dt.
$$

The symbol $a_n$ here denotes spectral weights and must not be confused with the RH Fourier multiplier $a_0(t)$. A proposed finite-part prescription is

$$
S_{10}^{\mathrm{ren}}
=\operatorname{FP}_{s=s_0}\mathcal Z_{\mathrm{reg}}(s;\mu,\tau)+S_{\mathrm{ct}}.
$$

For a fixed term with $\mu,\tau,\lambda_n>0$, the classical Bessel integral yields

$$
\int_0^\infty t^{s-1}e^{-\mu^2t-\lambda_n/(\tau^2t)}dt
=2\left(\frac{\sqrt{\lambda_n}}{\mu\tau}\right)^s
K_s\!\left(\frac{2\mu\sqrt{\lambda_n}}{\tau}\right).
$$

**Status: ESTABLISHED / STANDARD integral identity.** Passing the integral through an infinite sum, performing analytic continuation, and interpreting the finite part as a physical action require additional hypotheses (**CHECK/OPEN**).

### 3.2. Dimensional spectral reduction

Under a specified product geometry and compatible Dirac grading, a possible decomposition is

$$
M_{10}=M_4\times K_6,\qquad
D_{10}=D_4\otimes1+\Gamma_4\otimes D_6.
$$

If $D_6^2\phi_n=\lambda_n\phi_n$, a projected resolvent can have the formal spectral representation

$$
G_4(p;y_0,y_0)=\sum_n\frac{|\phi_n(y_0)|^2}{p^2+\lambda_n}.
$$

An internal zero mode formally generates a $p^{-2}$ contribution. This fact alone does **not** establish a unique gravitational action, reproduce the Standard Model, fix observed parameters, or explain dark energy. In dimension six the unregularized coincident-point sum can be ultraviolet divergent, so the expression requires an appropriate cutoff/renormalization interpretation.

**Distinctive research question (OPEN):** can the finite-part kernel and a controlled sequence of finite spectral geometries be linked to a well-defined 10D-to-4D physical reduction with falsifiable predictions? Earlier HUM schemas lacking explicit $B$-field and dilaton kinetic terms cannot simply be identified with a full heterotic action (**model-specific NO-GO**).

## 4. Noncommutative harmonic oscillator (NCHO)

For $\alpha,\beta>0$ and $\alpha\beta>1$, consider the established family [3,4]

$$
Q_{\alpha,\beta}
=\begin{pmatrix}\alpha&0\\0&\beta\end{pmatrix}
\frac12\left(-\frac{d^2}{dx^2}+x^2\right)
+\begin{pmatrix}0&-1\\1&0\end{pmatrix}
\left(x\frac{d}{dx}+\frac12\right).
$$

The numerical/spectral focus of this research is $Q_{3,2}$, with zeta function $\zeta_Q(s)=\operatorname{Tr}(Q^{-s})$ initially defined in its half-plane of convergence. The Weyl residue recorded in the internal notes is

$$
C_{3,2}=\operatorname{Res}_{s=1}\zeta_{Q_{3,2}}(s)=\frac5{\sqrt{30}}
\qquad\text{(INTERNAL PASS — comparison/audit pending)}.
$$

At the symmetric midpoint $\alpha=\beta=5/2$, the internal notes use a two-sector oscillator decomposition with frequency $\omega=\sqrt{21}/2$ to obtain

$$
\zeta_{Q_0}(-1)=2\omega\,\zeta(-1,1/2)
=\frac{\sqrt{21}}{24}
\qquad\text{(INTERNAL PASS — independent write-up pending)}.
$$

The intended original contribution is **not** meromorphic continuation or the existence of trivial zeros—these were studied by Ichinose and Wakayama [4]. Instead the research asks for a precise Laurent-residue/metaplectic description of perturbative coefficients and, ultimately, an exact or rigorously enclosed value of

$$
D_{3,2}=\operatorname{FP}_{s=1}\zeta_{Q_{3,2}}(s).
$$

For $\alpha=5/2+\delta$, $\beta=5/2-\delta$, the hypothesized bridge studies a second-order perturbation at $s=-1+\varepsilon$, extracting a regularized Laurent residue rather than substituting $s=-1$ into a divergent double series. The values $D_{3,2}\approx1.09374244$ and $\zeta_{Q_{3,2}}(-1)\approx0.1899094$ are **numerical CHECK**, not rigorous enclosures. An earlier claimed value $\zeta_{Q_{3,2}}(-1)\approx0.09495$ is **RETRACTED**. No exact $D_{3,2}$ value is claimed.

## 5. P versus NP: PHR-LTC as a proposed research architecture

The proposed *pair/repair/cut* (PHR-LTC) program investigates whether local repair operations, obstruction/cut certificates, and locally testable structures can be connected through explicit, efficiently checkable combinatorial invariants. Terminology in current notes includes repair-or-cut, semantic-core width, low-degree proof systems, and CFI-type obstructions.

This is **a research agenda, not a new general algorithm or theorem**. A credible mathematical claim requires: a formally specified input domain; precise algorithm or existential statement; soundness and completeness; polynomial running-time and bit complexity; uniformity; and independent performance against worst-case families. The Cook–Levin tradition and known logical obstructions such as Cai–Fürer–Immerman must be taken into account [5,6].

**OPEN:** any theorem establishing the proposed repair/cut dichotomy for arbitrary NP-complete problems with uniform polynomial complexity. This report claims **neither** $\mathrm P=\mathrm{NP}$ **nor** $\mathrm P\ne\mathrm{NP}$.

## 6. FS57: a geometric IFS and a separate symbolic system

### 6.1. Explicit eight-map construction

Let $\theta=57^\circ=19\pi/60$,

$$
s=\frac1{4(1+\cos\theta)},
\qquad
h=\frac{\sin\theta}{4(1+\cos\theta)}.
$$

Put

$$
\begin{aligned}
p_1&=(0,0),&p_2&=(s,0),&p_3&=(1/4,h),\\
p_4&=(1/2-s,0),&p_5&=(1/2,0),&p_6&=(1/2+s,0),\\
p_7&=(3/4,-h),&p_8&=(1-s,0),&p_9&=(1,0).
\end{aligned}
$$

With $\varphi=(0,\theta,-\theta,0,0,-\theta,\theta,0)$, define the planar similarities (identifying $\mathbb R^2$ with $\mathbb C$)

$$
f_i(z)=p_i+s e^{i\varphi_i}z,\quad i=1,\ldots,8,
\qquad K=\bigcup_{i=1}^8 f_i(K).
$$

The specification uniquely determines a compact attractor by the standard contraction-mapping theorem. Properties beyond existence, such as the exact self-embedding rigidity and a relation to a new monotile, require their own proofs. Earlier internal work records proposed rigidity and separation statements as **INTERNAL PASS — AUDIT PENDING**.

### 6.2. An explicit 8-adic symbolic substitution

For every $k\in\mathbb Z$, let $v_8(m)$ be the largest exponent $j\ge0$ such that $8^j\mid m$ (for nonzero integer $m$) and set

$$
x(k)=v_8(7k+1)\bmod2\ \in\{0,1\}.
$$

Elementary modular arithmetic gives

$$
x(8k+r)=\begin{cases}1-x(k),&r=1,\\0,&r\ne1,\end{cases}
\qquad r=0,\ldots,7.
$$

Consequently, the one-sided sequence for $k\ge0$ is compatible with the substitution

$$
\boxed{\sigma(0)=01000000,\qquad\sigma(1)=00000000.}
$$

Its incidence matrix, counting zeros and ones, is

$$
M=\begin{pmatrix}7&8\\1&0\end{pmatrix},
\qquad M^2=\begin{pmatrix}57&56\\7&8\end{pmatrix}>0.
$$

Thus **the substitution is primitive** (**ESTABLISHED / elementary calculation in this report**). Primitivity alone does not prove that the geometric FS57 boundary is an aperiodic monotile or that this symbolic substitution forces a specific matching rule. Those geometric identifications remain **OPEN**.

### 6.3. Aperiodicity claims and prior work

The existence of an aperiodic monotile and of a strictly chiral Spectre family was already established by Smith, Myers, Kaplan, and Goodman-Strauss [7,8]. Fractal substitution tile constructions are also known [9]. The proposed FS57-specific problem is not to rediscover that monotiles exist, but to prove a *particular* compatibility/forcing statement for the 57-degree construction. The September 2026 research checkpoint records an outstanding **FS57–Spectre admissibility** bridge (CP177): one must verify that any edge-curve replacement meets the assumptions of the applicable Spectre theorem, or prove the matching rigidity directly. **No FS57-derived single aperiodic monotile is established in this report.**

## 7. Novelty map: what a later paper would have to prove

| Research line | Pre-existing foundation | Specific content disclosed here | Missing validation |
|---|---|---|---|
| RH/HBP | Weil/Li criteria, explicit formula | prime-valuation operator and fixed-window pole-neutral core/tail KKT target | correct formula normalization; certified positivity; comparison with prior operator formulations |
| HUM | spectral action, heat kernels, KK reductions | named bare/regulated finite-part architecture and common-spectrum research questions | convergence, invariance, physical predictions; differentiation from known spectral action |
| NCHO | noncommutative oscillator and spectral zeta | proposed $s=-1+\varepsilon$ residue/metaplectic route for $Q_{3,2}$ | a new exact identity or proof not already available in literature |
| PHR-LTC | SAT/NP completeness and proof complexity | exploratory repair/cut/obstruction design | formal definitions, worst-case theorem, uniform complexity |
| FS57 | IFS theory, Spectre and fractal substitution tilings | specified 57° attractor and 8-adic symbolic structure | FS57-specific novel rigidity/forcing theorem, proof and exhaustive prior-art check |

**Priority statement, limited to content:** upon its eventual public archiving, the exact equations, formulations, claims and open questions *contained in that released version* will become a dated public record. This report cannot establish a first-in-history discovery merely by its title, and it cannot reserve priority for proofs that have not yet been written.

## 8. Reproducibility and planned release

Before public release, each claim intended to be labeled *proved* should carry (a) an exact statement with hypotheses, (b) a self-contained proof or an identified external theorem, (c) computational source and certified error bounds where necessary, and (d) a completed prior-work audit. Suggested repository layout: `README.md`, `reports/en/`, `reports/ja/`, `RH-HBP/`, `HUM/`, `NCHO/`, `PHR-LTC/`, `FS57/`, `verification/`, and `references/`.

The author should review disclosure scope and licensing before committing. On approval, make an immutable-identifiable GitHub Release (tag e.g. `v0.1`) and, if desired, archive that exact release using Zenodo. Record the actual public release date, immutable revision identifier (commit SHA), version DOI, and any errata. Do not backdate publication. The draft is **not yet published or assigned a DOI**.

## References (selected primary sources; not an exhaustive novelty search)

[1] E. Bombieri and J. C. Lagarias, “Complements to Li's Criterion for the Riemann Hypothesis,” *Journal of Number Theory* **77** (1999), 274–287. https://doi.org/10.1006/jnth.1999.2392.

[2] A. H. Chamseddine and A. Connes, “The Spectral Action Principle,” *Communications in Mathematical Physics* **186** (1997), 731–750. https://doi.org/10.1007/s002200050126.

[3] T. Ichinose and M. Wakayama, “Special Values of the Spectral Zeta Function of the Non-Commutative Harmonic Oscillator and Confluent Heun Equations,” *Kyushu Journal of Mathematics* **59** (2005), 39–100. https://doi.org/10.2206/kyushujm.59.39.

[4] T. Ichinose and M. Wakayama, “On the Spectral Zeta Function for the Noncommutative Harmonic Oscillator,” *Reports on Mathematical Physics* **59** (2007), 421–432. https://doi.org/10.1016/S0034-4877(07)80077-2.

[5] S. A. Cook, “The Complexity of Theorem-Proving Procedures,” *Proceedings of STOC* (1971), 151–158. https://doi.org/10.1145/800157.805047.

[6] J.-Y. Cai, M. Fürer and N. Immerman, “An Optimal Lower Bound on the Number of Variables for Graph Identification,” *Combinatorica* **12** (1992), 389–410. https://doi.org/10.1007/BF01305232.

[7] D. Smith, J. S. Myers, C. S. Kaplan and C. Goodman-Strauss, “An Aperiodic Monotile” (2023). https://arxiv.org/abs/2303.10798.

[8] D. Smith, J. S. Myers, C. S. Kaplan and C. Goodman-Strauss, “A Chiral Aperiodic Monotile” (2023). https://arxiv.org/abs/2305.17743.

[9] N. P. Frank, S. B. G. Webster and M. F. Whittaker, “Fractal Dual Substitution Tilings,” *Journal of Fractal Geometry* **3** (2016), 265–317. https://doi.org/10.4171/JFG/37.

---

**Authorship and review note.** Author: **Shigehisa Harada (原田重壽)**. Developed with AI-assisted drafting and exploratory research support. Mathematical claims have not been independently certified as a group. This document is a **preliminary public-facing technical disclosure**, not a statement of accepted academic results.
