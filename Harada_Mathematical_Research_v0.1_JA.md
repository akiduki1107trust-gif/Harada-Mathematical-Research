# 原田数学研究：独自構成候補・スペクトル的枠組み・未解決の証明課題

## 暫定技術開示報告書 — Version 0.1（公開用作業版・未査読）

**著者：原田重壽（Shigehisa Harada）**  
**所属：独立研究者**  
**草稿作成日：2026年10月9日（日本時間）**  
**公開日時の記録：本ファイルを最初に公開登録したGitHubコミットの日時（草稿作成日とは別）**  
**公開先：** https://github.com/akiduki1107trust-gif/Harada-Mathematical-Research  
**DOI：未取得**  
**状態：未査読・公開用暫定技術報告書**

> **重要な留保**：本書は研究対象の定義、候補構成、具体的数式、中間計算、未解決課題を記録するものである。リーマン予想、P vs NP、万物の理論、FS57単一非周期タイルを解決したとは主張しない。研究資料の記録と、その内容の新規性や数学的正しさの証明は別である。

## 要旨

本技術報告は、原田数学研究の5つの研究線を、公開前の同一時点で識別できる形に整理したものである。(1) 素数冪に基づく算術作用素と局所Weil正値性、(2) 原田普遍的曼荼羅数式（HUM）の正則化・スペクトル研究、(3) 非可換調和振動子のゼータ関数と摂動留数、(4) PHR-LTCによる計算量・証明複雑性の探索、(5) 57度・8写像IFS（FS57）と8進記号力学である。既知の定理と独自の研究対象候補を区別し、証明と数値観測を混同しない。公開後の先行性は、実際に公開した版と日付に対応してのみ主張する。

## 1．判定区分と先行性

| 表記 | 意味 |
|---|---|
| **ESTABLISHED / STANDARD** | 本稿で直接確認できる初等恒等式、または先行文献にある既知の成果。 |
| **INTERNAL PASS — 再監査待ち** | 内部引継ぎ資料で証明済みと記録されたが、本稿に独立検証可能な完全証明がないもの。 |
| **CHECK** | 数値観測、条件付きの計算、独立再検証を要するもの。 |
| **OPEN** | 未証明の問題・必要な一般化・未完成の構成。 |
| **RETRACTED / NO-GO** | 取り下げた旧主張、または限定したモデル内での障害。 |

Gitのコミット日時だけで独立した絶対的な先行性を立証できるわけではない。GitHubで実際に公開した版と、必要に応じてZenodoの版固有DOIを併用する。**草稿作成日と公開日は別**に記録する。最初に構想した時期、公開した時期、証明が完成した時期を区別する。

## 2．リーマン予想・HBP・局所Weil作用素

正整数の標準基底上で

$$
V_p|n\rangle=v_p(n)|n\rangle,\qquad
H_{\mathrm{HBP}}=\sum_p(\log p)V_p
$$

と置けば、素因数分解の一意性から

$$
\boxed{H_{\mathrm{HBP}}|n\rangle=(\log n)|n\rangle}
$$

が従う。これは**既知の算術恒等式の作用素表現**であり、そのままRHの証明ではない。

現在の具体的研究対象は $L=\log3$ の局所的なWeil候補作用素である。ゼロ延長平行移動 $S_h$、その対称化 $A_h=(S_h+S_h^*)/2$ により、

$$
\mu_0=\gamma+\frac\pi2+3\log2+\log\pi,\quad
c_n=\frac{2\Lambda(n)}{\sqrt n},
$$

$$
J_L=\sum_{\log n<2L}c_nA_{\log n},\quad
Q_L=A_{\mathrm{arch}}-\mu_0I-J_L,
$$

$$
\langle f,A_{\mathrm{arch}}f\rangle
=\frac1{2\pi}\int_{\mathbb R}\left[\operatorname{Re}\psi\!\left(\frac14+\frac{it}{2}\right)-\psi\!\left(\frac14\right)\right]|\widehat f(t)|^2dt.
$$

$\log n<\log9$ の**厳密な不等号**を採用するため、対象素数冪は $\{2,3,4,5,7,8\}$ であり、境界 $n=9$ は含まない。$\Lambda(8)=\log2$ に注意する。

pole-neutral制約は

$$
\langle f,\cosh(x/2)\rangle=\langle f,\sinh(x/2)\rangle=0.
$$

Legendre低モードのcoreと無限tailへ分割し、Schur/KKT作用素の慣性指数から正値性を厳密認証することが直近の研究課題である。400モードのtail下界$>0.46$は旧内部記録にあるが**独立の区間証明書が添付されていないためCHECK**。固定窓の正値性、全幅への一般化、RHそのものはいずれも**OPEN**である。既存のWeil/Li正値性条件と比較する[1]。

## 3．原田普遍的曼荼羅数式（HUM）

HUMは統合理論の**候補研究プログラム**であり、完成した万物の理論ではない。スペクトル作用原理自体には既存研究がある[2]。

裸核と正則化核を区別し、条件付きの研究対象として

$$
\mathcal Z_{\mathrm{reg}}(s;\mu,\tau)
=\frac1{\Gamma(s)}\int_0^\infty t^{s-1}\sum_n a_n
\exp\!\left(-\mu^2t-\frac{\lambda_n}{\tau^2t}\right)dt,
$$

$$
S_{10}^{\mathrm{ren}}
=\operatorname{FP}_{s=s_0}\mathcal Z_{\mathrm{reg}}(s;\mu,\tau)+S_{\mathrm{ct}}
$$

を記録する。各項の積分は、正のパラメータの下で既知のBessel積分

$$
\int_0^\infty t^{s-1}e^{-\mu^2t-\lambda/(\tau^2t)}dt
=2\left(\frac{\sqrt\lambda}{\mu\tau}\right)^s K_s\!\left(\frac{2\mu\sqrt\lambda}{\tau}\right)
$$

へ還元できる。ただし無限和と積分の交換、解析接続、物理的解釈には追加証明が必要である。

また条件付きの10次元分解

$$
D_{10}=D_4\otimes1+\Gamma_4\otimes D_6,
\qquad
G_4(p;y_0,y_0)=\sum_n\frac{|\phi_n(y_0)|^2}{p^2+\lambda_n}
$$

を調べる。zero modeは形式的に$1/p^2$を生むが、重力・標準模型・宇宙項の再現が実証されたわけではない。6次元内部空間のcoincident-point和には紫外発散の問題がある。**HUMの完成、物理予測、観測照合はOPEN**。

## 4．非可換調和振動子（NCHO）

既存のNCHO作用素族[3,4]

$$
Q_{\alpha,\beta}
=\begin{pmatrix}\alpha&0\\0&\beta\end{pmatrix}\frac12\left(-\frac{d^2}{dx^2}+x^2\right)
+\begin{pmatrix}0&-1\\1&0\end{pmatrix}\left(x\frac{d}{dx}+\frac12\right)
$$

の $Q_{3,2}$ を主対象とする。内部研究記録では

$$
\operatorname{Res}_{s=1}\zeta_{Q_{3,2}}(s)=\frac5{\sqrt{30}},\qquad
\zeta_{Q_0}(-1)=\frac{\sqrt{21}}{24}\quad(\alpha=\beta=5/2)
$$

をPASSとしているが、既存文献との照合および完全な証明本文の再整理を要する。ゼータの解析接続や自明零点は、既にIchinose–Wakayamaらの研究対象である[3,4]。

新規性を検査する研究課題は、$s=-1+\varepsilon$ でのLaurent留数とmetaplectic/Moyal構造の対応であり、最終量は

$$
D_{3,2}=\operatorname{FP}_{s=1}\zeta_{Q_{3,2}}(s).
$$

内部数値 $D_{3,2}\approx1.09374244$、$\zeta_{Q_{3,2}}(-1)\approx0.1899094$ は**CHECK**。旧値$\zeta(-1)\approx0.09495$は**RETRACTED**。厳密値はOPEN。

## 5．P vs NP：PHR-LTC探索構想

PHR-LTCは、局所repair、障害集合、cut証明、LTCおよび証明複雑性の関連を探索する構想である。任意のNP完全問題に対する一様な多項式時間アルゴリズムは示されていない。正確な定義、最悪ケース実行時間、uniformity、隠れた指数時間、CFI型の難例との比較が必要である[5,6]。

**P=NPおよびP≠NPのいずれも、本稿では証明していない。**

## 6．FS57：57度自己相似曲線と8進系列

$$
\theta=57^\circ=19\pi/60,\quad
s=\frac1{4(1+\cos\theta)},\quad
h=\frac{\sin\theta}{4(1+\cos\theta)}.
$$

$$
\begin{gathered}
p_1=(0,0),\ p_2=(s,0),\ p_3=(1/4,h),\ p_4=(1/2-s,0),\\
p_5=(1/2,0),\ p_6=(1/2+s,0),\ p_7=(3/4,-h),\ p_8=(1-s,0),\ p_9=(1,0),\\
\varphi=(0,\theta,-\theta,0,0,-\theta,\theta,0),\\
f_i(z)=p_i+s e^{i\varphi_i}z,\qquad K=\bigcup_{i=1}^8f_i(K).
\end{gathered}
$$

縮小写像の一般定理により、コンパクトなアトラクタの存在は知られる。FS57固有の自己埋込剛性やタイル対応は追加の証明責務を持つ。

独立の8進記号系として、$v_8$を「8の最大冪が割り切る指数」として

$$
x(k)=v_8(7k+1)\pmod2
$$

を定めると、初等合同式から

$$
x(8k+r)=\begin{cases}1-x(k)&r=1,\\0&r\ne1,\end{cases}
$$

となる。置換

$$
\sigma(0)=01000000,\quad\sigma(1)=00000000,
\quad M=\begin{pmatrix}7&8\\1&0\end{pmatrix},\quad
M^2=\begin{pmatrix}57&56\\7&8\end{pmatrix}>0
$$

ゆえに**この置換の原始性は初等的に確認できる**。ただし、記号列の非周期性や置換の原始性と、「FS57曲線から作った単一タイルが必ず非周期であること」は別問題である。

Smithらのhat/Spectre単一非周期タイル[7,8]や、Frank–Webster–Whittakerのフラクタル置換タイル[9]は既存成果である。FS57由来の曲線がSpectreのedge置換条件を満たすか（CP177）、または独立のmatching rigidityが成立するかは**OPEN**。

## 7．学術的な新規性と優先性を主張するための条件

| 分野 | 現在の具体的な開示対象 | 新規性を確立するために必要なもの |
|---|---|---|
| RH/HBP | 素因数作用素、局所Weil・KKT証明構想 | 先行作用素との厳密比較、正規化の再監査、証明書 |
| HUM | 二層正則化、10D→4Dスペクトル接続 | 既存spectral actionとの差分、収束と物理予測 |
| NCHO | CB-RESIDUE / metaplectic経路 | 既存にない正確な定理と独立証明 |
| PHR-LTC | repair-or-cut設計 | 形式化と全適用範囲での複雑性保証 |
| FS57 | 57°IFSと8進記号構造 | 既存タイルとの差分、剛性・タイル対応の証明 |

実際の公開時には、公開版のコミットSHA、GitHub Release名、版固有DOI（取得した場合）、公開日を記録する。**公開日を草稿作成日に遡らせない。** 未完成の将来の証明の先行性は主張しない。

## 主要参考文献

[1] E. Bombieri and J. C. Lagarias (1999), *Complements to Li's Criterion for the Riemann Hypothesis*, J. Number Theory 77, 274–287. https://doi.org/10.1006/jnth.1999.2392.

[2] A. H. Chamseddine and A. Connes (1997), *The Spectral Action Principle*, Commun. Math. Phys. 186, 731–750. https://doi.org/10.1007/s002200050126.

[3] T. Ichinose and M. Wakayama (2005), *Special Values of the Spectral Zeta Function of the Non-Commutative Harmonic Oscillator and Confluent Heun Equations*, Kyushu J. Math. 59, 39–100. https://doi.org/10.2206/kyushujm.59.39.

[4] T. Ichinose and M. Wakayama (2007), *On the Spectral Zeta Function for the Noncommutative Harmonic Oscillator*, Rep. Math. Phys. 59, 421–432. https://doi.org/10.1016/S0034-4877(07)80077-2.

[5] S. A. Cook (1971), *The Complexity of Theorem-Proving Procedures*, STOC, 151–158. https://doi.org/10.1145/800157.805047.

[6] J.-Y. Cai, M. Fürer and N. Immerman (1992), *An Optimal Lower Bound on the Number of Variables for Graph Identification*, Combinatorica 12, 389–410. https://doi.org/10.1007/BF01305232.

[7] D. Smith et al. (2023), *An Aperiodic Monotile*. https://arxiv.org/abs/2303.10798.

[8] D. Smith et al. (2023), *A Chiral Aperiodic Monotile*. https://arxiv.org/abs/2305.17743.

[9] N. P. Frank, S. B. G. Webster and M. F. Whittaker (2016), *Fractal Dual Substitution Tilings*, J. Fractal Geom. 3, 265–317. https://doi.org/10.4171/JFG/37.

---

**著者：原田重壽（Shigehisa Harada）**。本稿の編集にはAI支援を利用した。外部査読・独立数学監査は未実施。**未査読の暫定技術報告書であり、公開日時は最初のGitHub登録コミットから確認する。DOIは本版では未取得。**
