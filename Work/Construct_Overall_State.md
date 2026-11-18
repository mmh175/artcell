# Construct Overall State — Time-Bin WCP and Density-Matrix Conversation

**Scope:** Chronological archive of this conversation, beginning with the early/late WCP slide and continuing through single-photon and multiphoton Fock states, coherent-state products, density matrices, purity, postselection, and phase randomization.

**Format note:** This is a Markdown study transcript reconstructed from the chat. The mathematical steps and every substantive question and answer are retained; some repeated exposition and interface-only elements are reformatted or consolidated for readability. The original uploaded slide is supplied alongside this file, at `Construct_Overall_State_assets/original_slide.jpeg`. All equations use Markdown-compatible LaTeX. A former interactive quiz is reproduced as ordinary text, with answers in its answer key.

![Original user slide: early and late WCP states](Construct_Overall_State_assets/original_slide.jpeg)

---

## Part I — From early and late coherent states to the combined state

### Exchange 1 — Checking the slide and constructing the overall state

**User:** “This is the slide I made for early and late state from wcp. Check. Now I want to make the overall state that is superposition of early and late.”

**Assistant:** The early-only and late-only WCPs can be represented in the two-mode Fock basis

$$
\mathcal B=\{|0,0\rangle,|1,0\rangle,|0,1\rangle,|2,0\rangle,|1,1\rangle,|0,2\rangle,\ldots\}.
$$

The early-only state is

$$
|\psi_e\rangle=|\alpha\rangle_e\otimes|0\rangle_l
=e^{-|\alpha|^2/2}\begin{pmatrix}
1\\ \alpha\\0\\ \alpha^2/\sqrt2\\0\\0\\\vdots
\end{pmatrix}.
$$

The late-only state is

$$
|\psi_l\rangle=|0\rangle_e\otimes|\alpha\rangle_l
=e^{-|\alpha|^2/2}\begin{pmatrix}
1\\0\\\alpha\\0\\0\\\alpha^2/\sqrt2\\\vdots
\end{pmatrix}.
$$

For a conventional equal-intensity, equal-relative-phase WCP **plus** preparation, the two occupied coherent modes have amplitude $\alpha/\sqrt2$ each, where $\mu=|\alpha|^2$ is the total mean photon number:

$$
\boxed{|\psi_+\rangle=|\alpha/\sqrt2\rangle_e\otimes|\alpha/\sqrt2\rangle_l.}
$$

Its two-mode expansion is

$$
|\psi_+\rangle=e^{-|\alpha|^2/2}
\sum_{n,m=0}^{\infty}
\frac{(\alpha/\sqrt2)^{n+m}}{\sqrt{n!m!}}|n,m\rangle.
$$

Thus, in the slide's ordering,

$$
|\psi_+\rangle=e^{-|\alpha|^2/2}
\begin{pmatrix}
1\\\alpha/\sqrt2\\\alpha/\sqrt2\\
\alpha^2/(2\sqrt2)\\\alpha^2/2\\\alpha^2/(2\sqrt2)\\\vdots
\end{pmatrix}.
$$

The $|1,1\rangle$ component is now present: a pulse pair may contain one photon early and one late. This product of coherent states is *not* the same as the normalized sum of early-only and late-only coherent states.

### Exchange 2 — Explicit tensor product using column vectors

**User:** “can you please show me the tensor product that you did between two states in column vector form?”

**Assistant:** Define $\beta=\alpha/\sqrt2$. The single-mode coherent-state column vectors are

$$
|\beta\rangle_e=e^{-|\beta|^2/2}
\begin{pmatrix}1\\\beta\\\beta^2/\sqrt2\\\beta^3/\sqrt6\\\vdots\end{pmatrix},
\quad
|\beta\rangle_l=e^{-|\beta|^2/2}
\begin{pmatrix}1\\\beta\\\beta^2/\sqrt2\\\beta^3/\sqrt6\\\vdots\end{pmatrix}.
$$

The tensor product is the Kronecker product: multiply each element of the first vector by the *entire* second vector:

$$
\begin{aligned}
|\beta\rangle_e\otimes|\beta\rangle_l
&=e^{-|\beta|^2}
\begin{pmatrix}1\\\beta\\\beta^2/\sqrt2\\\vdots\end{pmatrix}
\otimes
\begin{pmatrix}1\\\beta\\\beta^2/\sqrt2\\\vdots\end{pmatrix}\\
&=e^{-|\beta|^2}
\begin{pmatrix}
1\begin{pmatrix}1\\\beta\\\beta^2/\sqrt2\\\vdots\end{pmatrix}\\[6pt]
\beta\begin{pmatrix}1\\\beta\\\beta^2/\sqrt2\\\vdots\end{pmatrix}\\[6pt]
\frac{\beta^2}{\sqrt2}\begin{pmatrix}1\\\beta\\\beta^2/\sqrt2\\\vdots\end{pmatrix}\\\vdots
\end{pmatrix}.
\end{aligned}
$$

The raw tensor product orders late-mode occupation fastest: $|0,0\rangle,|0,1\rangle,|0,2\rangle,\ldots,|1,0\rangle,\ldots$. Reordering into the user's **total-photon-number** basis gives

$$
e^{-|\alpha|^2/2}
\begin{pmatrix}1\\\alpha/\sqrt2\\\alpha/\sqrt2\\\alpha^2/(2\sqrt2)\\\alpha^2/2\\\alpha^2/(2\sqrt2)\\\vdots\end{pmatrix}.
$$

### Exchange 3 — “There should be a lot of zeros”

**User:** “i think your column states are wronk. check twice. there should be a lot of zeros like the pic uploaded”

**Assistant:** The objection is correct for the **already embedded, two-mode** early-only and late-only state vectors. In the user's basis,

$$
|\psi_e\rangle=e^{-|\alpha|^2/2}
\begin{pmatrix}
1\\\alpha\\0\\\alpha^2/\sqrt2\\0\\0\\\alpha^3/\sqrt6\\0\\0\\0\\\vdots
\end{pmatrix},
\quad
|\psi_l\rangle=e^{-|\alpha|^2/2}
\begin{pmatrix}
1\\0\\\alpha\\0\\0\\\alpha^2/\sqrt2\\0\\0\\0\\\alpha^3/\sqrt6\\\vdots
\end{pmatrix}.
$$

Their many zeros are physically required because the other time bin is vacuum. The equal-amplitude **two-occupied-bin** coherent state, however, contains $|1,1\rangle$, $|2,1\rangle$, $|1,2\rangle$, etc. It has nonzero amplitudes for all nonnegative occupations. To construct it, tensor the two *single-mode* coherent states; do not tensor two vectors that are already in the joint two-mode space.

Through three photons, the corrected vector is

$$
|\psi_+\rangle=e^{-|\alpha|^2/2}
\begin{pmatrix}
1\\ \alpha/\sqrt2\\ \alpha/\sqrt2\\
\alpha^2/(2\sqrt2)\\\alpha^2/2\\\alpha^2/(2\sqrt2)\\
\alpha^3/(4\sqrt3)\\\alpha^3/4\\\alpha^3/4\\\alpha^3/(4\sqrt3)\\\vdots
\end{pmatrix}.
$$

An actual normalized **sum** $\mathcal N(|\alpha,0\rangle+|0,\alpha\rangle)$ would retain zero amplitudes in $|1,1\rangle$, $|2,1\rangle$, etc.; it is a different optical state.

### Exchange 4 — Why addition for $|+\rangle$ but tensor product for WCP?

**User:** “q1: usually, when we do |+> stateor the superposition, we use superposition/sum: |+> = (|0>+|1>)/sqrt2. why we are doing tensor product?”

**Assistant:** For exactly one photon,

$$
|e\rangle=|1,0\rangle,\quad |l\rangle=|0,1\rangle,
$$

and the time-bin qubit is the **sum**

$$
\boxed{|+\rangle=\frac{|1,0\rangle+|0,1\rangle}{\sqrt2}}
=\begin{pmatrix}0\\1/\sqrt2\\1/\sqrt2\\0\\\vdots\end{pmatrix}.
$$

For weak coherent light, early and late are two distinct optical modes with Hilbert space $\mathcal H_e\otimes\mathcal H_l$. The usual equal-amplitude WCP plus preparation is the **product**

$$
|\psi_+\rangle=|\beta\rangle_e\otimes|\beta\rangle_l,
\qquad \beta=\alpha/\sqrt2.
$$

But each $|\beta\rangle$ is itself a *superposition of Fock states*:

$$
|\beta\rangle=e^{-|\beta|^2/2}
\left(|0\rangle+\beta|1\rangle+\frac{\beta^2}{\sqrt2}|2\rangle+\cdots\right).
$$

Grouping the product by total photon number,

$$
\begin{aligned}
|\psi_+\rangle=e^{-\mu/2}\bigg[&|0,0\rangle
+\sqrt{\frac\mu2}(|1,0\rangle+|0,1\rangle)\\
&+\frac\mu{2\sqrt2}(|2,0\rangle+\sqrt2|1,1\rangle+|0,2\rangle)+\cdots\bigg]
\end{aligned}
$$

for real $\alpha=\sqrt\mu$. The normalized one-photon component is exactly $|+\rangle$. Addition and tensor product are both used, but at different levels of description.

The normalized sum of the two original coherent states is instead

$$
\mathcal N(|\alpha,0\rangle+|0,\alpha\rangle),\qquad
\mathcal N=[2(1+e^{-|\alpha|^2})]^{-1/2},
$$

which is a cat-like coherent-state superposition, not an ordinary two-pulse WCP plus state.

### Exchange 5 — Manually multiplying the underlying single-mode states

**User:** “yes, i'll do it later, give me a reminder. but first, can you show manual operation of first few term of the tensor product between early and late state?”

**Assistant:** Take

$$
|\beta\rangle_e=e^{-|\beta|^2/2}
\left(|0\rangle_e+\beta|1\rangle_e+\frac{\beta^2}{\sqrt2}|2\rangle_e+\cdots\right)
$$

and an identical expansion for the late mode. Multiply each early term with each late term:

$$
\begin{array}{lll}
|0\rangle_e\otimes|0\rangle_l=|0,0\rangle,&
|0\rangle_e\otimes\beta|1\rangle_l=\beta|0,1\rangle,&
|0\rangle_e\otimes\frac{\beta^2}{\sqrt2}|2\rangle_l=\frac{\beta^2}{\sqrt2}|0,2\rangle,\\[5pt]
\beta|1\rangle_e\otimes|0\rangle_l=\beta|1,0\rangle,&
\beta|1\rangle_e\otimes\beta|1\rangle_l=\beta^2|1,1\rangle,&
\beta|1\rangle_e\otimes\frac{\beta^2}{\sqrt2}|2\rangle_l=\frac{\beta^3}{\sqrt2}|1,2\rangle,\\[5pt]
\frac{\beta^2}{\sqrt2}|2\rangle_e\otimes|0\rangle_l=\frac{\beta^2}{\sqrt2}|2,0\rangle,&
\frac{\beta^2}{\sqrt2}|2\rangle_e\otimes\beta|1\rangle_l=\frac{\beta^3}{\sqrt2}|2,1\rangle,&
\frac{\beta^2}{\sqrt2}|2\rangle_e\otimes\frac{\beta^2}{\sqrt2}|2\rangle_l=\frac{\beta^4}{2}|2,2\rangle.
\end{array}
$$

Collecting sectors $N=0,1,2$:

$$
|\psi_+\rangle=e^{-|\beta|^2}\left[|0,0\rangle+
\beta(|1,0\rangle+|0,1\rangle)
+\frac{\beta^2}{\sqrt2}|2,0\rangle+\beta^2|1,1\rangle+
\frac{\beta^2}{\sqrt2}|0,2\rangle+\cdots\right].
$$

Its two-mode column is $e^{-|\beta|^2}(1,\beta,\beta,\beta^2/\sqrt2,\beta^2,\beta^2/\sqrt2,\ldots)^T$.

### Exchange 6 — Tensoring the user's two *embedded* column vectors

**User:** “no, I am interested in the manual multiplication between:”

$$
|\psi_e\rangle=e^{-|\alpha|^2/2}
\begin{pmatrix}1\\\alpha\\0\\\alpha^2/\sqrt2\\0\\0\\\vdots\end{pmatrix},
\quad
|\psi_l\rangle=e^{-|\alpha|^2/2}
\begin{pmatrix}1\\0\\\alpha\\0\\0\\\alpha^2/\sqrt2\\\vdots\end{pmatrix}.
$$

**Assistant:** The *literal* Kronecker product is mathematically valid:

$$
|\psi_e\rangle\otimes|\psi_l\rangle=e^{-|\alpha|^2}
\begin{pmatrix}1\\\alpha\\0\\\alpha^2/\sqrt2\\0\\0\\\vdots\end{pmatrix}
\otimes
\begin{pmatrix}1\\0\\\alpha\\0\\0\\\alpha^2/\sqrt2\\\vdots\end{pmatrix}.
$$

Multiply the late vector by each coefficient of the early vector:

$$
1\times\begin{pmatrix}1\\0\\\alpha\\0\\0\\\alpha^2/\sqrt2\\\vdots\end{pmatrix}
=\begin{pmatrix}1\\0\\\alpha\\0\\0\\\alpha^2/\sqrt2\\\vdots\end{pmatrix},
$$

$$
\alpha\times\begin{pmatrix}1\\0\\\alpha\\0\\0\\\alpha^2/\sqrt2\\\vdots\end{pmatrix}
=\begin{pmatrix}\alpha\\0\\\alpha^2\\0\\0\\\alpha^3/\sqrt2\\\vdots\end{pmatrix},
$$

$$
0\times\begin{pmatrix}1\\0\\\alpha\\0\\0\\\alpha^2/\sqrt2\\\vdots\end{pmatrix}=\mathbf 0,
$$

$$
\frac{\alpha^2}{\sqrt2}\times\begin{pmatrix}1\\0\\\alpha\\0\\0\\\alpha^2/\sqrt2\\\vdots\end{pmatrix}
=\begin{pmatrix}\alpha^2/\sqrt2\\0\\\alpha^3/\sqrt2\\0\\0\\\alpha^4/2\\\vdots\end{pmatrix}.
$$

Stacking these blocks gives the Kronecker-product vector. **Physical caveat:** each original vector already lies in $\mathcal H_e\otimes\mathcal H_l$, so their direct Kronecker product lies in $(\mathcal H_e\otimes\mathcal H_l)^{\otimes2}$: it describes **four mode factors**, not the desired two-mode WCP.

### Exchange 7 — Where exactly does $\alpha/\sqrt2$ come from?

**User:** “good. I want a concrete derivation of this $\psi_+$ state about why $\alpha/\sqrt2$ came from”

**Assistant:** Begin with $|\alpha\rangle$ and $\mu=|\alpha|^2$. An ideal lossless 50:50 beam splitter has equal output intensities, so

$$
\mu_e=\mu_l=\frac\mu2,
\qquad
|\alpha_e|^2=|\alpha_l|^2=\frac{|\alpha|^2}{2}.
$$

After choosing or compensating the relative phase,

$$
\boxed{\alpha_e=\alpha_l=\frac\alpha{\sqrt2}.}
$$

Using $\alpha/2$ would give $2|\alpha/2|^2=\mu/2$, incorrectly losing half the original mean photon number.

One creation-operator convention for a balanced splitter is

$$
\hat a^\dagger\longrightarrow\frac{\hat e^\dagger+\hat l^\dagger}{\sqrt2}.
$$

Write the input as

$$
|\alpha\rangle=e^{-|\alpha|^2/2}e^{\alpha\hat a^\dagger}|0\rangle.
$$

At the splitter output,

$$
\begin{aligned}
|\psi_{\rm out}\rangle
&=e^{-|\alpha|^2/2}
\exp\left[\frac\alpha{\sqrt2}(\hat e^\dagger+\hat l^\dagger)\right]|0,0\rangle\\
&=e^{-|\alpha|^2/2}e^{(\alpha/\sqrt2)\hat e^\dagger}e^{(\alpha/\sqrt2)\hat l^\dagger}|0,0\rangle\\
&=\boxed{|\alpha/\sqrt2\rangle_e\otimes|\alpha/\sqrt2\rangle_l}.
\end{aligned}
$$

The exponentials factor because $[\hat e^\dagger,\hat l^\dagger]=0$. Physically the output arms can be mapped to early and late time bins by a delay, with relative optical phase properly controlled. The one-photon component is $e^{-\mu/2}\alpha|+\rangle$.

### Exchange 8 — Can normalization of the two original columns produce $1/\sqrt2$?

**User:** Provided the original two columns again and wrote, “trying to get sqrt2 from these column matrix.”

**Assistant:** If you add the full WCP states, you get

$$
|\psi_e\rangle+|\psi_l\rangle
=e^{-|\alpha|^2/2}
\begin{pmatrix}2\\\alpha\\\alpha\\\alpha^2/\sqrt2\\0\\\alpha^2/\sqrt2\\\vdots\end{pmatrix}.
$$

The vacuum amplitude becomes 2. The coherent states are not orthogonal:

$$
\langle\psi_e|\psi_l\rangle=e^{-|\alpha|^2}.
$$

Thus the normalized sum is

$$
\frac{e^{-|\alpha|^2/2}}{\sqrt{2(1+e^{-|\alpha|^2})}}
\begin{pmatrix}2\\\alpha\\\alpha\\\alpha^2/\sqrt2\\0\\\alpha^2/\sqrt2\\\vdots\end{pmatrix},
$$

**not** the conventional two-bin coherent WCP. On the other hand, within the strictly one-photon subspace, $|1,0\rangle$ and $|0,1\rangle$ are orthogonal, so

$$
\frac1{\sqrt2}\left[
\begin{pmatrix}0\\1\\0\\0\\\vdots\end{pmatrix}+
\begin{pmatrix}0\\0\\1\\0\\\vdots\end{pmatrix}
\right]=
\begin{pmatrix}0\\1/\sqrt2\\1/\sqrt2\\0\\\vdots\end{pmatrix}.
$$

There are *two distinct origins* of $1/\sqrt2$: normalization of orthogonal one-photon basis states, and amplitude splitting at a balanced beam splitter. Directly adding the full coherent-state columns does not generate the latter.

---
## Part II — Hilbert-space dimensions and a 10-question review

### Exchange 9 — Recapping single photons, imperfect sources, and WCPs

**User:** Summarized their understanding: perfect single-photon states as $[1,0]^T$ and $[0,1]^T$ in a two-dimensional time-bin space; plus/minus states from linear addition/subtraction; imperfect sources requiring Fock occupations; and a WCP requiring an infinite-dimensional space and coherent-state probabilities. Asked whether each claim was right and whether the imperfect source's local space was four-dimensional.

**Assistant:** The progression is essentially right, with a distinction between the *logical qubit subspace* and the full *optical-mode Hilbert space*.

For a perfect single-photon time-bin qubit,

$$
|e\rangle=\begin{pmatrix}1\\0\end{pmatrix},\quad
|l\rangle=\begin{pmatrix}0\\1\end{pmatrix},\quad
|\pm\rangle=\frac1{\sqrt2}\begin{pmatrix}1\\\pm1\end{pmatrix}.
$$

These vectors represent the **2D exactly-one-photon subspace**, although their implicit two-mode Fock interpretation is $|e\rangle=|1,0\rangle$ and $|l\rangle=|0,1\rangle$.

If each local mode permits $n=0,1,2$, then each local mode is 3D and their tensor-product space is $3\times3=9$ dimensional. However, if the **total** photon count is at most two, the allowed basis is

$$
\mathcal B_{\le2}=
\{|0,0\rangle,|1,0\rangle,|0,1\rangle,|2,0\rangle,|1,1\rangle,|0,2\rangle\},
$$

which is a **6D** truncated space. If each bin is instead capped at one photon independently, the joint space is 4D, including $|1,1\rangle$. These are *different truncations*.

For WCPs, each mode has a countably infinite Fock basis $|0\rangle,|1\rangle,|2\rangle,\ldots$, and the joint two-mode space is also infinite-dimensional. The coherent state has amplitudes

$$
|\alpha\rangle=e^{-|\alpha|^2/2}\sum_{n=0}^\infty\frac{\alpha^n}{\sqrt{n!}}|n\rangle,
$$

with photon-number probabilities

$$
\boxed{P(n)=e^{-\mu}\frac{\mu^n}{n!},\quad \mu=|\alpha|^2.}
$$

For equal-intensity time bins, the joint number probabilities are

$$
P(n_e,n_l)=e^{-\mu}\frac{(\mu/2)^{n_e+n_l}}{n_e!n_l!}.
$$

At $\mu=0.2$ the probabilities are about $81.87\%$ for $|0,0\rangle$, $8.19\%$ each for $|1,0\rangle$ and $|0,1\rangle$, $0.82\%$ for $|1,1\rangle$, and $0.41\%$ each for $|2,0\rangle$ and $|0,2\rangle$.

An **imperfect single-photon source** need not be a coherent state. It may produce a statistical mixture, e.g.

$$
\rho=P_0|0,0\rangle\langle0,0|+P_1|+\rangle\langle+|+P_2|\psi_2\rangle\langle\psi_2|.
$$

### Exchange 10 — Ten multiple-choice questions and density-matrix study plan

**User:** “1. give me 10 questions of multiple choice 2. yes, I want to move into the density matrix next. one at a time. give me reminder if I forget”

**Assistant:** Provided an interactive 10-question review, later reproduced below in conventional Markdown. Agreed to study density matrices one step at a time and to retain the pending topic of 50:50 beam-splitter coherent-state transformations.

#### Quiz: Time-bin encoding — 10 questions

**Q1.** A perfect single-photon time-bin qubit has basis states $|e\rangle,|l\rangle$. What is the dimension of its logical Hilbert space?

A. 1  
B. 2  
C. 4  
D. Infinite

**Q2.** In basis $\{|e\rangle,|l\rangle\}$, which column vector represents normalized $|-\rangle$?

A. $[1,-1]^T$  
B. $[1/2,-1/2]^T$  
C. $[1/\sqrt2,1/\sqrt2]^T$  
D. $[1/\sqrt2,-1/\sqrt2]^T$

**Q3.** What does the state $|2,1\rangle$ represent, with early occupancy written first?

A. Two early photons and one late photon  
B. One early photon and two late photons  
C. Two possible photons with probability one  
D. A superposition of early and late photons

**Q4.** If each time-bin mode is independently restricted to occupations 0 or 1, what is the dimension of the full joint Hilbert space?

A. 2  
B. 3  
C. 4  
D. 6

**Q5.** If total photon number across the two modes is at most two, how many two-mode Fock basis states are allowed?

A. 4  
B. 6  
C. 8  
D. 9

**Q6.** In the ordered basis $\{|0,0\rangle,|1,0\rangle,|0,1\rangle,|2,0\rangle,|1,1\rangle,|0,2\rangle\}$, which unnormalized column represents $|1,0\rangle+|0,1\rangle$?

A. $[0,1,1,0,0,0]^T$  
B. $[1,1,0,0,0,0]^T$  
C. $[0,1,0,1,0,0]^T$  
D. $[0,0,1,0,1,0]^T$

**Q7.** A coherent pulse with total mean photon number $\mu=0.2$ is split equally into early and late bins. What mean photon number does each have, assuming no loss?

A. 0.05  
B. 0.2  
C. 0.1  
D. $\sqrt{0.2}$

**Q8.** A coherent state has mean photon number $\mu$. What is the probability of detecting exactly zero photons?

A. $1-e^{-\mu}$  
B. $\mu e^{-\mu}$  
C. $e^{-\mu/2}$  
D. $e^{-\mu}$

**Q9.** Consider $|\beta\rangle_e\otimes|-\beta\rangle_l$, $\beta\ne0$. Which normalized time-bin qubit appears upon projection onto exactly one photon?

A. $(|1,0\rangle+|0,1\rangle)/\sqrt2$  
B. $(|1,0\rangle-|0,1\rangle)/\sqrt2$  
C. $(|0,0\rangle-|1,1\rangle)/\sqrt2$  
D. $(|2,0\rangle-|0,2\rangle)/\sqrt2$

**Q10.** If $|\psi_e\rangle=|\alpha\rangle_e\otimes|0\rangle_l$ and $|\psi_l\rangle=|0\rangle_e\otimes|\alpha\rangle_l$, what happens when these already joint-mode states are directly tensor-producted?

A. The ordinary two-mode WCP plus state results  
B. Exactly one photon results  
C. A state in a four-mode tensor-product space results  
D. The normalized sum of early and late results

**Answer key:** 1 **B** (2D logical space); 2 **D** (normalized minus state); 3 **A** ($n_e=2,n_l=1$); 4 **C** ($2\times2=4$); 5 **B** ($1+2+3=6$); 6 **A** (basis entries 2 and 3); 7 **C** ($\mu/2=0.1$); 8 **D** (Poisson vacuum probability); 9 **B** (relative minus sign); 10 **C** (two already two-mode factors tensor into four).

---

## Part III — Building density matrices one step at a time

### Exchange 11 — Density matrix of a pure single-photon $|+\rangle$ state

**User:** “ok move on with density matrix”

**Assistant:** In basis $\{|e\rangle,|l\rangle\}$,

$$
|e\rangle=\begin{pmatrix}1\\0\end{pmatrix},\quad
|l\rangle=\begin{pmatrix}0\\1\end{pmatrix},\quad
|+\rangle=\frac1{\sqrt2}\begin{pmatrix}1\\1\end{pmatrix}.
$$

For any pure state $|\psi\rangle$, the density matrix is the outer product $\rho=|\psi\rangle\langle\psi|$; the bra is the complex-conjugate transpose of the ket. Thus,

$$
\begin{aligned}
\rho_+&=\frac1{\sqrt2}\begin{pmatrix}1\\1\end{pmatrix}
\frac1{\sqrt2}\begin{pmatrix}1&1\end{pmatrix}\\
&=\boxed{\frac12\begin{pmatrix}1&1\\1&1\end{pmatrix}}.
\end{aligned}
$$

The diagonal entries give $P(e)=P(l)=0.5$. The off-diagonal entries represent early–late coherence. The trace is 1; for a pure density matrix, $\rho^2=\rho$.

**Exercise:** Calculate $\rho_-=|-\rangle\langle-|$ for $|-\rangle=(1,-1)^T/\sqrt2$.

### Exchange 12 — Minus-state density matrix

**User:**

```text
1 -1
-1 1
```

**Assistant:** The signs and entries were right, but the factor $1/2$ was missing:

$$
\boxed{\rho_-=\frac12\begin{pmatrix}1&-1\\-1&1\end{pmatrix}.}
$$

The trace is 1. Next, distinguish a pure superposition from a **50:50 statistical mixture**.

For pure $|+\rangle$,

$$
\rho_A=\frac12\begin{pmatrix}1&1\\1&1\end{pmatrix}.
$$

For Alice preparing $|e\rangle$ with probability $1/2$ and $|l\rangle$ with probability $1/2$,

$$
\rho_B=\frac12|e\rangle\langle e|+\frac12|l\rangle\langle l|
=\begin{pmatrix}0.5&0\\0&0.5\end{pmatrix}.
$$

They have identical early/late measurement probabilities, but differ in off-diagonal coherence. In the $X$ basis, the probability of measuring $|+\rangle$ is $P(+)=\langle+|\rho|+\rangle$.

**Exercise:** Find $P_A(+)$ and $P_B(+)$.

### Exchange 13 — $X$-basis probability for the pure state

**User:** “1”

**Assistant:** Correct for Case A: $P_A(+)=1$.

$$
\begin{aligned}
P_A(+)&=\frac1{\sqrt2}(1,1)
\left[\frac12\begin{pmatrix}1&1\\1&1\end{pmatrix}\right]
\frac1{\sqrt2}\begin{pmatrix}1\\1\end{pmatrix}=1.
\end{aligned}
$$

**Next exercise:** Evaluate $P_B(+)$ for $\rho_B=I/2$.

### Exchange 14 — $X$-basis probability for the mixture

**User:** “.5”

**Assistant:** Correct: $P_B(+)=0.5$. The statistical mixture has no $X$-basis preference:

$$
\langle+|\tfrac12I|+\rangle=\tfrac12.
$$

**Next:** Compute purity, $\gamma=\operatorname{Tr}(\rho^2)$, for $\rho_B=I/2$.

### Exchange 15 — Purity of the maximally mixed qubit

**User:** “.5”

**Assistant:** Correct:

$$
\rho_B^2=\frac14 I,\quad
\operatorname{Tr}(\rho_B^2)=\frac14+\frac14=\boxed{0.5}.
$$

For any qubit, purity is between 0.5 (maximally mixed) and 1 (pure).

**Next exercise:** Compute the purity of the partially coherent state

$$
\rho=\frac12\begin{pmatrix}1&0.6\\0.6&1\end{pmatrix}.
$$

### Exchange 16 — Intermediate purity

**User:** “.68”

**Assistant:** Correct. Squaring the matrix:

$$
\rho^2=\frac14\begin{pmatrix}1.36&1.2\\1.2&1.36\end{pmatrix},
\qquad
\boxed{\operatorname{Tr}(\rho^2)=0.68}.
$$

It is mixed but retains nonzero early–late coherence. One ensemble decomposition is

$$
\boxed{\rho=0.8|+\rangle\langle+|+0.2|-\rangle\langle-|.}
$$

**Next exercise:** Compute $P(+)=\langle+|\rho|+\rangle$.

### Exchange 17 — $X$-basis probability with partial coherence

**User:** “.8”

**Assistant:** Correct:

$$
P(+)=\frac14(1,1)\begin{pmatrix}1&0.6\\0.6&1\end{pmatrix}
\begin{pmatrix}1\\1\end{pmatrix}
=\frac{3.2}{4}=\boxed{0.8}.
$$

Next, extend the Hilbert space to include vacuum. Use the 3D basis

$$
\mathcal B=\{|0,0\rangle,|1,0\rangle,|0,1\rangle\}.
$$

The single-photon plus state has vector $(0,1,1)^T/\sqrt2$ and density matrix

$$
\rho_+=\frac12\begin{pmatrix}0&0&0\\0&1&1\\0&1&1\end{pmatrix}.
$$

**Exercise:** A source produces 50% vacuum and 50% single-photon plus state:

$$
\rho=0.5|0,0\rangle\langle0,0|+0.5|+\rangle\langle+|.
$$

Calculate the $3\times3$ matrix.

### Exchange 18 — Vacuum–single-photon mixture

**User:**

```text
.5 0 0
0 .25 .25
0 .25 .25
```

**Assistant:** Exactly correct:

$$
\rho=\boxed{\begin{pmatrix}
0.5&0&0\\0&0.25&0.25\\0&0.25&0.25
\end{pmatrix}}.
$$

The vacuum probability is 0.5, early detection is 0.25, late detection is 0.25, and $\rho_{23}=\rho_{32}=0.25$ expresses coherence within the single-photon sector. The mixture has **no coherence between vacuum and one photon**.

Next, choose a toy source that produces:

- 50% $|0,0\rangle$;
- 30% $|+\rangle$;
- 20% $|2,0\rangle$.

Use the 6D basis $\{|0,0\rangle,|1,0\rangle,|0,1\rangle,|2,0\rangle,|1,1\rangle,|0,2\rangle\}$. The state is

$$
\rho=0.5|0,0\rangle\langle0,0|+0.3|+\rangle\langle+|+0.2|2,0\rangle\langle2,0|.
$$

**Exercise:** Find its six diagonal entries.

### Exchange 19 — Six diagonal entries

**User:** “(.5, .15, .15, .2, 0, 0)”

**Assistant:** Correct. The trace is $0.5+0.15+0.15+0.2=1$. The density matrix is

$$
\rho=\begin{pmatrix}
0.5&0&0&0&0&0\\
0&0.15&?&0&0&0\\
0&?&0.15&0&0&0\\
0&0&0&0.2&0&0\\
0&0&0&0&0&0\\
0&0&0&0&0&0
\end{pmatrix}.
$$

**Next exercise:** Find the off-diagonal entries $\rho_{23}$ and $\rho_{32}$ arising from the 30%-weighted $|+\rangle$ component.

### Exchange 20 — Off-diagonal entries and full 6D toy matrix

**User:** “.15, .15”

**Assistant:** Correct: both equal $0.3/2=0.15$. The complete matrix is

$$
\boxed{
\rho=\begin{pmatrix}
0.5&0&0&0&0&0\\
0&0.15&0.15&0&0&0\\
0&0.15&0.15&0&0&0\\
0&0&0&0.2&0&0\\
0&0&0&0&0&0\\
0&0&0&0&0&0
\end{pmatrix}.}
$$

The full preparation is mixed, but the single-photon block retains early–late coherence.

**Exercise:** Calculate $\operatorname{Tr}(\rho^2)$, remembering the off-diagonal entries.

### Exchange 21 — Purity of the 6D toy matrix

**User:** “.38”

**Assistant:** Correct. For a Hermitian density matrix,

$$
\operatorname{Tr}(\rho^2)=\sum_{i,j}|\rho_{ij}|^2.
$$

Here,

$$
\operatorname{Tr}(\rho^2)=0.5^2+4(0.15)^2+0.2^2
=0.25+0.09+0.04=\boxed{0.38}.
$$

A statistical mixture across photon-number sectors may retain a pure coherent state *inside* one sector. For the one-photon component, condition on one photon:

$$
\rho_{\rm 1ph}=\frac1{0.3}\begin{pmatrix}0.15&0.15\\0.15&0.15\end{pmatrix}.
$$

**Exercise posed:** What is the purity of the resulting conditioned state?

---
## Part IV — Postselection, two-photon states, and mode entanglement

### Exchange 22 — Where did the conditional density matrix come from? Are only one-photon WCP components entangled?

**User:** “Before that: 1. How did you get the conditional density matrix? derived from the previous one or just made up 2. previously, in the made up state, we saw one photon case was entangled |=> but 2 photon case was not- jusst mixed. in real life wcp, are only one photon cases get entangled?”

**Assistant, part 1 — Deriving postselection:** The conditional density matrix comes **directly from the 6D density matrix**, not from an independent assumption.

The projector onto the exactly-one-total-photon subspace is

$$
\boxed{P_1=|1,0\rangle\langle1,0|+|0,1\rangle\langle0,1|}
=\begin{pmatrix}
0&0&0&0&0&0\\
0&1&0&0&0&0\\
0&0&1&0&0&0\\
0&0&0&0&0&0\\
0&0&0&0&0&0\\
0&0&0&0&0&0
\end{pmatrix}.
$$

Apply the projection on both sides:

$$
\tilde\rho_1=P_1\rho P_1
=\begin{pmatrix}
0&0&0&0&0&0\\
0&0.15&0.15&0&0&0\\
0&0.15&0.15&0&0&0\\
0&0&0&0&0&0\\
0&0&0&0&0&0\\
0&0&0&0&0&0
\end{pmatrix}.
$$

Its trace is the probability of obtaining that photon-number outcome:

$$
p_1=\operatorname{Tr}(P_1\rho P_1)=0.3.
$$

After normalization,

$$
\boxed{\rho_{\rm 1ph}=\frac{P_1\rho P_1}{\operatorname{Tr}(P_1\rho P_1)}.}
$$

In the reduced two-state basis $\{|1,0\rangle,|0,1\rangle\}$,

$$
\rho_{\rm 1ph}=\frac1{0.3}\begin{pmatrix}0.15&0.15\\0.15&0.15\end{pmatrix}
=\boxed{\frac12\begin{pmatrix}1&1\\1&1\end{pmatrix}}
=|+\rangle\langle+|.
$$

This projector **does not reveal which time bin** contains the photon and therefore preserves the early/late coherence. A which-bin measurement would not.

**Assistant, part 2 — Are multiphoton states entangled?** No rule says that only single-photon components can have coherent time-bin superposition or early/late *mode entanglement*. In the toy model, the two-photon state was simply chosen to be $|2,0\rangle=|2\rangle_e\otimes|0\rangle_l$, which is separable. That was a pedagogical choice, not a universal fact about WCPs.

The single-photon time-bin state

$$
|+\rangle=\frac{|1,0\rangle+|0,1\rangle}{\sqrt2}
$$

is a coherent superposition and can be described as **single-photon mode entanglement** between early and late subsystems. It is not entanglement between two different photons.

For the WCP plus preparation,

$$
|\psi_+\rangle=|\alpha/\sqrt2\rangle_e\otimes|\alpha/\sqrt2\rangle_l,
$$

the two-photon sector is proportional to

$$
|2,0\rangle+\sqrt2|1,1\rangle+|0,2\rangle.
$$

Its normalized state is

$$
\boxed{|\psi_2\rangle=\frac12|2,0\rangle+\frac1{\sqrt2}|1,1\rangle+\frac12|0,2\rangle.}
$$

In basis $\{|2,0\rangle,|1,1\rangle,|0,2\rangle\}$ this is

$$
|\psi_2\rangle=\begin{pmatrix}1/2\\1/\sqrt2\\1/2\end{pmatrix},
\quad
\frac14+\frac12+\frac14=1.
$$

This fixed-two-photon state is not a product of separate early- and late-mode states, so it is **mode-entangled** in the two-mode description. However, the **full fixed-phase coherent WCP** is a separable product across early and late modes. Projecting onto a fixed *total* photon number changes the state being considered. Also, mode entanglement and accessible entanglement between spatially separated parties are not identical operational resources; phase references and allowed operations matter.

For a phase-randomized WCP (one common randomized optical phase per pair), the photon-number mixture can be expressed as

$$
\boxed{\rho_{\rm WCP}=\sum_{n=0}^\infty P(n)|\psi_n\rangle\langle\psi_n|},
\qquad
P(n)=e^{-\mu}\mu^n/n!.
$$

**Exercise posed:** What is the dimension of the fixed-two-photon space and of the associated density matrix?

### Exchange 23 — Dimension of the two-photon sector

**User:**

```text
3
3x3
```

**Assistant:** Both correct. The fixed-two-photon sector has basis $\{|2,0\rangle,|1,1\rangle,|0,2\rangle\}$, so dimension 3 and density matrix $3\times3$.

To construct the matrix,

$$
\rho_2=|\psi_2\rangle\langle\psi_2|
=\begin{pmatrix}1/2\\1/\sqrt2\\1/2\end{pmatrix}
\begin{pmatrix}1/2&1/\sqrt2&1/2\end{pmatrix}.
$$

**Exercise posed:** Find the first row.

### Exchange 24 — First row of the two-photon density matrix

**User:** “1/4, 1/2sqrt2, 1/4”

**Assistant:** Correct:

$$
\rho_2=\begin{pmatrix}
1/4&1/(2\sqrt2)&1/4\\
?&?&?\\?&?&?
\end{pmatrix}.
$$

**Exercise posed:** Find the second row.

### Exchange 25 — Completing the matrix without another row-by-row exercise

**User:** “i got this. go on next step”

**Assistant:** The completed density matrix is

$$
\boxed{
\rho_2=\begin{pmatrix}
1/4&1/(2\sqrt2)&1/4\\
1/(2\sqrt2)&1/2&1/(2\sqrt2)\\
1/4&1/(2\sqrt2)&1/4
\end{pmatrix}.}
$$

It is pure, so $\operatorname{Tr}(\rho_2^2)=1$. The nonzero off-diagonal entries reflect coherence between the configurations $|2,0\rangle$, $|1,1\rangle$, and $|0,2\rangle$.

For a phase-randomized WCP, the toy probabilities are replaced by Poisson weights:

$$
P(0)=e^{-\mu},\qquad
P(1)=\mu e^{-\mu},\qquad
P(2)=\frac{\mu^2}{2}e^{-\mu}.
$$

The complete density matrix is block diagonal across *total* photon-number sectors:

$$
\boxed{\rho_{\rm WCP}=\sum_{n=0}^\infty P(n)\rho_n,\quad \rho_n=|\psi_n\rangle\langle\psi_n|.}
$$

**Exercise posed:** At $\mu=0.2$, calculate $P(2)=e^{-0.2}(0.2)^2/2!$.

### Exchange 26 — Numerical phase-randomized WCP density matrix

**User:** “go on”

**Assistant:** For $\mu=0.2$,

$$
\begin{aligned}
P(0)&=e^{-0.2}\approx0.818731,\\
P(1)&=0.2e^{-0.2}\approx0.163746,\\
P(2)&=\frac{(0.2)^2}{2}e^{-0.2}\approx0.016375.
\end{aligned}
$$

The probability of three or more photons is about 0.001148, or 0.1148%.

The first three photon-number sector matrices are

$$
\rho_0=(1),\quad
\rho_1=\frac12\begin{pmatrix}1&1\\1&1\end{pmatrix},\quad
\rho_2=\begin{pmatrix}
1/4&1/(2\sqrt2)&1/4\\
1/(2\sqrt2)&1/2&1/(2\sqrt2)\\
1/4&1/(2\sqrt2)&1/4
\end{pmatrix}.
$$

Using $\oplus$ to place these matrices in different *diagonal blocks*:

$$
\rho_{\rm WCP}=P(0)\rho_0\oplus P(1)\rho_1\oplus P(2)\rho_2\oplus\cdots.
$$

The truncated $6\times6$ numerical matrix in basis $\{|0,0\rangle,|1,0\rangle,|0,1\rangle,|2,0\rangle,|1,1\rangle,|0,2\rangle\}$ is

$$
\boxed{
\rho_{\le2}\approx\begin{pmatrix}
.818731&0&0&0&0&0\\
0&.081873&.081873&0&0&0\\
0&.081873&.081873&0&0&0\\
0&0&0&.004094&.005790&.004094\\
0&0&0&.005790&.008187&.005790\\
0&0&0&.004094&.005790&.004094
\end{pmatrix}.}
$$

Its trace is about 0.998852, not exactly 1, because the $N\ge3$ terms were omitted. The matrix has off-diagonal entries **within** fixed-number sectors but zeros **between** different total-number sectors.

**Exercise posed:** If Alice postselects exactly two photons, is the conditional state pure or mixed?

### Exchange 27 — The postselected two-photon state is pure

**User:** “pure”

**Assistant:** Correct. The unnormalized two-photon block is $P(2)\rho_2$, so conditioning and renormalizing yields

$$
\rho_{{\rm conditional},2}
=\frac{P(2)\rho_2}{P(2)}
=\rho_2=|\psi_2\rangle\langle\psi_2|.
$$

Thus $\operatorname{Tr}(\rho_2^2)=1$. The full phase-randomized WCP is mixed across total photon number, but each fixed-number component in this ideal model is pure.

**Next topic introduced:** A fixed-optical-phase WCP has

$$
\rho_{\rm fixed}=|\Psi\rangle\langle\Psi|,
\quad
|\Psi\rangle=|\alpha/\sqrt2\rangle_e\otimes|\alpha/\sqrt2\rangle_l.
$$

Unlike the globally phase-randomized state, it contains coherence *between* different photon-number sectors. The assistant asked whether its complete density matrix is pure or mixed and what its purity is; the user paused to ask what phase randomization means physically.

---
## Part V — Global versus relative phase randomization, and physical hardware

### Exchange 28 — What does global-phase randomization mean, and can hardware control it?

**User:** “before that, I want to better understand what is phase randomization looking at the density matrix. ‘global-phase randomization.’- what does it mean? using hardware- it is something that we can control or depends on the wcp source?”

**Assistant:** It can be deliberately implemented in hardware, although certain source architectures naturally produce random optical phases. For a coherent amplitude,

$$
\alpha=|\alpha|e^{i\phi}.
$$

In the time-bin plus preparation, **common or global optical-phase randomization** means applying the same random optical phase $\phi$ to both early and late coherent amplitudes:

$$
\boxed{|\psi_+(\phi)\rangle
=\left|\frac{\alpha e^{i\phi}}{\sqrt2}\right\rangle_e
\otimes\left|\frac{\alpha e^{i\phi}}{\sqrt2}\right\rangle_l,}
$$

where $\alpha>0$ may now be taken real before applying the phase. Within a given pulse pair,

$$
\Delta\phi=\phi_l-\phi_e=0,
$$

but the common phase is varied randomly from *pair to pair*—ideally uniformly on $[0,2\pi)$. The optical phase $\phi$ is not merely a physically irrelevant overall factor multiplying the entire ket; it changes relative phases between different total-photon-number terms.

To see its effect on a density matrix, truncate the *display* to vacuum and one photon. In basis $\{|0,0\rangle,|1,0\rangle,|0,1\rangle\}$, let $a=\sqrt{\mu/2}$. The vacuum-and-one-photon components of the coherent state are

$$
|\psi(\phi)\rangle_{\le1}
=e^{-\mu/2}\begin{pmatrix}1\\ae^{i\phi}\\ae^{i\phi}\end{pmatrix}.
$$

The corresponding **upper-left block of the full, untruncated density matrix** is

$$
\rho_{\le1}(\phi)
=e^{-\mu}\begin{pmatrix}
1&ae^{-i\phi}&ae^{-i\phi}\\
ae^{i\phi}&a^2&a^2\\
ae^{i\phi}&a^2&a^2
\end{pmatrix}.
$$

Averaging over uniformly distributed common phases gives

$$
\boxed{\bar\rho=\frac1{2\pi}\int_0^{2\pi}\rho(\phi)\,d\phi.}
$$

The integral

$$
\frac1{2\pi}\int_0^{2\pi}e^{i\phi}\,d\phi=0
$$

removes vacuum–one-photon coherence and yields this block:

$$
\boxed{
\bar\rho_{\le1}=e^{-\mu}
\begin{pmatrix}1&0&0\\0&\mu/2&\mu/2\\0&\mu/2&\mu/2\end{pmatrix}.}
$$

The off-diagonal terms between $|1,0\rangle$ and $|0,1\rangle$ are still present because both one-photon amplitudes acquired the *same* phase. More generally, averaging over a uniform common phase removes coherences between different **total** photon numbers, but preserves within-sector relative-phase coherence.

**Experimental implementations discussed:**

1. **Active phase modulation.** A phase modulator (PM) driven by random electronic voltages can apply a chosen common phase to each early–late pair. In a simple linear PM model, $\phi(t)=\pi V(t)/V_\pi$. The PM drive should give both bins of the *same pair* the same common phase while allowing a new phase on successive pairs. Intensity modulators carve or attenuate pulses; delay interferometers create separated time bins with a controlled relative phase.
2. **Intrinsic laser phase randomness.** Certain gain-switched laser sources, if driven sufficiently below threshold between emitted pulses, restart emission from spontaneous noise and can have approximately random phase between pulses. A continuously driven laser does **not** necessarily have independently randomized phases between adjacent pulses. Residual phase correlations depend on the laser and driving regime and need experimental validation.

**QKD relevance:** Standard decoy-state security models often assume globally phase-randomized coherent states so the emitted state is a statistical Poisson mixture

$$
\rho_{\rm WCP}=\sum_{n=0}^{\infty}e^{-\mu}\frac{\mu^n}{n!}|\psi_n\rangle\langle\psi_n|.
$$

Without phase randomization, photon-number coherences remain and this mixture description cannot simply be assumed.

**Exercise posed:** If Alice randomizes the **relative** early–late phase rather than their common optical phase, what happens to $\rho_{12}$ and $\rho_{21}$ of the single-photon plus-state density matrix?

### Exchange 29 — Relative-phase averaging

**User:** “random offdiagonal value <=1”

**Assistant:** Partly right: a changing relative phase changes the *complex off-diagonal values*. For a fixed relative phase $\theta$,

$$
|\psi(\theta)\rangle
=\frac{|1,0\rangle+e^{i\theta}|0,1\rangle}{\sqrt2},
$$

so

$$
\boxed{
\rho(\theta)=\frac12\begin{pmatrix}
1&e^{-i\theta}\\e^{i\theta}&1
\end{pmatrix}.}
$$

For each fixed $\theta$, the magnitude of each off-diagonal term is exactly 0.5; the complex phase rotates. For a **uniformly random** $\theta\in[0,2\pi)$,

$$
\frac1{2\pi}\int_0^{2\pi}e^{\pm i\theta}d\theta=0,
$$

and the average is

$$
\boxed{\rho_{\rm avg}=\frac12\begin{pmatrix}1&0\\0&1\end{pmatrix}.}
$$

This erases early–late single-photon coherence. A *nonuniform* relative-phase distribution can leave an intermediate off-diagonal magnitude between 0 and 0.5.

**Comparison:**

| Operation | Different photon-number sectors | One-photon early–late coherence |
|---|---|---|
| Uniform random **common optical phase** | Cross-sector coherence removed | Preserved if relative phase controlled |
| Uniform random **relative phase** | Does not generally have the same photon-number-diagonalizing effect | Removed |

**Exercise posed:** Instead of uniform continuous randomization, choose $\theta=0$ or $\theta=\pi$ each with 50% probability. What happens to the off-diagonal elements?

### Exchange 30 — Two discrete relative phases

**User:** “0”

**Assistant:** Correct. The two density matrices are

$$
\rho(0)=\frac12\begin{pmatrix}1&1\\1&1\end{pmatrix},\quad
\rho(\pi)=\frac12\begin{pmatrix}1&-1\\-1&1\end{pmatrix}.
$$

Averaging them,

$$
\begin{aligned}
\rho_{\rm avg}&=\frac12\rho(0)+\frac12\rho(\pi)\\
&=\frac14\begin{pmatrix}2&0\\0&2\end{pmatrix}
=\boxed{\begin{pmatrix}0.5&0\\0&0.5\end{pmatrix}}.
\end{aligned}
$$

This is the maximally mixed qubit with purity 0.5. It destroys phase-sensitive $X$-basis interference averaged over many shots.

**Exercise posed:** For $\rho_{\rm avg}=I/2$, what is $P(+)=\langle+|\rho_{\rm avg}|+\rangle$ when Bob measures in the $X$ basis?

### Exchange 31 — Measurement with randomized relative phase

**User:** “.5”

**Assistant:** Correct:

$$
P(+)=\frac1{\sqrt2}(1,1)
\left(\frac12\begin{pmatrix}1&0\\0&1\end{pmatrix}\right)
\frac1{\sqrt2}\begin{pmatrix}1\\1\end{pmatrix}
=\boxed{0.5}.
$$

The ideal $X$-basis outcome probabilities are:

| Preparation | $P(+)$ | $P(-)$ |
|---|---:|---:|
| Pure $|+\rangle$ | 1 | 0 |
| Pure $|-\rangle$ | 0 | 1 |
| Uniformly randomized relative phase | 0.5 | 0.5 |

Thus uniform relative-phase averaging eliminates average interference contrast. Common optical-phase randomization does **not** destroy relative early–late coherence within each photon-number sector.

The next comparison, not yet answered when this archive was requested, was:

**Case A (fixed optical phase):**

$$
\rho_A=|\Psi\rangle\langle\Psi|,
\quad |\Psi\rangle=|\alpha/\sqrt2\rangle_e\otimes|\alpha/\sqrt2\rangle_l.
$$

**Case B (uniform common phase randomization):**

$$
\rho_B=\sum_{n=0}^\infty P(n)|\psi_n\rangle\langle\psi_n|.
$$

Both preparations have the same Poisson photon-number probabilities, but the second lacks coherence *between total photon-number sectors*. The open question was: **Which state is pure, A or B, and what is its purity $\operatorname{Tr}(\rho^2)$?**

### Exchange 32 — Request to archive this conversation

**User:** “before that, can you make a .md file for the entire conversation of Construct Overall State?”

**Assistant:** Prepared this Markdown archive, including the early/late WCP slide, mathematical derivations, the ten-question quiz, step-by-step exercises, and the pending next question.

---

## Where to resume

We were at the comparison between a **fixed-phase coherent WCP** and an **ensemble with uniformly randomized common optical phase**, with the question:

> Which state is pure, and what is $\operatorname{Tr}(\rho^2)$ for the pure one?

Other pending study topic from an earlier exchange:

> Derive experimentally why a 50:50 beam splitter transforms a coherent-state input and vacuum into a **tensor product of coherent outputs**, rather than a superposition of two early-only / late-only coherent states.

### Quick reference: recurring notation

| Symbol | Meaning |
|---|---|
| $|n_e,n_l\rangle$ | $n_e$ photons in early bin, $n_l$ photons in late bin |
| $|e\rangle=|1,0\rangle$ | Single early photon |
| $|l\rangle=|0,1\rangle$ | Single late photon |
| $|\pm\rangle=(|1,0\rangle\pm|0,1\rangle)/\sqrt2$ | Single-photon time-bin qubit $X$ basis |
| $\alpha$ | Complex coherent amplitude |
| $\mu=|\alpha|^2$ | Mean total photon number |
| $\beta=\alpha/\sqrt2$ | Coherent amplitude per time bin in ideal equal splitting |
| $\rho=|\psi\rangle\langle\psi|$ | Pure-state density matrix |
| $\rho=\sum_i p_i|\psi_i\rangle\langle\psi_i|$ | Statistical mixture density matrix |
| $\operatorname{Tr}(\rho^2)$ | Purity |
| $P_n$ | Projector onto exactly $n$ total photons |
| $P(n)=e^{-\mu}\mu^n/n!$ | Poisson photon-number distribution |

*End of archive.*
