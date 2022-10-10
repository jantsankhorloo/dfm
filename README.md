# Dynamic Factor Model for Mongolia

The dynamic factor model considered in this notebook can be found in the `DynamicFactorMQ` class, which is a part of the time series analysis component (and in particular the state space models subcomponent) of Statsmodels. It can be accessed as follows:

```python
import statsmodels.api as sm
model = sm.tsa.DynamicFactorMQ(...)
```
The statistical model and the EM-algorithm used for parameter estimation are described in:

- Bańbura and Modugno (2014), "Maximum likelihood estimation of factor models on datasets with arbitrary pattern of missing data." ([Working paper](https://core.ac.uk/download/pdf/6684705.pdf), [Published](https://onlinelibrary.wiley.com/doi/full/10.1002/jae.2306?casa_token=tX0xS_49OXcAAAAA%3Aocw-egTRztTVg643NCHRCQUs_OGCPMTS78Qds4gk2nN6ViFjOMZYSDVip-0eeDwQCpvaTOTqjof5_wKI)), and
- Bańbura et al. (2011), "Nowcasting" ([Working paper](https://core.ac.uk/download/pdf/6518537.pdf), [Handbook chapter](https://www.oxfordhandbooks.com/view/10.1093/oxfordhb/9780195398649.001.0001/oxfordhb-9780195398649-e-8))

As in these papers, the basic specification starts from the typical "static form" of the dynamic factor model:

$$
\begin{aligned}
y_t & = \Lambda f_t + \epsilon_t \\
f_t & = A_1 f_{t-1} + \dots + A_p f_{t-p} + u_t
\end{aligned}
$$
