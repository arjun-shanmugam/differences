<img src="./doc/source/images/logo/bw/logo_name_bw.png" alt="drawing" width="200" 
style="display: block;margin-left: auto;margin-right: auto;width: 80%;"/>

difference-in-differences estimation and inference for Python

**For the following use cases**

- Balanced panels, unbalanced panels & repeated cross-section
- Two + Multiple time periods
- Fixed + Staggered treatment timing
- Binary + Multi-Valued treatment
- Heterogeneous treatment effects & triple difference
- One + Multiple treatments per entity

see the [Documentation](https://differences.readthedocs.io/en/latest/) for more details.

## Installing

The latest release can be installed using pip

```bash
pip install differences
```

requires Python >= 3.8

## Quick Start

### ATTgt 

the ATTgt class implements the estimation procedures suggested by [Callaway and Sant'Anna (2021)
](https://www.sciencedirect.com/science/article/abs/pii/S0304407620303948), [Sant'Anna and Zhao 
(2020)](https://www.sciencedirect.com/science/article/abs/pii/S0304407620301901) and the 
multi-valued treatement case discussed in [Callaway, Goodman-Bacon & Sant'Anna (2021)](https://arxiv.org/abs/2107.02637)

```python
from differences import ATTgt, simulate_data

df = simulate_data()

att_gt = ATTgt(data=df, cohort_name='cohort')

att_gt.fit(formula='y')

att_gt.aggregate('event')
```

*differences* ATTgt benefitted substantially from the original authors' R packages: Callaway & Sant'Anna's [did](https://github.com/bcallaway11/did) and Sant'Anna and 
Zhao's [DRDID](https://github.com/pedrohcgs/DRDID)

### TWFE

```python
from differences import TWFE, simulate_data

df = simulate_data()

att_gt = TWFE(data=df, cohort_name='cohort')

att_gt.fit(formula='y')
```
