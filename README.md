# Network nonlocality with tripartite entangled sources

Companion code for the paper

> **Network nonlocality with tripartite entangled sources**
> Sudip Chakrabarty (S. N. Bose National Centre for Basic Sciences, Kolkata, India) and
> Amit Kundu (The Institute of Mathematical Sciences, Chennai, India)

The Jupyter notebook in this repository reproduces every number, table entry and figure of the paper. Each step is explained in a text cell that names the equation, theorem or appendix it belongs to, and the notebook follows the order of the paper.

## About the paper

Quantum networks are built from independent sources. Their nonlocality has mostly been studied with sources that emit entangled pairs. The paper considers sources that emit three entangled qubits, whose nonlocality can be tested either by the Mermin inequality or by the stronger Svetlichny inequality. It asks how network nonlocality is related to these two single-source notions.

The answer depends on how the sources are wired:

- **Closed network.** Two central nodes without inputs share every source. With Bell-state measurements, every state that violates the Svetlichny inequality also violates the network inequality with two copies. All entangled generalized GHZ states violate the network inequality as well, so Svetlichny nonlocality is sufficient but not necessary.
- **Open network.** A single central node is shared. With a Bell-state measurement, a network violation requires a Mermin violation of the source. GHZ sources reach the algebraic maximum.
- **Many sources.** When the central nodes have no inputs, the maximal violation of these two-correlator inequalities depends on whether the number of sources is even or odd. The paper gives tight bounds for both cases.

## Contents

| File | Description |
|---|---|
| `network_nonlocality_tripartite.ipynb` | The notebook, saved with all outputs and figures |
| `fig1_networks.pdf` | Fig. 1, the closed and open networks |
| `fig2_hierarchy.pdf` | Fig. 2, generalized GHZ states and critical visibilities |
| `fig3_random.pdf` | Fig. 3, Theorems 2 and 3 checked on random states |
| `fig4_swapping.pdf` | Fig. 4, network value and CHSH value of the swapped state |
| `fig5_parity.pdf` | Fig. 5, the parity effect |

## Structure of the notebook

| Part | Paper | What is computed |
|---|---|---|
| 0 | Fig. 1 | Schematic of the networks |
| 1 | Sec. II | Pauli matrices, states, correlation tensor, Mermin and Svetlichny values |
| 2 | Sec. III A, App. A | Local bounds (Theorem 1, Proposition 3) tested on random hidden-variable models |
| 3 | Sec. III B, App. B | Closed-network value (Proposition 1), checked against a direct six-qubit calculation |
| 4 | Sec. III C–D | Theorem 2, the GHZ, generalized GHZ, W and biseparable examples, the table of values |
| 5 | Sec. III–V | Open-network value, random-state checks of Theorems 2 and 3, Figs. 2 and 3 |
| 6 | Sec. IV, App. F | Entanglement swapping through two central nodes (Proposition 2), noise, Fig. 4 |
| 7 | Sec. V, App. D | Open network: the value 2 for GHZ sources, Theorem 3, biseparable examples |
| 8 | Sec. VI, App. E | Parity effect (Theorem 4), optimal strategies, tripartite swapping, Fig. 5 |

## Requirements

- Python 3.9 or later
- `numpy`, `scipy`, `matplotlib`
- `jupyter`, to run the notebook

Install with

```bash
pip install numpy scipy matplotlib jupyter
```

## Running

```bash
jupyter notebook network_nonlocality_tripartite.ipynb
```

Then run all cells in order. A full run takes about 7 minutes on a laptop, and the five figures are written as PDF files to the working directory. All random numbers use fixed seeds, so the output is reproducible.

## Notes on the numerics

- The analytical results of the paper do not rely on numerics. The computations serve as consistency checks and supply the values marked as numerical in the paper.
- Maxima are found by multistart local optimization (Nelder–Mead, BFGS or L-BFGS-B, from many random starting points). They are therefore lower bounds on the true maxima, and the corresponding critical visibilities are upper bounds.
- The random states used for Fig. 3 are not drawn uniformly from any standard measure. They are a consistency check, not evidence for the theorems.

## Citation

If you use this code, please cite the paper. Citation details will be added on publication.

## Contact

Sudip Chakrabarty, sudip27042000@gmail.com
Amit Kundu, amit8967@gmail.com
