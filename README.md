# Data for “Braiding Majorana Zero Modes in a Number-Conserving Hubbard Trijunction”

This repository contains precomputed numerical data and Jupyter notebooks for selected plots in the paper. The notebooks read the `.npz` archives in `data/` and use `aps.mplstyle`; existing PDF plots are in `figures/`. The numerical simulations that produced the archives are not included.

## Figure and data guide

| Paper figure | Data file(s) | Arrays in each archive | Plotting notebook |
| --- | --- | --- | --- |
| Fig. 1(c), energy levels in conserved sectors | `data/fig1c_sector_energy_levels.npz` | `level_list`, `p_values` | `plot_fig1_sector_energy_levels.ipynb` |
| Fig. 3(a), spectrum during braiding | `data/fig3a_braiding_energy_levels.npz` | `times`, `E_t` | `plot_fig3_braiding_dynamics.ipynb` |
| Fig. 3(b), braiding phase | `data/fig3b_braiding_phase_series_01.npz` through `series_03.npz` | `times`, `braiding_phase` | `plot_fig3_braiding_dynamics.ipynb` |
| Fig. 3(c), final fidelity loss versus ramp time | `data/fig3c_fidelity_loss_vs_ramp_time.npz` | `T`, `alpha`, `loss_of_fidelity` | `plot_fig3_braiding_dynamics.ipynb` |
| Fig. 3(d), braiding error versus defect strength | `data/fig3d_braiding_error_vs_defect.npz` | `T`, `alpha`, `braiding_error` | `plot_fig3_braiding_dynamics.ipynb` |
| Fig. 4(b), adaptive-protocol spectrum | `data/fig4b_adaptive_energy_levels.npz` | `times`, `E_t` | `plot_fig4_adaptive_ spatial_shift.ipynb` |
| Fig. 5, phase diagram | `data/fig5_phase_diagram.npz` | `U1`, `U2`, `p_values` | `plot_fig5_phase_diagram.ipynb` |

Additional trajectories are provided in `data/braiding_fidelity_loss_time_series_01.npz` through `series_03.npz` (`times`, `loss_of_fidelity`) and `data/braiding_wavefunctions_series_01.npz` through `series_03.npz` (`times`, `psi_t_lists`). The fidelity-loss trajectories are plotted in the Fig. 3 notebook but are not a separate panel in the paper. The wavefunction archives are not loaded by the supplied plotting notebooks; `psi_t_lists` is an object array and requires `numpy.load(..., allow_pickle=True)` when read from this trusted repository.

`series_01`, `series_02`, and `series_03` identify the order used by the plotting notebook. Those individual archives do not contain an `alpha` field, so their filenames do not assign a defect strength. Where an archive does contain `alpha`, use that array to inspect the stored parameter values. The `T` array denotes the ramping-time scale τ in the Fig. 3(c,d) archives.
