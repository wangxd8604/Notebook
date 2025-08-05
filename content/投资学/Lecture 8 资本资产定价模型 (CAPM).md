---
{"publish":true,"aliases":"CAPM","cssclasses":""}
---

## 一、引言 (Introduction)

*   **[[投资学/Lecture 7 证券组合管理\|Markowitz]]的投资组合管理理论：**
    *   在均值-方差框架下考察投资者对风险资产组合的选择过程，开创了现代金融理论的先河。
    *   **局限性：**
        *   将金融资产收益率作为已知，未深入探讨收益率的来源，也未说明资产价格如何受投资者偏好和资产特征影响。
        *   指出通过构建投资组合可以消除部分风险，但未明确单个资产的总风险是否决定其价格水平，以及单个资产价格与风险之间的具体关系。
*   **CAPM的诞生：**
    *   上述问题直到1964年由Sharpe给出答案，随后Lintner（1965）和Mossin（1966）也独立进行了证明，这便是**资本资产定价模型 (CAPM)** 。

## 二、两种基本的资产定价方法 (Two Basic Asset Pricing Methods)

现代理论金融经济学的核心内容是在不确定市场环境下为金融资产定价，即确定资产未来所有可能状态下的价值，并据此确定其当前价值。

1.  **一般均衡定价模型 (General Equilibrium Models)**
    *   **起源：** 1874年Walras首次提出一般经济均衡理论，后经Arrow和Debreu于1954年给出严格存在性证明。
    *   **核心思想：**
        *   描述经济体中消费者（追求消费效用最大化）和生产者（追求生产利润最大化）的经济活动，形成供需。
        *   市场供需影响价格，价格又反过来影响供需，最终市场出清，每个商品都有确定价格，且消费者和生产者都实现目标。
    *   **应用于金融：** Arrow（1953）将证券理解为在不确定状态下有不同价值的商品，Debreu认为金融产品是不同时间、不同状态下价值不同的商品，通过拓广商品空间维度，可将一般经济均衡模型应用于金融产品定价。
    *   **面临挑战：** 金融市场存在不确定性，商品数量是随机变量，传统确定性环境下的效用函数无法直接用于决策。
    *   **解决方案：** 引入Von Neunmann和Morgenstern（1944）提出的**期望效用函数理论**，将不确定环境下的决策描述为最大化期望效用函数的过程。
    *   **证券市场均衡形成：** 投资者从最大化个人期望效用角度选择最优证券持有量，投资者对证券的需求共同影响证券价格，直至需求等于供给，市场出清。

2.  **套利定价模型 (Arbitrage Pricing Models)**
    *   **起源：** Modigliani和Miller（1958）在探讨公司财务政策时，将无套利假设作为“公理”进行金融资产定价。
    *   **无套利假设 (No-arbitrage assumption)：** 在完善的金融市场中，不存在无成本获取无风险利润的机会。
        *   **微观角度：** 如果两个资产（组合）在未来每种状态下的支付都相同，则它们的价格应该相同。
    *   **与一般均衡模型的关系：** 无套利假设是“均衡定价论”的一个推论，即达到一般均衡的价格体系一定是无套利的。
    *   **优点：** 不需要对投资者偏好、禀赋、金融资产供需等问题进行假设，可脱离复杂的一般均衡框架直接定价。
    *   **缺点：**
        *   只能“就事论事”，无法建立全市场的理论框架。
        *   无套利假设在现实中需非常理想的市场条件才能成立，因此被寻求套利机会的[[投资学/Lecture 5-1 证券投资分析\|技术分析]]流派所排斥。
    *   **重要性：** 无套利假设是否成立可视为市场是否有效的标志。套利机会多的市场并非有效市场，定价问题无法有稳定解。理论研究定价问题必须要求市场有无套利假设。

## 三、资本资产定价模型 (CAPM)

CAPM是一个市场均衡模型，意味着证券供需相等，市场出清，且每个参与者都能实现自身效用最大化。

1.  **模型假设 (Model Assumptions)**
    1.  **大量投资者：** 每个投资者财富相对于市场总量微不足道，是资产价格的接受者，单个交易行为无法影响资产价格。
    2.  **理性与风险厌恶：** 所有投资者理性、风险厌恶，追求投资组合收益最大化和方差最小化（即采用[[投资学/Lecture 7 证券组合管理\|Markowitz]]模型进行投资决策）。
    3.  **一致预期：** 所有投资者对证券评价和经济局势看法一致，对证券收益率的概率分布期望一致，并拥有相同投资期限。
    4.  **可交易资产：** 投资者交易对象仅限于公开金融市场上的资产，非交易性资产（如人力资本）不在模型考虑范围内。
    5.  **无风险借贷：** 投资者可在固定的无风险利率水平上借入或贷出任何额度的资产。
    6.  **无交易成本：** 市场中不存在证券交易费用和税收。

2.  **结论一：所有投资者都将持有包含所有可交易资产的**市场资产组合**M**
    *   **市场组合M：** 将所有个人投资者的资产组合加总，借贷相互抵消，加总的风险资产组合价值等于整个经济中全部财富的价值。其中，每个股票在该组合中的比例等于该股票市值占所有股票市值的比例。
    *   **为何持有相同组合？** CAPM假设投资者都遵循[[投资学/Lecture 7 证券组合管理\|Markowitz]]的均值-方差模型，且投资期限和信念相同，因此必然选择相同的最优风险组合。
    *   **为何是市场组合？** 这是市场价格调整的结果。若某股票不被包含，其需求为零，价格将下跌，直到变得有吸引力并被投资者吸纳到最优组合中。价格动态调整确保所有股票都进入最优组合。

3.  **结论二：市场资产组合M不仅在有效边界上，而且M也是资本配置线与有效边界的切点**
    *   由于所有投资者均采用[[投资学/Lecture 7 证券组合管理\|Markowitz]]模型，其选择的最优风险资产组合一定在有效边界上，且是资本配置线 (CAL) 与有效边界的切点。
    *   **资本市场线 (CML - Capital Market Line)：** 当市场存在无风险资产和多个风险资产时，CAL成为一条通过无风险资产和市场资产组合的直线，即CML。
    *   **CML方程式：** $E(r_p) = r_f + \frac{E(r_M) - r_f }{σ_M }σ_p$。
    *   **图示：** CML是一条从无风险利率 `r_f` 出发，与有效边界相切于市场组合M的直线。
    ![](https://files.mdnice.com/user/73277/c12e2002-10fd-4f68-8063-d3d1da23ab20.png)


4.  **结论三：单个资产的风险溢价与市场资产组合M的风险溢价成比例，且与该证券的**Beta系数**成比例**
    *   **CAPM基本表达式：** $E(r_i) - r_f = \beta_i \times [E(r_M) - r_f]$。
        *   左端 `E(r_i) - r_f` 是资产 `i` 的风险溢价。
        *   右端 `E(r_M) - r_f` 是市场资产组合的风险溢价。
    *   **Beta定义：** $\beta_i = \frac{Cov(r_i, r_M)}{ Var(r_M)}$。
    *   **推导逻辑：**
        *   CAPM是一个市场均衡模型$\Rightarrow$证券的供给和需求相等，每个参与者都实现自身效用最大化。
        *   市场组合的风险溢价可以分解为：$E(r_M)-r_f=E(\Sigma_iw_ir_i)-r_f=\Sigma_iw_i[E(r_i)-r_f]$ $\Rightarrow$每个资产对于风险溢价的贡献为：$w_i[E(r_i)-r_f]$
        *   市场组合的风险可以分解为：$\operatorname{Var}\left(r_M\right)=\operatorname{Cov}\left(\sum_{i=1}^N w_i r_i, r_M\right)=\sum_{i=1}^N w_i \operatorname{Cov}\left(r_i, r_M\right)$ $\Rightarrow$每个资产对于风险的贡献为：$w_i \operatorname{Cov}\left(r_i, r_M\right)$
        *   市场组合中资产的风险价格全部相等（如果不等则需求一定为0或无穷大，无法达到均衡）:$\frac{w_i[E\left(r_i\right)-r_f]}{w_i\operatorname{Cov}\left(r_i, r_M\right)}=\frac{E\left(r_i\right)-r_f}{\operatorname{Cov}\left(r_i, r_M\right)}=\frac{E\left(r_j\right)-r_f}{\operatorname{Cov}\left(r_j, r_M\right)} \equiv \bar{k}$
        *   $E\left(r_i\right)-r_f=\bar{k}\operatorname{Cov}\left(r_i, r_M\right)$等式两侧乘上对应的$w_i$，所有等式两侧相加，最终得到均衡条件下，市场组合的风险价格等于单个资产的风险价格。$\begin{gathered}\sum_{i=1}^N w_i\left[E\left(r_i\right)-r_f\right] \equiv \sum_{i=1}^N w_i \bar{k} \operatorname{Cov}\left(r_i, r_M\right) \\ E\left(r_M\right)-r_f=\bar{k} \operatorname{Cov}\left(r_M, r_M\right)=\bar{k} \operatorname{Var}\left(r_M\right) \\ \frac{E\left(r_M\right)-r_f}{\operatorname{Var}\left(r_M\right)}=\bar{k}=\frac{E\left(r_i\right)-r_f}{\operatorname{Cov}\left(r_i, r_M\right)}\end{gathered}$
        * 最终得到CAPM的基本表达式。
## 四、CAPM的理论的数学推导 (Theoretical Derivation of CAPM)

理论推导从市场组合是切点组合（即斜率 $(E(r_p) - r_f) / σ_p$ 达到最大）开始，通过最优化问题的一阶条件，最终推导出CAPM表达式，具体推导过程不在考察范围内，以下仅做展示。


> *推导：*
>$\begin{array}{lc}\max _{w_1 \cdots w_N} & \theta=\text { slope }=\frac{E\left(r_p\right)-r_f}{\sigma_p} \\ \text { s.t. } & E\left(r_p\right)=\sum_{i=1}^N w_i E\left(r_i\right) \\ & \sum_{i=1}^N w_i=1\\ &\sigma_p=\left[\sum_{i=1}^N w_i^2 \sigma_i^2+\sum_{i=1}^N \sum_{j=1, i \neq j}^N w_i w_j \sigma_{i j}^2\right]^{0.5}\end{array}$
>将方差、期望代入目标方程
>$\theta=\frac{\sum_{i=1}^N w_i\left[E\left(r_i\right)-r_f\right]}{\left[\sum_{i=1}^N w_i^2 \sigma_i^2+\sum_{i=1}^N \sum_{j=1, i \neq j}^N w_i w_j \sigma_{i j}^2\right]^{0.5}}$
令：
$\begin{gathered}F_1(w)=\sum_{i=1}^N w_i\left[E\left(r_i\right)-r_f\right] \\ F_2(w)=\left[\sum_{i=1}^N w_i^2 \sigma_i^2+\sum_{i=1}^N \sum_{j=1, i \neq j}^N w_i w_j \sigma_{i j}^2\right]^{-0.5} \\ \frac{\partial F_1(w)}{\partial w_k}=E\left(r_k\right)-r_f \\ \frac{\partial F_2(w)}{\partial w_k}=-\frac{1}{2}\left(\sum_{i=1}^N w_i^2 \sigma_i^2+\sum_{i=1}^N \sum_{j=1, i, i j}^N w_i w_j \sigma_{i j}^2\right)^{-\frac{3}{2}} \times\left(2 w_k \sigma_k^2+2 \sum_{j=1, j \neq k}^N w_j \sigma_{j k}^2\right) \\ =-\frac{1}{2} F_2(w)^3 \times\left(2 w_k \sigma_k^2+2 \sum_{j=1, j \neq k}^N w_j \sigma_{j k}^2\right) \\ \end{gathered}$
令：
$\frac{\partial \theta}{\partial w_k}=F_1(w^*) \frac{\partial F_2(w)}{\partial w_k}|_{w=w^*}+F_2(w^*) \frac{\partial F_1(w)}{\partial w_k}|_{w=w^*}=0,\ \ \ k=1,...,N$
替换式中函数与偏导：
$-\frac{\sum_{i=1}^N w_i[E(r_i)-r_f]}{\sum_{i=1}^N (w_i)^2 \sigma_i^2+\sum_{i=1}^N \sum_{j=1, i \neq j}^N w_i w_j \sigma_{i j}^2} (w_k \sigma_k^2+\sum_{j=1, j \neq k}^N w_j \sigma_{j, k}) |_{w=w^*}+[E(r_k)-r_f]=0$
>由于下面的表达式对全体资产求和，简化下角标:
$\begin{gathered}\\ \lambda=\frac{\sum_{i=1}^N w_i\left[E\left(r_i\right)-r_f\right]}{\sum_{i=1}^N w_i^2 \sigma_i^2+\sum_{i=1}^N \sum_{j=1, i \neq j}^N w_i w_j \sigma_{i j}^2} |_{w=w^*}=\frac{E\left(r_M\right)-r_f}{\sigma_M^2} \\ E\left(r_k\right)-r_f=\lambda w_k \sigma_k^2 |_{w=w^*}+\sum_{j=1, k \neq j}^N \lambda w_j \sigma_{j k}^2 |_{w=w^*} \\ z_k=\lambda w_k^* \\ E\left(r_i\right)-r_f=z_1 \sigma_{i 1}^2+z_2 \sigma_{i 2}^2+z_3 \sigma_{i 3}^2+\cdots+z_N \sigma_{i N}^2 \end{gathered}$
此N元线性方程组满秩条件下有唯一解，但对应得$w^*$存在无数个，解系为与$z$共线的向量集（证明略，证明思路是求出$w$关于$\lambda$的表达式并反代回$\lambda$关于$w$的方程，证明左右两侧恒成立，这也是该模型存在解析解精妙的地方），但根据优化问题中剩下的最后一个条件——解的和为1，可以确定唯一的解析解： 
$w_k^*=\frac{z_k}{\sum_{k=1}^N z_k}$
继续对单个资产的风险溢价分析：
$E\left(r_i\right)-r_f=z_1 \sigma_{i 1}^2+z_2 \sigma_{i 2}^2+z_3 \sigma_{i 3}^2+\cdots+z_N \sigma_{i N}^2=\lambda Cov(r_i,r_M) = \frac{E\left(r_M\right)-r_f}{\sigma_M^2} Cov(r_i,r_M)=\beta_i(E\left(r_M\right)-r_f)$
得出均衡条件下，单个资产的风险价格相等：$\frac{E\left(r_i\right)-r_f}{Cov(r_i,r_M)}=\lambda$
此外，模型的解析解给出了一个重要的结论：均衡状态下，资产的风险溢价只和市场组合回报一起波动的系统风险相关，即结论三。这意味着市场不会对单个资产的非系统性风险给予任何回报，这是均衡条件下内生推导的一个定理而非经验结论或前提假设。

1.  **Beta的意义 (Meaning of Beta)**
    *   **衡量系统性风险：** Beta衡量的是资产的**系统性风险**，而非系统性风险（可通过投资组合分散消除）与资产定价无关。资产价格只与系统性风险的大小有关，市场只针对系统性风险进行风险补偿。
    *   **资产组合的Beta：** 资产组合的Beta值等于组合中每个资产Beta值的加权平均，权重即资产在组合中的比重：$\beta_P = Σ(\omega_i * \beta_i)$，其中的$\omega_i$非市场组合权重。
    *   **市场组合的Beta：** 市场组合的Beta值为**1**。$\beta_M=\sum_{i=1}^N w_i \beta_i=\sum_{i=1}^N w_i \frac{\operatorname{Cov}\left(r_i, r_M\right)}{\operatorname{Var}\left(r_M\right)}=1$
    *   **Beta与波动：** 若资产Beta高于1，其收益率波动大于市场组合；若Beta低于1，则波动小于市场组合。

2.  **证券市场线 (SML - Security Market Line)**
    *   **定义：** **期望收益-Beta关系曲线**就是证券市场线。
    *   **SML方程式：** $E(r_i) = r_f + \beta_i * [E(r_M) - r_f]$。
    *   **斜率：** SML的斜率为市场资产组合的风险溢价 `E(r_M) - r_f`。
    *   **特点：**
        *   当Beta=1时，期望收益为市场组合的期望收益 `E(r_M)`。
        *   刻画的是作为资产风险函数的单项资产的风险溢价，风险工具是Beta。
        *   **适用于任意资产组合或单项资产**。![|366x305](https://files.mdnice.com/user/73277/71fc2b06-d9d7-49ea-9ac1-c9e0434a26e3.png)
3.  **CAL、CML和SML的比较**
    *   **CAL (Capital Allocation Line - 资本配置线)：** 仅考虑有风险+无风险资产的组合情况，描述任意资产的期望收益与标准差的关系，最优条件下是过无风险资产与有效边界相切的线。
	    ![|299x292](https://files.mdnice.com/user/73277/e23b0edc-d61b-4ace-836f-1fc01da67436.png)
    *   **CML (Capital Market Line - 资本市场线)：** 描述当所有投资者有同质预期时，有效率资产的期望收益与标准差的关系。是过无风险资产与市场组合的线。**只适用于有效率的投资组合**。
	    ![|321x303](https://files.mdnice.com/user/73277/d6a5783b-adea-41a4-ae30-36cb1079e594.png)
    *   **SML (Security Market Line - 证券市场线)：** 描述市场均衡时资产的期望收益与**系统性风险（Beta）** 的关系。只要市场有效率（不对非系统性风险补偿），**无论是单个资产还是资产组合都在SML上**。
     ![|366x305](https://files.mdnice.com/user/73277/71fc2b06-d9d7-49ea-9ac1-c9e0434a26e3.png)

4.  **SML与业绩评估 (SML and Performance Evaluation)**
    *   **公平定价基准：** “公平定价”的资产一定在SML上，其期望收益与风险相匹配。
    *   **业绩评估工具：** SML为评估投资业绩提供了基准。
    *   **Alpha (Jensen's Alpha)：** 实际期望收益与SML预测的“正常期望收益”之差。
        *   若**Alpha > 0**，资产被认为是“好”资产，当前价格可能被低估。
        *   例：股票Beta 1.2，期望收益17%；无风险利率6%，市场期望收益14%。则该股票应获得期望收益为 `6% + 1.2 * (14% - 6%) = 15.6%`。此时Alpha为 `17% - 15.6% = 1.4%`。

## 五、CAPM的拓展 (Extensions of CAPM)

1.  **Fischer Black：零Beta CAPM (Zero Beta CAPM)**
    *   **动机：** 传统CAPM假设（存在无风险资产、投资者能以无风险利率借贷且借贷利率相同）在现实中不完全成立。严格意义上的无风险资产（如美国短期国债）也仅是近似。
    *   **Black (1972) 的贡献：** 在市场中不存在无风险资产以及借款贷款利率不相等的情况下考察了CAPM。他发现无风险资产的存在性和借贷利率相等的要求并非CAPM成立的必要条件。
    *   **核心思想：** 无风险资产的Beta值为零。如果能构造一个收益与市场无关的投资组合，其Beta值为零，这个零Beta组合的期望收益率就可以代替无风险利率。
    *   **修正形式：** $E(R_i) = E(R_Z) + \beta_i \times [E(R_M) - E(R_Z)]$。
        *   `E(R_Z)` 是零Beta组合的期望收益率。
        *   `E(R_M) - E(R_Z)` 是风险溢价。
        *   模型形式变化不大，只是用零Beta组合的期望收益率替代了无风险利率。
    ![|442x409](https://files.mdnice.com/user/73277/ac89272f-a085-4df1-8543-b09b2a0ec34d.png)

2.  **Robert Merton：多因素CAPM (Multifactor CAPM)**
    *   **动机：** [[投资学/Lecture 7 证券组合管理\|Markowitz]]和CAPM假设投资者唯一关心的风险是证券价格在未来的不确定性。但现实中投资者还关心其他影响其未来消费能力的风险，如未来劳务收入风险、消费品未来相对价格、未来投资机会等。
    *   **Merton (1973) 的贡献：** 以消费为基础对象扩展了CAPM，推导出当人们面临这些额外市场风险来源时，其生存期间的最优消费组合。
    *   **基本形式：** $E(R_P) - R_f = \beta_{PM} \times [E(R_M) - R_f] + \beta_{PF_1} \times [E(R_{F_1}) - R_f] + ... + \beta_{PF_k} \times [E(R_{F_k}) - R_f]$。
        *   `F_k` 为额外的市场风险来源（如经济、金融、行业因素）。
        *   `Beta_PM` 为投资组合对市场的敏感性。
        *   `Beta_PF_k` 为投资组合对第 `k` 个风险来源的敏感性。
    *   **意义：** 投资者除了市场风险外，还要为其承担的每一个额外风险来源获得补偿。若不存在额外风险来源，该模型即退化为传统CAPM形式。



## 六、总结 (Summary)

*   **资本资产定价模型 (CAPM)** 是金融理论中的核心模型，用于估计资产的风险和预期回报。
*   **核心假设：** 所有投资者遵循[[投资学/Lecture 7 证券组合管理\|Markowitz]]模型，市场由大量价格接受者组成，市场高效，无交易费用和税收，投资者风险厌恶且预期一致。
*   **关键结论：** 所有投资者将持有**市场资产组合 (M)**，该组合在**资本市场线 (CML)** 上是有效的，且是资本配置线与有效边界的切点。
*   **风险衡量：** 资产或资产组合的预期收益通过其**Beta系数**评估，Beta衡量的是系统风险。
*   **证券市场线 (SML)：** 描绘了市场均衡条件下资产预期收益与系统性风险 (Beta) 之间的关系。SML用于评估资产表现是否与其风险匹配，高于SML预期的资产表现良好（正Alpha），反之表现不佳（负Alpha）。
*   **CAPM的拓展：** 例如Merton的多因素CAPM和Black的零Beta CAPM，提供了对传统模型的补充和改进，能够更全面地解释资产的风险和预期回报。
