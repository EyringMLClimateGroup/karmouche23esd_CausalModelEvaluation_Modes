08.08.2022 @Soufiane Karmouche (SK), Institute of Environmental Physics (IUP), University of Bremen

- This repository presents a sample of the regime-oriented causal model evaluation (CME) in the form of jupyter notebooks. The main set of code is used to produce most of the figures on the paper "karmouche22copernicus_CME_CMIP6" 



# **I. INSTALLATION**

#### **1.**  Clone the repository: 
    git clone https://github.com/EyringMLClimateGroup/karmouche22copernicus_CME_CMIP6

#### **2.**  Create conda environment from environment.yml:
    cd karmouche22copernicus_CME_CMIP6
    
    conda env create -f environment.yml
    
    conda activate causalenv

    cd ..

#### **3.** Install the TIGRAMITE package to use PCMCI+: please follow instructions: [here](https://github.com/jakobrunge/tigramite)
    git clone https://github.com/jakobrunge/tigramite.git

    cd tigramite   

    python setup.py install

    cd ..
     
**It is the User's responsibility to install TIGRAMITE**. Results of the paper have been produced using version: 5.0.1.17

After installing Tigramite in the conda environment, add environment to jupyter kernels:
    
    python -m ipykernel install --user --name=causalenv   
---------------


# **II. DOWNLOADING DATA**

#### The complete CVDP-LE diagnostic for the 1900-2014 historical CMIP6 comparison run can be found on: [CESM CVCWG CVDP-LE Data Repository](https://www.cesm.ucar.edu/working_groups/CVC/cvdp-le/data-repository.html)
#### -  Alternatively through command line:  
####     1. Download: 
    wget http://webext.cgd.ucar.edu/Multi-Case/CVDP-LE_repository/CMIP6_Historical_1900-2014/CMIP6_Historical_1900-2014.cvdp_data.tar
####     2. Extract: 
    tar -xvf CMIP6_Historical_1900-2014.cvdp_data.tar

After installing TIGRAMITE and downloading the data, it is time to slightly edit the jupyter notebooks before running them.

---------------


# **III. EDITTING JUPYTER NOTEBOOKS**

##### [OBS_CMIP6_pcmciplus.ipynb](../main/OBS_CMIP6_pcmciplus.ipynb): 
1. In the **first code cell** (Imports): **Remove the hashtag (#)** at the beginning of last **four** lines in the **Imports cell** (e.g. `from tigramite`...)
2. **Change the path_to_data** in Data PATH cell to where CMIP6_Historical_1900-2014.cvdp_data is saved.
##### [F1_score.ipynb](../main/F1_score.ipynb) and [Ensemble_graphs.ipynb](../main/Ensemble_graphs.ipynb): 
1. In the **first code cell** (Imports): **Remove the hashtag (#)** at the beginning of last line in the **Imports cell** (e.g. `from tigramite import plotting as tp`)
##### [Pattern_correlation.ipynb](../main/Pattern_correlation.ipynb): 
1. **Change the path_to_data** in Data PATH cell to where CMIP6_Historical_1900-2014.cvdp_data is saved.


---------------


# **IV. RUNNING JUPYTER NOTEBOOKS**
###### First create a directory where results will be saved:
    mkdir Results_DIR/

**We recommend running the notebooks in the order below:**      
(some notebooks require results from other notebooks)
   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**1. [Pattern_correlation.ipynb](../main/Pattern_correlation.ipynb)**        

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**2. [OBS_CMIP6_pcmciplus.ipynb](../main/OBS_CMIP6_pcmciplus.ipynb)**        

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**3. [F1_score.ipynb](../main/F1_score.ipynb)**       

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**4. [Ensemble_graphs.ipynb](../main/Ensemble_graphs.ipynb)**

---------------


# **V. RESULTS**
#####  Results from running the jupyter notebooks will be saved under the `Results_DIR/` directory
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; To refer to figures from the paper, please see [overview_figures](../main/overview_figures) to locate the notebook needed to produce a specific plot. 


---------------

# **REFERENCES**:

> [Phillips, A. S., C. Deser, J Fasullo, D. P. Schneider and I. R. Simpson, 2020: Assessing Climate Variability and Change in Model Large Ensembles: A User’s Guide to the “Climate Variability Diagnostics Package for Large Ensembles”, doi:10.5065/h7c7-f961](https://opensky.ucar.edu/islandora/object/manuscripts:1001)

> [PCMCI+: J. Runge (2020): Discovering contemporaneous and lagged causal relations in autocorrelated nonlinear time series datasets. Proceedings of the 36th Conference on Uncertainty in Artificial Intelligence, UAI 2020,Toronto, Canada, 2019, AUAI Press, 2020.](http://auai.org/uai2020/proceedings/579_main_paper.pdf)
