# MF-GC-network-backprop-public

This is the code (and some data) necessary to reproduce all major figures for Cayco-Gajic, Clopath & Silver 2017, "Sparse synaptic connectivity is required for decorrelation and pattern separation in feedforward networks." A simplified version of the biophysical model is available in the standalone folder osb_model. See also: http://www.opensourcebrain.org/projects/grclayer-caycogajic2017

### Getting started
In general, Matlab code are designed to be run locally and python code to be run on a cluster. All simulations require defined network connectivities and input statistics saved in .mat or .pkl files. Examples have been provided, but see below to change them.

### Simulations
For the analytical model, simulations are done within the .m plotting files, or within the .py file for backpropagation. On the other hand, the biophysical model must be simulated on a cluster prior to analysing the patterns using the following script:
```
biophysical_model/run_mf_grc_network.py
```
This saves the GC and MF spike times as .dat files for each simulation. To save memory and analyse further, after finishing the simulations run
```
biophysical_model/save_samples_as_txt.py
```
to convert the spike times to spike count activity patterns, and remove the .dat files. Note that simulating the biophysical model requires NeuroML2 and pyNeuroML: https://github.com/NeuroML/pyNeuroML

### Analysis
Activity pattern properties (variance, covariance, population sparseness) can be computed using the following code:
```
analytical_model/get_var_cov.m
```
or
```
biophysical_model/get_cov_randompatterns.py
```

To run backpropagation, use either:
```
analytical_model/test_mf_grc_backprop.py
```
or
```
biophysical_model/test_mf_grc_backprop_biophys.py
```

For the analytical model, the .m files above will automatically produce relevant plots. For the biophysical model, after running the above .py files, use:
```
biophysical_model/analyze_simulated_data.m
```

### Additional information
The folder grc_lemsDefinitions includes NeuroML2 and XML files necessary to run the biophysical model.

To generate new network connectivities, use network_structures/GCL_make_connectivity.py

To change input statistics, use input_statistics/generate_input_patterns.m.  This requires the Dichotomized Gaussian tools from the Macke Lab in order to generate spike trains with arbitrary correlations. See: https://bitbucket.org/mackelab/pop_spike/src

