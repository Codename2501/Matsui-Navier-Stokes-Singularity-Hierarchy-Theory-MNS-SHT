# 松井・ナビエ・ストークス特異点階層理論（MNS-SHT）

## *絶対仕様書（第3版、完全版）*

---

## I. 基本設定（松井NSシステム）

基本方程式は、松井型NSタイプ2/3の基礎として、古典的な非圧縮性ナビエ・ストークス方程式を採用している：

$$
\frac{\partial \boldsymbol{u}}{\partial t} - \nu \Delta \boldsymbol{u} + (\boldsymbol{u} \cdot \nabla)\boldsymbol{u} + \nabla p = \boldsymbol{f}, \quad \nabla \cdot \boldsymbol{u} = 0
$$

- **初期条件と外力：**

$$
\boldsymbol{u}(0,\cdot) \in H^1(\Omega) \cap L^\infty(\Omega)
$$

$$
\boldsymbol{f} \in L_{\text{loc}}^2([0,T); H^1(\Omega))
$$

- **特異点候補：**

$$
(T,\boldsymbol{x}^*) \in (0,\infty) \times \Omega
$$

- **局所領域：**

$$
B_r(\boldsymbol{x}^{\*}) = \{ \boldsymbol{x} \in \Omega \mid |\boldsymbol{x} - \boldsymbol{x}^{\*}| < r \}
$$

---

## II. 特異点形成層

### 1. 弱い爆発条件と単調性エネルギー評価（無振動補題）

高周波振動によって引き起こされるゴースト特異点を排除するために、弱い爆発条件に単調性エネルギーの下限（単調性エネルギー推定値）が課せられる：

$$
\limsup_{t \uparrow T} \|\nabla \boldsymbol{u}(t,\cdot)\|_{L^p(B_r(\boldsymbol{x}^*))} = \infty \quad (p > 3)
$$

$$
\limsup_{t \uparrow T} \|\boldsymbol{\omega}(t,\cdot)\|_{L^q(B_r(\boldsymbol{x}^*))} = \infty \quad \left(q > \frac{3}{2}\right)
$$

> **[補題 2.1：単調性／無振動補題]**  
> 任意の $t_1 < t_2 < T$ に対し、定数 $C_{\text{mon}} > 0$ および $0 < \delta < 1$ が存在し、局所的なエネルギー散逸率が次の単調増加評価を満たす：
>
> $$
> \int_{t_1}^{t_2} \|\nabla \boldsymbol{u}(\tau,\cdot)\|_{L^2(B_r(\boldsymbol{x}^*))}^2 \, d\tau \ge C_{\text{mon}} (T - t_2)^{-\delta} \left( 1 - \frac{T - t_2}{T - t_1} \right)
> $$
>
> これは、無限に振動する解によって引き起こされる決定論的層への擬似遷移を数学的に排除し、以下の等式を代数的に強制する：
>
> $$
> \limsup_{t \uparrow T} = \lim_{t \uparrow T} = \infty
> $$

### 2. 一般化された自己相似プロファイル

$$
\boldsymbol{y} = (T-t)^{-\gamma} (\boldsymbol{x} - \boldsymbol{x}^*)
$$

$$
\boldsymbol{u}(t,\boldsymbol{x}) = (T-t)^{-\beta} \boldsymbol{U}(\boldsymbol{y})
$$

- **ルレイ尺度（標準次元解析）：**

$$
\beta = \gamma = \frac{1}{2}
$$

- **松井の強発散スケーリング（階層生成モデル）：**

$$
\beta = \gamma = 1
$$

---

## III. 5種類の特異点の分岐とグリッド補正閾値

### 1. 5種類の特異点タイプの厳密な分類とタイプ固有のスケーリング指数

候補特異点における局所場の崩壊/崩壊モードに応じて、グリッド解像度 $h$ 依存指数は以下のように分岐定義される：

1. **渦特異点 ($S_{\text{vortex}}$)：**

$$
\lim_{t \uparrow T} \|\boldsymbol{\omega}(t,\cdot)\|_{L^q(B_r(\boldsymbol{x}^*))} = \infty \quad \left(q > \frac{2}{3}\right)
$$

$$
\alpha_{\text{vortex}} = 2\gamma - \frac{3}{q} + 1
$$

2. **シャープ特異点 ($S_{\text{sharp}}$)：**

$$
\lim_{t \uparrow T} \|\nabla \boldsymbol{u}(t,\cdot)\|_{L^p(B_r(\boldsymbol{x}^{\*}))} = \infty \quad (p > 3)
$$

$$
\alpha_{\text{sharp}} = 2\beta + 2\gamma - 1 - \frac{6}{p}
$$

3. **ブレイク特異点 ($S_{\text{break}}$)：**

$$
\lim_{t \uparrow T} \left( \sup_{\boldsymbol{x}, \boldsymbol{y} \in B_r(\boldsymbol{x}^*), \boldsymbol{x} \neq \boldsymbol{y}} \frac{|\boldsymbol{u}(t,\boldsymbol{x}) - \boldsymbol{u}(t,\boldsymbol{y})|}{|\boldsymbol{x}-\boldsymbol{y}|} \right) = \infty
$$

$$
\alpha_{\text{break}} = \beta + \gamma
$$

4. **ジャンプ特異点 ($S_{\text{jump}}$)：**

$$
\text{片側限界解離: } |\boldsymbol{u}^+(t,\boldsymbol{x}^{\*}) - \boldsymbol{u}^-(t,\boldsymbol{x}^{\*})| > 0
$$

$$
\alpha_{\text{jump}} = 1.0
$$

> **[補題 3.1：粘性衝撃層補題 ($S_{\text{jump}}$)]**  
> ジャンプ特異点 $S_{\text{jump}}$ の不連続面 $\Sigma$ において、粘性 $\nu > 0$ の存在により解がディラック $\delta'$ 分布特異点を示すのが防がれる。代わりに、以下の厚みを持つ滑らかな粘性衝撃層を形成する：
>
> $$
> \delta_{\text{shock}} \sim \frac{\nu}{|\boldsymbol{u}^+ - \boldsymbol{u}^-|}
> $$
>
> 引き戻された空間 $(\tau, \boldsymbol{\xi})$ において、粘性項 $\tilde{\nu} \Delta_{\boldsymbol{\xi}} \boldsymbol{\Phi}$ は局所的に有界であり（$C^\infty$ 正則化）、ランキン・ユゴニオのジャンプ条件の粘性版（バーガース・NS連続性条件）を厳密に満たす。

5. **レイヤー特異点 ($S_{\text{layer}}$)：**

$$
\alpha_{\text{layer}} = \max_k \{ \alpha_k \} + \eta \quad (\eta > 0)
$$

### 2. 離散決定論的関数とタイプ固有の閾値

$$
\mathcal{D}_h [\boldsymbol{u}](t) = \int_0^t \left( \|\boldsymbol{\omega}(\tau,\cdot)\|_{L^\infty(B_r(\boldsymbol{x}^*))} + \|\nabla \boldsymbol{u}(\tau,\cdot)\|_{L^p(B_r(\boldsymbol{x}^*))}^2 \right) d\tau
$$

- **決定論的基準：**

$$
\lim_{t \uparrow T} \mathcal{D}_h [\boldsymbol{u}](t) \ge C_{\text{crit}, k}(h)
$$

$$
C_{\text{crit}, k}(h) = C_{0, k} \cdot \left(\frac{h}{L_0}\right)^{-\alpha_k} \quad (C_{0, k} > 0)
$$

---

## IV. 特異点決定論的層と幾何学的引き戻し構造

### 1. 微分形式プルバックマップによる動的階層型リフティングオペレーター

時空微分同相写像 $\psi_\tau: (\tau, \boldsymbol{\xi}) \mapsto (t, \boldsymbol{x})$：

$$
\tau(t) = -\ln(T-t)
$$

$$
\boldsymbol{\xi}(t,\boldsymbol{x}) = (T-t)^{-\gamma} (\boldsymbol{x} - \boldsymbol{x}^*)
$$

階層フィールド $\boldsymbol{\Phi}(\tau, \boldsymbol{\xi})$ は 1-形式速度場 $\boldsymbol{\alpha}_{\boldsymbol{u}} = u_i dx^i$ の微分形式プルバック $\psi_\tau^*$ として定義される：

$$
\boldsymbol{\Phi}(\tau, \boldsymbol{\xi}) = \mathcal{L}[\boldsymbol{u}](t,\boldsymbol{x}) \equiv e^{\beta \tau} \cdot \psi_\tau^* (\boldsymbol{u}(t,\boldsymbol{x}))
$$

$$
\boldsymbol{\Phi}(\tau, \boldsymbol{\xi}) = e^{(\beta - \gamma)\tau} \boldsymbol{u}\left(T - e^{-\tau}, \, \boldsymbol{x}^* + e^{-\gamma \tau} \boldsymbol{\xi}\right)
$$

### 2. 階層的偏微分方程式、遠方場圧力減衰、および不可逆エントロピー生成

階層場 $\boldsymbol{\Phi}$ および階層的圧力 $\Pi$ が満たす進化方程式：

$$
\frac{\partial \boldsymbol{\Phi}}{\partial \tau} - \beta \boldsymbol{\Phi} - \gamma (\boldsymbol{\xi} \cdot \nabla_{\boldsymbol{\xi}})\boldsymbol{\Phi} - \tilde{\nu} \Delta_{\boldsymbol{\xi}} \boldsymbol{\Phi} + (\boldsymbol{\Phi} \cdot \nabla_{\boldsymbol{\xi}})\boldsymbol{\Phi} + \nabla_{\boldsymbol{\xi}} \Pi = 0
$$

$$
\nabla_{\boldsymbol{\xi}} \cdot \boldsymbol{\Phi} = 0
$$

> **[補題 4.1：階層的圧力の遠方場減衰推定]**  
> プルバック座標 $|\boldsymbol{\xi}| \to \infty$ において、階層的圧力 $\Pi$ は一様な積分可能性評価を満たす：
>
> $$
> \lim_{|\boldsymbol{\xi}| \to \infty} |\Pi(\tau, \boldsymbol{\xi})| \le C_\Pi \cdot e^{(2\beta - 2\gamma)\tau} |\boldsymbol{\xi}|^{-2}
> $$

> **[補題 4.2：内部時間におけるOSGエントロピー単調性法則]**  
> 内部時間 $\tau = -\ln(T-t)$ は単なるパラメータの再設定ではなく、外殻グリッド（OSG）上の位相空間における不可逆的な散逸的動的流れを記述する。OSGエントロピー汎関数 $S_{\text{OSG}}$：
>
> $$
> S_{\text{OSG}}[\boldsymbol{\Phi}](\tau) \equiv -\int_{\text{OSG}} \boldsymbol{\Phi} \ln \boldsymbol{\Phi} \, d\mu_{\text{shell}}
> $$
>
> に対し、以下が厳密に成立する：
>
> $$
> \frac{d S_{\text{OSG}}}{d\tau} = \tilde{\nu} \int_{\text{OSG}} \frac{|\nabla_{\boldsymbol{\xi}} \boldsymbol{\Phi}|^2}{\boldsymbol{\Phi}} \, d\mu_{\text{shell}} \ge 0
> $$
>
> リアルタイム $t$ での微視的な可逆性とは対照的に、引き戻された内部時間 $\tau$ は熱力学的矢印（不可逆的な散逸）を単調に前進させ、数学的に自己完結的なアトラクターに収束する。

### 3. ホログラフィック投影と位相的コボルディズム不変性

外殻グリッド（OSG）上の階層的場 $\boldsymbol{\Phi}$ から実空間への投影：

$$
\boldsymbol{u}_{\text{eff}}(t,\boldsymbol{x}) = \mathcal{P}_\sigma [\boldsymbol{\Phi}] = e^{-(\beta-\gamma)\tau} \int_{\text{OSG}} \boldsymbol{\Phi}\left(\tau, \, e^{\gamma \tau}(\boldsymbol{x} - \boldsymbol{x}^*)\right) d\mu_{\text{shell}}(\sigma)
$$

> **[補題 4.3：測度の位相的コボルディズム不変性]**  
> 特異点が $S_k$ から複合相 $S_{\text{layer}}$ へ移行する際、OSG多様体 $\mathcal{M}_{\text{OSG}}$ 上で位相的相転移が起こる。このとき、シェル測度 $d\mu_{\text{shell}}(\sigma)$ は微分可能多様体のコボルディズム類の下で不変であり、オイラー標数 $\chi(\mathcal{M}_{\text{OSG}})$ の不連続なジャンプを跨ぐ連続性を保証する：
>
> $$
> \int_{\mathcal{M}_{\text{OSG}}^{\text{before}}} d\mu_{\text{shell}}(\sigma) = \int_{\mathcal{M}_{\text{OSG}}^{\text{after}}} d\mu_{\text{shell}}(\sigma) = 1
> $$
>
> これは位相幾何学的に、相転移の前後における全確率の可算加法性とエネルギー保存を保証する。

---

## V. 因果構造フローチャート

弱い爆発条件 ＋ 単調性／無振動補題：

$$
\limsup_{t \uparrow T} \|\nabla \boldsymbol{u}\|_{L^p} = \infty \quad \land \quad \text{単調性推定}
$$

$$
\Downarrow
$$

タイプ固有のスケーリング指数 $\alpha_k$ および粘性衝撃層補題に基づいて5つのタイプを特定：

$$
\left( S_{\text{vortex}}[\alpha_{\text{vortex}}], \, S_{\text{sharp}}[\alpha_{\text{sharp}}], \, S_{\text{break}}[\alpha_{\text{break}}], \, S_{\text{jump}}[\alpha_{\text{jump}}], \, S_{\text{layer}}[\alpha_{\text{layer}}] \right)
$$

$$
\Downarrow
$$

離散決定論的関数が閾値 $C_{\text{crit}, k}(h)$ を超えているか判定：

$$
\lim_{t \uparrow T} \mathcal{D}_h [\boldsymbol{u}](t) \ge C_{\text{crit}, k}(h) = C_{0,k} h^{-\alpha_k}
$$

$$
\Downarrow
$$

微分形式プルバックオペレーター $\psi_\tau^*$ による動的リフティング：

$$
\boldsymbol{\Phi}(\tau, \boldsymbol{\xi}) = e^{(\beta-\gamma)\tau} \psi_\tau^* [\boldsymbol{u}]
$$

$$
\Downarrow
$$

遠方場圧力減衰 $\Pi$ および OSGエントロピー成長法則の下での内部偏微分方程式の発展：

$$
\frac{d S_{\text{OSG}}}{d\tau} \ge 0
$$

$$
\frac{\partial \boldsymbol{\Phi}}{\partial \tau} - \beta \boldsymbol{\Phi} - \gamma (\boldsymbol{\xi} \cdot \nabla_{\boldsymbol{\xi}})\boldsymbol{\Phi} + \nabla_{\boldsymbol{\xi}} \Pi = \dots
$$

$$
\Downarrow
$$

コボルディズム不変測度 $d\mu_{\text{shell}}(\sigma)$ によるホログラフィック投影：

$$
\boldsymbol{u}_{\text{eff}}(t,\boldsymbol{x}) = \mathcal{P}_\sigma [\boldsymbol{\Phi}]
$$

---

## VI. フックを量子重力にマッピングする（シェル型正則化結合）

アインシュタイン＝ヒルベルト領域における時空計量 $g_{\mu\nu}$ を用いた幾何学的結合方程式：

$$
G_{\mu\nu} + \Lambda g_{\mu\nu} = 8\pi G \left( T_{\mu\nu}^{\text{matter}} + T_{\mu\nu}^{(\sigma)} \right)
$$

### ガウス型／シェル型正則化応力エネルギーテンソル

$$
T_{\mu\nu}^{(\sigma)}(\boldsymbol{x}) = \rho_{\text{shell}}(\boldsymbol{x} - \boldsymbol{x}^*) \int_{\text{OSG}} \left( \nabla_\mu \boldsymbol{\Phi} \otimes \nabla_\nu \boldsymbol{\Phi} - \frac{1}{2} g_{\mu\nu} |\nabla_{\boldsymbol{\xi}} \boldsymbol{\Phi}|^2 \right) d\mu_{\text{shell}}(\sigma)
$$

- **正則化されたシェル密度関数 $\rho_{\text{shell}}$：**

$$
\rho_{\text{shell}}(\boldsymbol{r}) = \frac{1}{(2\pi \ell_{\text{OSG}}^2)^{3/2}} \exp\left( -\frac{|\boldsymbol{r}|^2}{2 \ell_{\text{OSG}}^2} \right)
$$

$$
\ell_{\text{OSG}} \sim h \quad \text{または} \quad \text{プランク長 } \ell_P
$$
