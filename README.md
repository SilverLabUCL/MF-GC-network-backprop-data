# MF-GC-network-backprop-data

This repo contains pre-simulated data necessary to reproduce all major figures for Cayco-Gajic, Clopath & Silver 2017, "Sparse synaptic connectivity is required for decorrelation and pattern separation in feedforward networks." 

Note that throughout the data, “_rX” indicates correlation radius (sigma) of X, so that r0 indicates independent inputs, r5 indicates spatial correlations of 5 microns, etc. Similarly, “_shuff” indicates that the GC activity patterns have been partially shuffled, and in ``results_bp_th``, “_rX_Y” indicates sigma of X and threshold of Y.

Includes:
* In ``network_structures``: 
  * Generated network connectivities and MF rosette/ GC positions (e.g. ``GCLconnectivity_4.pkl``)
* In ``input_statistics``:
  * Generated input statistics for varying spatial correlations (e.g. ``mf_patterns_r0.mat``)
* In ``biophysical model``: 
  * Initialized parameters for cluster array job (e.g. ``params_file.pkl``)
  * Variance and covariance of pre-simulated activity patterns (e.g. ``data_r0/grc_cov_biophys_r0.mat``)
  * Population sparseness of pre-simulated activity patterns: (e.g. ``data_r0/grc_spar_biophys_r0.mat``)
  * Error from backpropagation training  (e.g. ``data_r0/grc_bp_biophys_r0.mat``)
* In ``analytical model``: 
  * Error from backpropagation training (e.g. ``results_bp/grc_toy_r0.mat``)

This repo only contains data. For necessary scripts, see: https://github.com/SilverLabUCL/MF-GC-network-backprop-public

Warning before you clone: This repo is ~2Gb.
