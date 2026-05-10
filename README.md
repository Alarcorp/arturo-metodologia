# 2. Methodology

## 2.1 Chemical-Optical Input Modeling

Chemical species identification was modeled through the relationship between analyte concentration and the refractive-index variation of aqueous solutions. Four representative compounds were selected based on their environmental significance and compliance with the Mexican drinking water regulation NOM-127-SSA1-2021 (Secretaría de Salud, 2022): Lead Sulfate ($PbSO_4$), Copper Sulfate ($CuSO_4$), Nitrate ($KNO_3$) and Calcium Carbonate ($CaCO_3$). These species are commonly associated with industrial leaching, mining contamination, agricultural runoff, and water hardness, respectively (Páez-Osuna et al., 2015; Santucci and Scully, 2020; Ward et al., 2018; World Health Organization, 2011).

The modeling framework proceeds in two integrated stages. First, the chemical concentration is transduced into an optical parameter for the waveguide system. For a given solute, the molecular signature is defined by its molar mass $M_{solute}$ and molar refractivity $R_{solute}$. The molar mass is derived from the stoichiometric sum of the constituent atomic weights. For instance, in the case of $PbSO_4$, the calculation considers the atomic masses of 207.2 u from the Pb cation, 32.06 u from sulfur (S) and 64 u from the four oxygen atoms, yielding a total molecular mass of $M_{solute} = 303.27 \text{ g/mol}$. Complementarily, the molar refractivity quantifies the electronic polarizability of the ionic species, retrieved from standardized physicochemical databases and reference handbooks (Batsanov, 1982, Haynes, 2017). For $PbSO_4$, the $R_{solute}$ is taken as 38.8 $\text{cm}^3\text{/mol}$, $CuSO_4$ is 33.72 $\text{cm}^3\text{/mol}$, $KNO_3$ is 12.4 $\text{cm}^3\text{/mol}$ and $CaCO_3$ is 13.1 $\text{cm}^3\text{/mol}$. To connect these stoichiometric properties with the optical response of the solution, the analyte concentration expressed in mg/L was first converted into molar concentration through

$$C_{(mol/L)}=\frac{C_{(mg/L)}}{M_{solute} \cdot 1000} \quad , \quad (1)$$

where the factor $10^3$ converts milligrams into grams, ensuring dimensional consistency in mol/L. This conversion is physically relevant because electromagnetic interactions depend on the effective number density of molecular entities present in the solution rather than solely on their total mass concentration. Under dilute conditions, the molar concentration determines the corresponding mole fraction of the solute, $\chi_{solute}$, within the aqueous mixture

$$\chi_{solute}=\frac{C_{(mol/L)}}{C_{(mol/L)}+\frac{1000 \text{ g/L}}{M_{H_2 O}}} \quad , \quad (2)$$

where $M_{H_2 O} = 18.015 \text{ g/mol}$ is the molar mass of water. The mole fraction acts as a weighting factor in the molar refractivity of the mixture $R_{mix}$ as 

$$R_{mix}=(1-\chi_{solute}) \cdot R_{H_2 O}+\chi_{solute} \cdot R_{solute} \quad , \quad (3)$$

being the molar refractivity of water $R_{H_2 O} = 3.71 \text{ cm}^3\text{/mol}$ and $R_{solute}$ act as the fundamental optical signatures of each component (Atkins and de Paula, 2018) (González-Velasco, 2014). Subsequently, the refractive index of the mixture $n$ is derived using the Lorentz-Lorenz equation (Alavia, Soto and Lovera, 2021; Talebian and Talebian, 2013), linking macroscopic polarizability to the optical density of the medium

$$n=\sqrt{\frac{1+2(R_{mix} / V_{mol})}{1-(R_{mix} / V_{mol})}} \quad . \quad (4)$$

Within this expression, $V_{mol}$ represents the molar volume, defining the space occupied by one mole of the solution. For trace-level concentrations in aqueous media, it is assumed that no significant volumetric changes occur; therefore, $V_{mol}$ is approximated to the molar volume of pure water, $V_{mol} = 18.07 \text{ cm}^3\text{ mol}^{-1}$. This parameter effectively scales the microscopic electronic polarizability of the molecules to the macroscopic refractive index. Under dilute conditions, the refractive-index variation of aqueous solutions can be locally approximated through a first-order dependence on analyte concentration. This approximation follows from the Lorentz–Lorenz relation, where small perturbations in molecular polarizability produce correspondingly small variations in the effective refractive index of the medium (González-Velasco, 2014). Accordingly, the refractive index was parameterized as

$$n_{linear}=n_{H_2 O}+k \cdot C_{(mg/L)} \quad \quad (5)$$

where $n_{H_2 O} = 1.333$ is the refractive index of water, $k = 10^{-3} \cdot R_{solute}/M_{solute}$ is an effective optical sensitivity coefficient expressed in L/mg, while the factor $10^{-3}$ ensures dimensional consistency between molar refractivity and concentration expressed in mg/L. The resulting parametrization preserves the relative optical contrast among analytes and enables concentration-dependent refractive-index discrimination. As summarized in Table 1, the proposed model predicts a progressive increase in refractive index with increasing contaminant concentration. For instance, $PbSO_4$, starting from a pure water, $n_{H_2 O} = 1.333$, the model records a progressive increase in optical density until reaching a value of $n_{linear} = 1.39780999$ at a concentration of 505.05 mg/L.

| component | Concentration mg/L | n_linear |
| :--- | :--- | :--- |
| **PbSO_4** | 0 | 1.333 |
| | 101.010101 | 1.345962 |
| | 202.020202 | 1.35892399 |
| | 505.050505 | 1.39780999 |

*Table 1. Concentration-dependent refractive-index values $n_{linear}$, for $PbSO_4$ obtained from the first-order optical parametrization using pure water as the reference baseline.*

---

## 2.2 Slot waveguide model and solution

Once the concentration-dependent refractive index $n_{linear}$ is obtained from the chemical–optical transduction model described in Section 2.1, it is incorporated as the optical parameter associated with the analyte medium within the sensing structure. Since the electromagnetic response of the guided mode is directly governed by the dielectric properties of the surrounding medium, variations in analyte concentration produce corresponding perturbations in the optical propagation characteristics of the waveguide.

In the second stage of the modeling framework, the optical response of the sensing structure is analyzed using the slot-waveguide architecture proposed by Almeida et al. (2004). The configuration consists of two parallel high-refractive-index dielectric slabs of refractive index $n_h$ and thickness $W = b - a$, separated by a distance $d = 2a$. The region between the slabs is filled with the analyte medium, whose refractive index is defined as $n_s = n_{linear}$, thereby forming a low-index slot region. The complete structure is embedded within a cladding medium of refractive index $n_c$. As illustrated in Fig. 1, the system is modeled as a symmetric five-layer structure (regions I–V), where the symmetry of the slabs enhances the confinement of the electromagnetic field within the slot region, enabling increased sensitivity to refractive index variations.

Light propagation is assumed along the z-axis, with invariance in the y-direction, reducing the problem to a one-dimensional transverse analysis along x. The optical response of the structure is governed by Maxwell’s equations. In this work, the analysis focuses on Transverse Magnetic (TM) modes due to their strong electric-field enhancement within the low-index slot region, which is particularly advantageous for high-sensitivity refractive-index sensing applications (Agrawal, 2005; Biallo, et al. 2006; Ghosh, 2017). The magnetic field distribution associated with the guided TM mode is expressed as $E(x,y,z,t)=\phi_y (x) e^{i(\omega t-\beta z)}$, where $\beta$ is the propagation constant and $\omega=2\pi c/\lambda$ is the angular frequency related to the operating wavelength $\lambda$, with $c$ denoting the speed of light in vacuum. The transverse field profile $\phi_y (x)$ is evaluated across the five regions of the structure illustrated in Fig. 1. Following the analytical model by Almeida et al. (2004), the profile is defined as

$$\phi(x) = A \begin{cases} \frac{1}{n_c^2} \left[ \cosh(\gamma_s a) \cos(k_h W) + \frac{\gamma_s}{k_h} \left(\frac{n_h}{n_s}\right)^2 \sinh(\gamma_s a) \sin(k_h W) \right] e^{-\gamma_c(x-b)}, & x > b \\ \frac{1}{n_h^2} \cosh(\gamma_s a) \cos[k_h(x-a)] + \frac{\gamma_s}{n_s^2 k_h} \sinh(\gamma_s a) \sin[k_h(x-a)], & -a < x < b \\ \frac{1}{n_s^2} \cosh(\gamma_s x), & -a < x < a \\ \frac{1}{n_h^2} \left[ \cosh(\gamma_s a) \cos[k_h(x+a)] + \frac{\gamma_s}{k_h} \left(\frac{n_h}{n_s}\right)^2 \sinh(\gamma_s a) \sin[k_h(x+a)] \right], & -b < x < -a \\ \frac{1}{n_c^2} \left[ \cosh(\gamma_s a) \cos(k_h W) + \frac{\gamma_s}{k_h} \left(\frac{n_h}{n_s}\right)^2 \sinh(\gamma_s a) \sin(k_h W) \right] e^{\gamma_c(x+b)}, & x < -b \end{cases} \quad , \quad (6)$$

where $A$ is a normalization constant, while $\gamma_c^2 = \beta^2 - (\omega n_c / c)^2$, $\gamma_s^2 = \beta^2 - (\omega n_s / c)^2$ and $k_h^2 = (\omega n_h / c)^2 - \beta^2$, correspond to the transverse field parameters in the cladding, slot, and high-index slabs, respectively. Specifically, $\gamma_c$ governs evanescent decay in the cladding, ensuring optical confinement; $\gamma_s$ characterizes the field behavior within the slot region; and $k_h$ determines the oscillatory propagation of the field within the guiding slabs. The analysis assumes guided modes satisfying $\beta > \omega n_s/c, \omega n_c/c$, ensuring evanescent decay outside the guiding region. By applying the continuity conditions of the transverse magnetic field at each interface between the j-th and k-th layer, namely the continuity of $\phi(x)$ and its derivative weighted by the refractive index contrast, $\phi_{j,y}(x) = \phi_{k,y}(x)$ and $\frac{d}{dx}\phi_{j,y}(x) = \left(\frac{n_j}{n_k}\right)^2 \frac{d}{dx}\phi_{k,y}(x)$, a system of equations for the field amplitudes is obtained. These conditions lead to the transcendental equation that governs the propagation constant of the guided modes (Liu et al., 2015):

$$\arctan\left[\frac{n_h^2 \gamma_c}{n_c^2 k_h}\right] + \arctan\left[\frac{n_h^2 \gamma_s}{n_s^2 k_h} \tanh(\gamma_s a)\right] + m\pi = k_h(b-a) \quad , \quad (7)$$

where $m$ denotes the mode order. In this work, only the fundamental TM mode ($m=0$) was considered in order to ensure stable single-mode operation and simplify the interpretation of the sensing response. Eq. (7) enables the calculation of the propagation constant $\beta$ for each optical wavelength $\lambda$. The structural parameters of the waveguide ($W, d, n_h$, and $n_c$) are kept fixed, while the slot refractive index $n_s$, was varied according to the concentration-dependent described in Section 2.1. By systematically sweeping both the operating wavelength $\lambda$ in a range from 200 nm to 1400 nm and the slot refractive index $n_s$, the modal response of the structure was evaluated through the propagation constant $\beta$, which characterizes the effective electromagnetic behavior of the guided mode. Once $\beta$ was determined, the electromagnetic field distribution associated with the TM mode was reconstructed from Eq. (6), allowing the evaluation of relevant sensing quantities. In this modeling, the refractive indices of the high-index slabs and the cladding were kept constant at $n_h = 3.48$ and $n_c = 2$, respectively, while the refractive index of the slot region, $n_s$, was adjusted according to the specific values derived from the ionic mixture dependent on its concentration. In particular, the normalized electromagnetic energy confined within the slot region was quantified through the confinement factor, $\eta$, defined as (Liu et al., 2015):

$$\eta = \frac{P_{slot}}{P_{total}} = \frac{n_s^2 \int_{-a}^{a} |\phi(x)|^2 dx}{\sum_j n_j^2 \int_{\text{region } j} |\phi(x)|^2 dx} \quad , \quad (8)$$

where $P_{slot}$ and $P_{total}$ denote the electromagnetic energy confined within the slot region and across the complete waveguide structure, respectively (Liu et al., 2015). To characterize energy transport through the waveguide, the group velocity $v_g$ was obtained from the dispersion relation as (Dombi and Dineva, 2020)

$$v_g = \left(\frac{d\beta}{d\omega}\right)^{-1} \quad , \quad (9)$$

where the derivative is evaluated numerically from the wavelength-dependent data using a Savitzky–Golay filter to reduce discretization noise. Assuming steady-state guided mode propagation, the optical power confined within the slot region is $P_{slot} = P_{in} \cdot \eta$, where $P_{in}$ denotes the input optical power associated with the guided mode. The corresponding electromagnetic energy density within the slot region is then estimated as (Han et al., 2022)

$$u_{slot} = \frac{P_{in} \cdot \eta}{v_g} \quad . \quad (10)$$

The conversion of the optical response into an effective electrical signal was subsequently modeled from the electromagnetic energy density. Considering the cross-sectional dimensions of the sensing region, the effective electric field within the slot region, $E_{eff}$, was estimated as (Agrawal, 2005)

$$E_{eff} = \sqrt{\frac{2u_{slot}}{\varepsilon_0 n_s^2}} \quad , \quad (11)$$

where $\varepsilon_0$ is the vacuum permittivity. Once $E_{eff}$ is determined, the dissipated electrical power within the ionic medium was estimated through

$$P_{elec} = \sigma |E_{eff}|^2 V_{vol} \quad \quad (12)$$

The electrical conductivity of the analyte solution is defined as $\sigma = \Lambda \cdot C_{(mol/L)}$, where $\Lambda$ denotes the molar conductivity of the specific ionic species. For the analytes under evaluation, the nominal values of $\Lambda$ at 25°C are: 150.02 $\text{S}\cdot\text{cm}^2\text{/mol}$ for $PbSO_4$, 133.62 $\text{S}\cdot\text{cm}^2\text{/mol}$ for $CuSO_4$, 144.90 $\text{S}\cdot\text{cm}^2\text{/mol}$ for $KNO_3$ and 128.80 $\text{S}\cdot\text{cm}^2\text{/mol}$ for $CaCO_3$ (Atkins and de Paula, 2018; Haynes, 2017) and $V_{vol}$ corresponds to the effective interaction volume of the sensing region (Biallo et al., 2006). This quantity provides an additional descriptor associated with the electrical response of the analyte-loaded waveguide. Complementarily, standard performance metrics for integrated photonic sensing were extracted from the simulated electromagnetic response. The spectral sensitivity $S_\lambda$ was evaluated as the variation of the effective modal index $n_{eff} = \beta \lambda / 2\pi$ with respect to analyte concentration (Khonina et al., 2022)

$$S_\lambda = \frac{\partial n_{eff}}{\partial C} \quad . \quad (13)$$

In addition, the electromagnetic interaction factor $\xi$ was calculated as (Saleh and Teich, 2019; Han et al., 2022)

$$\xi = \frac{\int_{slot} |E|^2 dA}{\int_{total} |E|^2 dA} \quad , \quad (14)$$

From these physically derived quantities, a simulation-driven electromagnetic dataset was generated using MATLAB by systematically varying both analyte concentration and operating wavelength. The resulting descriptors, including $\beta$, $\eta$, $v_g$, $E_{eff}$, $P_{elec}$, $S_\lambda$, and $\xi$, define a multidimensional electromagnetic signature associated with each chemical species. These descriptors were subsequently processed in Python to construct the feature space employed in the machine-learning classification stage.

---

# 3. Classification models

To evaluate the separability of the generated electromagnetic feature space, four complementary machine-learning approaches were implemented: Decision Tree (DT), Random Forest (RF), XGBoost, and Multilayer Perceptron (MLP). These models were selected to progressively analyze the classification problem from interpretable rule-based methods to ensemble-learning strategies and nonlinear deep-learning architectures.

## 3.1 Decision Tree

A Decision Tree (DT) classifier was employed as an interpretable baseline to evaluate the discriminatory capacity of the electromagnetic descriptors. For a dataset $D=\{(x_i,y_i)\}_{i=1}^n$, the model recursively partitions the feature space using threshold rules $x_j \le \tau$, selecting splits that minimize the Gini impurity, $1-\sum_{i=1}^K p_i^2$. Model complexity was controlled by limiting tree depth and minimum samples per split to reduce overfitting.

## 3.2 Random Forest

A Random Forest (RF) classifier was employed to enhance robustness and reduce variance through bootstrap aggregation and random feature selection. The model constructs an ensemble of decision trees trained on resampled subsets of the data, with each split considering a subset of features. Predictions are obtained via majority voting, $\hat{H}(x)=\text{argmax}_k \sum_{b=1}^B I(\hat{y}_b(x)=k)$, where $B$ is the number of trees and $I(\cdot)$ the indicator function. Model complexity was controlled by tuning the number of estimators and maximum tree depth to balance accuracy and generalization.

## 3.3 XGBoost

Extreme Gradient Boosting (XGBoost) was employed as a high-performance ensemble method based on sequential tree boosting. The model iteratively fits decision trees to minimize a regularized objective function combining a differentiable loss and a complexity penalty. At iteration $t$, the prediction is updated as $\hat{y}_i^{(t)} = \hat{y}_i^{(t-1)} + f_t(x_i)$, where $f_t$ denotes the newly added tree. Regularization terms controlling tree complexity were included to prevent overfitting. Key hyperparameters, including learning rate, maximum depth, and number of estimators, were optimized to balance bias–variance trade-offs.

## 3.4 Multilayer Perceptron

A Multilayer Perceptron (MLP) was employed to model nonlinear relationships in the electromagnetic feature space. For an input vector $x=[x_1,\dots,x_n]$, each neuron computes a linear transformation followed by a nonlinear activation, $z=w^T x+b$. The network parameters were optimized via backpropagation using stochastic gradient-based methods. To improve generalization, dropout regularization and validation-based early stopping were applied during training.

All the above models are evaluated using standard classification metrics derived from the confusion matrix, including Accuracy, Recall, and F1-score (Hastie et al., 2009),

$$\text{Accuracy} = \frac{\text{TP}+\text{TN}}{\text{TP}+\text{TN}+\text{FP}+\text{FN}}$$  
$$\text{Recall} = \frac{\text{TP}}{\text{TP}+\text{FN}}$$  
$$\text{F1} = 2 \frac{\text{Precision} \cdot \text{Recall}}{\text{Precision}+\text{Recall}}$$

where TP, TN, FP, and FN denote true positives, true negatives, false positives, and false negatives, respectively. Complementarily, confusion matrices and learning curves analysis were employed to evaluate class separability and overall model discrimination performance.
