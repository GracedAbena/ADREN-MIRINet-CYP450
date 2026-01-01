# ADREN-MIRINet-CYP450

**ADREN** (descriptor/fingerprint network) and **MIRINet** (molecular image network) for multi-isoform prediction of CYP450 inhibitors:
- CYP1A2, CYP2C9, CYP2C19, CYP2D6, CYP3A4

This repository contains:
- Modular PyTorch implementations for both models
- RDKit-based preprocessing (SMILES → 2D compound depictions, fingerprints)
- Training + evaluation scripts
- Config-driven experiments (YAML)
- Metrics: Acc, AUC, Sensitivity, Specificity, MCC, F1, Precision

> Note: MIRINet expects **compound images generated from SMILES** (RDKit 2D depictions), not arbitrary images.

---

## Repository Structure

```text
cyp_pred/
  README.md
  requirements.txt
  pyproject.toml
  train_adren.py
  train_mirinet.py
  evaluate.py
  configs/
    adren.yaml
    mirinet.yaml
  src/
    __init__.py
    constants.py
    utils/
      __init__.py
      seed.py
      checkpoint.py
    chemistry/
      __init__.py
      rdkit_image.py
      fingerprints.py
    data/
      __init__.py
      dataset.py
    nn/
      __init__.py
      losses.py
      metrics.py
    models/
      __init__.py
      common/
        __init__.py
        mlp_head.py
        pooling.py
      adren/
        __init__.py
        embedding.py
        attention_trmha.py
        blocks.py
        model.py
      mirinet/
        __init__.py
        chem_gelu.py
        se.py
        residual_cnn_block.py
        attention_srmha.py
        model.py
    training/
      __init__.py
      trainer.py
