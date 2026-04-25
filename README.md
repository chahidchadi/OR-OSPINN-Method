# Optimized Schwarz PINNs for Fourth-Order PDEs

This repository contains cleaned Google Colab notebooks for experiments with Optimized Schwarz Physics-Informed Neural Networks (OR-OSPINNs), monodomain PINNs, and local/nonlocal approximations of optimal transmission operators.

The notebooks are organized so that results can be inspected directly on GitHub or in Colab without rerunning the expensive training cells. Most notebooks include the original outputs and figures.

## Quick Navigation

### Example 1: Symmetric and Asymmetric Decomposition

| Notebook | Purpose |
| --- | --- |
| [Example_1_symmetric_decomposition_cleaned_commented_with_outputs.ipynb](Example_1_symmetric_decomposition_cleaned_commented_with_outputs.ipynb) | Example 1 with symmetric domain decomposition, convergence plots, displacement reconstruction, and seed statistics. |
| [Example_1_asymmetric_decomposition_cleaned_minimal_comments_with_outputs.ipynb](Example_1_asymmetric_decomposition_cleaned_minimal_comments_with_outputs.ipynb) | Example 1 with asymmetric domain decomposition, Y-PINN reconstruction, paper-table comparisons, and robustness across seeds. |

### Example 2: Symmetric and Asymmetric Decomposition

| Notebook | Purpose |
| --- | --- |
| [Example_2_symmetric_decomposition.ipynb](Example_2_symmetric_decomposition.ipynb) | Example 2 with symmetric decomposition, 3D visualizations, displacement reconstruction, and seed statistics. |
| [Example_2_asymmetric_decomposition.ipynb](Example_2_asymmetric_decomposition.ipynb) | Example 2 with asymmetric decomposition and multi-seed convergence analysis. |
| [Example_2_OR_OSPINN_vs_CFD_CBSQI_and_DQM.ipynb](Example_2_OR_OSPINN_vs_CFD_CBSQI_and_DQM.ipynb) | Comparison of OR-OSPINN against CFD, CBSQI, and DQM reference methods. |

### Monodomain PINN vs OR-OSPINN

| Notebook | Purpose |
| --- | --- |
| [MonoDomain_PINN_vs_OR_OSPINN.ipynb](MonoDomain_PINN_vs_OR_OSPINN.ipynb) | Compares single-domain PINN baselines with OR-OSPINN configurations. |

### Local vs Nonlocal Transmission Operators

These notebooks compare the nonlocal optimal transmission operator approximation with local approximations of orders 0 through 4.

| Notebook | Time Horizon |
| --- | --- |
| [Local_vs_Nonlocal_optimal_operators_approximation_T1.ipynb](Local_vs_Nonlocal_optimal_operators_approximation_T1.ipynb) | `T = 1` |
| [Local_vs_Nonlocal_optimal_operators_approximation_T2.ipynb](Local_vs_Nonlocal_optimal_operators_approximation_T2.ipynb) | `T = 2` |
| [Local_vs_Nonlocal_optimal_operators_approximation_T3.ipynb](Local_vs_Nonlocal_optimal_operators_approximation_T3.ipynb) | `T = 3` |
| [Local_vs_Nonlocal_optimal_operators_approximation_T4.ipynb](Local_vs_Nonlocal_optimal_operators_approximation_T4.ipynb) | `T = 4` |

### Robustness Study

| Notebook | Purpose |
| --- | --- |
| [Robustness_to_Decomposition_and_Sampling.ipynb](Robustness_to_Decomposition_and_Sampling.ipynb) | Tests robustness with respect to decomposition and sampling choices. |

## Suggested Reading Order

1. Start with `Example_1_symmetric_decomposition...` to understand the main OR-OSPINN workflow.
2. Move to `Example_1_asymmetric_decomposition...` to see how the method behaves under asymmetric decomposition.
3. Read the Example 2 symmetric/asymmetric notebooks for the second manufactured solution.
4. Use the monodomain comparison notebook to compare OR-OSPINN with a standard PINN baseline.
5. Study the local-vs-nonlocal operator notebooks to compare transmission-operator approximations across time horizons.
6. Finish with the robustness notebook to see sensitivity to decomposition and sampling.

## Notebook Style

The cleaned notebooks follow a consistent presentation format:

- Markdown cells explain the purpose of each major section.
- Code cells keep only a Colab title and one short purpose comment.
- Decorative and repeated comments were removed.
- Original outputs and figures were preserved where available.
- Empty separator cells were removed.

## Running the Notebooks

The notebooks were designed for Google Colab.

Typical dependencies:

```python
torch
numpy
matplotlib
pandas
IPython
```

Most notebooks can be inspected without rerunning because outputs are saved inside the `.ipynb` files. If you rerun training cells, GPU runtime is recommended.

## Reproducibility Notes

- Most training experiments use seed `1234`; multi-seed notebooks also include seeds such as `123`, `12`, and `1`.
- Several notebooks store raw training logs inside notebook cells, allowing convergence plots to be regenerated without rerunning training.
- Checkpoints are usually written to a local `checkpoints/` directory inside the Colab runtime.
- Some reconstruction cells expect trained `z1`/`z2` models or checkpoint files from previous cells.

## Naming Convention

Notebook filenames include:

- `Example_1` or `Example_2`: manufactured-solution case.
- `symmetric` or `asymmetric`: domain decomposition type.
- `OR_OSPINN`, `MonoDomain`, `Local_vs_Nonlocal`: experiment family.
- `T1`, `T2`, `T3`, `T4`: final time horizon for local/nonlocal operator comparison.



