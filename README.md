# σ-LEM – Analytical Local Effect Model for AuNP Radiosensitisation
[![arXiv](https://img.shields.io/badge/arXiv-2506.06671-b31b1b.svg)](https://arxiv.org/abs/2506.06671)  
[![Python](https://img.shields.io/badge/python-3.9%2B-blue)](#)  
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.15734277.svg)](https://doi.org/10.5281/zenodo.15734277) 
> Reference implementation & reproducibility notebooks for  
> **“An analytical model for gold nanoparticle radiosensitisation”**  
> P. Teles, *arXiv : 2506.06671 (2025)*  

---

## Overview
`σ-LEM` provides a **closed-form, variance-driven Local-Effect Model** that eliminates Monte-Carlo voxel scoring.  
Key equations (Eqs. 9–37 of the paper) are implemented exactly as printed — including  
* variance-only,  
* variance + mixed term, and  
* full 2nd-order σ² models —  
plus the truncated-Gaussian correction for negative-dose tails (Eq. 27).

All figures, tables and numerical values in the manuscript can be re-generated with the notebooks below.

---

## Repository layout
```text
sigma_lem/                      # core Python functions (model, fitting, utils)
notebooks/
 ├─ K_c.ipynb                   # Fig. 2 & Tables 2-3 (K_c vs energy)
 ├─ Survival_curves-truncated.ipynb   # Fig. 3-4, survival curves w/ truncation
 ├─ DEF80-truncated.ipynb       # DEF_80 calculations (Tab. C.6-C.8)
 └─ FIT_results-truncated.ipynb # α′, β′ fits (Tab. 4-5)
LICENSE                         # GPL v3
CITATION.cff                    # citation metadata
requirements.txt                # tested package versions
README.md                       # you are here


### Tested versions

| Package    | Version |
|------------|---------|
| numpy      | 1.26 |
| scipy      | 1.12 |
| matplotlib | 3.9 |
| jupyter    | 1.0 |
| tqdm       | 4.66 |

*(Python ≥ 3.9; other 3.x versions should work but are untested.)*

---

## Quick start

```bash
# interactive notebook
jupyter notebook notebooks/K_c.ipynb

# or, non-interactive full reproduction
python -m sigma_lem.demo   # recreates all manuscript numbers in <60 s
```

---

## Reproducibility checklist

| Manuscript item                           | Notebook / script                   | ✓ SHA-256 check |
|-------------------------------------------|-------------------------------------|-----------------|
| Fig. 2 – \(K_\mathrm{c}(E)\) curve        | `K_c.ipynb`                         | ✓ |
| Tables 2–3 – \(K_\mathrm{c}\) values & DER| `K_c.ipynb`                         | ✓ |
| Figs. 3–4 – σ, σ + mixed, σ² models       | `Survival_curves-truncated.ipynb`   | ✓ |
| DEF\_80 hierarchy (Tab. C.6–C.8)          | `DEF80-truncated.ipynb`             | ✓ |
| α′ / β′ fits (Tab. 4–5)                   | `FIT_results-truncated.ipynb`       | ✓ |

All notebooks were last executed against commit `<hash>`  

---

## Citing this work

If you use the code or model, please cite **both** the software release and the
pre-print:

```bibtex
@software{teles_sigmaLEM,
  author       = {Pedro Teles},
  title        = {{σ-LEM}: Log-normal Analytical Local Effect Model},
  version      = {v1.0.2},
  date         = {2025},
  doi          = {10.5281/zenodo.15734277},  
  url          = {[https://github.com/PedroTelesFCUP/sigma-LEM]}
}

@article{teles_2025,
  author  = {Pedro Teles},
  title   = {An analytical model for gold nanoparticle radiosensitisation},
  journal = {arXiv e-prints},
  year    = {2025},
  eprint  = {2506.06671},
  url     = {https://arxiv.org/abs/2506.06671}
}
```

---

## License

Distributed under the **GPL v3** licence.  
See [`LICENSE`](LICENSE) for the full text.

---

## Contributing

Pull requests with bug fixes, additional test cases, or new beam-quality data are
welcome.  
Please open an issue first to discuss major changes.

---

## Contact

Pedro Teles – ppteles@fc.up.pt  
