08.08.2022 @Soufiane Karmouche (SK), Institute of Enviromental Physics (IUP), University of Bremen

- This repository presents a sample of the regime-oriented causal model evaluation (CME) in the form of jupyter notebooks. The main set of code is used to produce most of the figures on the paper "karmouche22copernicus_CME_CMIP6" 

## **INTRUCTIONS**


> ##### environment.yml: Python packages and libraries used in every notebook (see Imports in top of every notebook).
The user can use: `conda env create -f environment.yml` for creating the environment.

> ### To be able to run the regime-oriented CME using PCMCI+, the TIGRAMITE package should be installed. It is the User’s responsibility to perform the installation. 

> #### To install the TIGRAMITE, please follow instructions: [here](https://github.com/jakobrunge/tigramite)

> #### Once this is done, remove the comment sign (#) from the import commands (see Imports cell top of every notebook) before running

## **DIRECTORIES**


 > ##### **DATA** 
 Directory containing the sample data used in this repository: Two Reanalysis datasets (for sea surface temperature and sea level pressure) for reference and two CMIP6 models (five realizations each). These are selected from the original CVDP-LE results found as NetCDF files under: https://www.cesm.ucar.edu/working_groups/CVC/cvdp-le/data-repository.html

 > ##### **Results_DIR** 
 Directory containing the sample results obtained by running the notebooks.


## **MAIN FILES**

The main code is contained in the following files:

> ##### Spatial_correlation.ipynb: 
This is a sample of the methodology followed in section 3.1 (Figure 4b) of the paper. Used to compute the Person r correlations between the observed regressed spatial patterns of AMV,PDV, PNA and PSA1 to those from CMIP6 simulations.

> ##### OBS_CMIP6_pcmciplus.ipynb: 
Regime-oriented causal anaylsis using PCMCI+ from reanalysis data (OBS) and two (for simplicity) CMIP6 Large Ensemble (LE) models with five simulations. The user can choose to extend the list of CMIP6 LEs used. (Figure 5)

> ##### F1_score.ipynb: 
Requires results from OBS_CMIP6_pcmciplus.ipynb. To compute the F1-scores translating the similarity between the observed causal networks (from reanalysis data) to those from CMIP6 simulations for all regimes. (Figure 8a and Figure 9)



### PS:
 This is a Work in Progress (WIP) and is yet to be finalized



## **REFERENCES**:

> [Phillips, A. S., C. Deser, J Fasullo, D. P. Schneider and I. R. Simpson, 2020: Assessing Climate Variability and Change in Model Large Ensembles: A User’s Guide to the “Climate Variability Diagnostics Package for Large Ensembles”, doi:10.5065/h7c7-f961](https://opensky.ucar.edu/islandora/object/manuscripts:1001)

> [PCMCI+: J. Runge (2020): Discovering contemporaneous and lagged causal relations in autocorrelated nonlinear time series datasets. Proceedings of the 36th Conference on Uncertainty in Artificial Intelligence, UAI 2020,Toronto, Canada, 2019, AUAI Press, 2020.](http://auai.org/uai2020/proceedings/579_main_paper.pdf)
