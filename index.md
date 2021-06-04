# Data Description

This project is to provides an analysis on the numerical modeling of a small-scale wave energy converter (WEC).
A crucial step in the design process of WECs is the numerical modeling.
With large-scale modeling, frequency domain modeling is typically used. 
This calculates the hydrodynamic coefficients of WEC bodies using linear wave theory. 
The benefits to using frequency domain modeling is that it has a relatively low computational cost. 
With small-scale WECs, frequency-domain modeling may not accurately represent the nonlinear interactions the small-scale WEC might experience in a range of wave conditions. 
This is due to the relative size of the small-scale WEC and its interactions with incoming waves of the same magnitude as the large-scale WEC. 
Linear wave theory will not always apply to smaller WECs, which is why time-domain modeling might be the better option when designing small-scale WECs. 
The goal of this project is to understand if frequency-domain modeling can be used with a small-scale WEC by comparing the performance of three different hull-shapes for a two-body point absorber WEC. 

*Data Types:* 

- Input files
  - Files that provide information on the models. The information in these input files include the WEC configuration information, environmental conditions, wave parameters, and control information. Most of these files are in the file format .ini which is the input format for the ProteusDS software used to model the WECs.
-	Output/results
    - The outputs from ProteusDS are compiled into one Results folder for a simulation run. All of the output files written in ASCII characters and can be read in any text editor. The outputs of interest for this project include the 6-degrees of freedom linear and rotational responses which include: positions [m], velocities [m/s], and accelerations [m/s2] of the WEC bodies. Other outputs from each simulation include information on the incoming waves, like sea height [m], sea pressure [Pa], sea current [m/s]
-	Post-processing scripts
    - As described above, the goal of this project is to investigate the difference in modeling a small-size WEC with frequency-domain analysis compared to a time-domain analysis. The post-processing scripts read the output files and plot the root-mean-squared (RMS) velocity against the RMS wave height. 
-	Data visualization
    - The post-processing scripts described above produce figures that display the post-processing results of the modeling comparison. 

*Data Collection:*

As mentioned above, the numerical simulations for this project are carried out through the software ProteusDS. Proteus is use for the nonlinear time-domain modeling in this study. Proteus models the dynamic responses of offshore structures with a semi-empirical multibody dynamic model. Hydrodynamic loading is calculated using the Morrison method from prescribed meta-ocean conditions. 

*Data Size:*

Each Result file generating in Proteus depends on the length of the simulation and the WEC configuration complexity. For this project, each results folder is approximately 50 MB. Because this project is comparing different numerical modeling configurations the total size of the data will be approximately 1.7 GB.


# Roles and Responsibilities 

This research is supported in part by an appointment with Marine and Hydrokinetic Graduate Student Research Program sponsored by the U.S. Department of Energy (DOE), Office of Energy Efficiency and Renewable Energy, and Water Power Technologies Office. This program is administered by the Oak Ridge Institute for Science and Education (ORISE) for the DOE. ORISE is managed by ORAU under DOE contract number DESC0014664.

The graduate student taking part in the ORISE program is responsible for the implementation of the data management plan (DMP). There are no official requirements from the Water Power Technology Office (WPTO) that oversees these graduate appointments other than reporting back findings from the research conducted on this fellowship. The graduate student holds ownership in the data being collected for the project. 

The graduate student holds most of the responsibilities when it comes to data collection/data generation, data organization, metadata generation, quality control, data analysis, access control, and DMP implementation. The two PI’s overseeing the project share responsibilities with the data analysis and the metadata generation. Data ownership of the project would transfer over to

Because a majority of the data management responsibilities are on the graduate student participating in this fellowship, if that student was to leave the project, the data would likely fall to either of the PIs. The graduate student would be in charge of ensuring all of the scripts and model input files are on the Github respository and any data collected from simulations is transfered to the PI's if the data is not yet on the publically available respository. Thourough README files will also be required in the Github repository to help describe the metadata as well as giving information on how to use the scripts and model input files to ProteusDS. 


# Data Standards and Metadata

The data plan includes three types of data. The plan is based on the NSF data management plan for engineers which can be found here. As mentioned previously, there are no formal data management requirements. GitHub will be used to help with version control of the model inputs and scripts that are created for data visualization. The plan to document these are as follows:

- *Dataset 1:* Model inputs. The inputs for the model are used to generate the model within the ProteusDS (PDS) software. The data for these inputs includes all relevant information to model the wave energy converter (WEC). All parameters and variables are labelled within the PDS input file structure. Within the PDS GUI, detailed descriptions of each parameter/variable are included as well as the units for the variables. For these input files, all model information for the different model setups remain the same other than the ocean wave parameters in the environmental.ini input file. For this reason, the naming convention for the input file folders are named based on the way the model inputs are set up. In this dataset there are three different model configurations all modeled with PDS: the fully linear model, the non-linear model, and the hybrid model setup. With each of these varying setups, there are also three different WEC hull-shapes being assessed. The folders compiling the model inputs for these three different setups and three different hull-shapes are recorded as follows: HullShape_model_type_YYYYMMDD. 

  As mentioned before, the folders for the model inputs include all of the PDS input files which are as follows:
    -	Environmental.ini
    -	Simulation.ini
    -	Rigid_body_1.ini
    -	Rigid_body_2.ini
    -	Cable.ini
    -	PTO.ini
    -	HullShape_model.pds (GUI file)

-	*Dataset 2:* Model outputs. The model outputs when run through the software, are created within the main folder. When completing a single simulation, the folder with the outputs are compiled in a folder called Results. These result folders are renamed after each run to describe the wave conditions modeled in the simulation. The format for these folder names are Results_HullShape_modeltype_waveperiod_waveheight_YYYYMMDD. After simulations are complete these are copies over to result folders that compile the results of each hull-shape into the same folder for easier post-processing in Matlab. All of the files in the results folder are tabular text-based .dat files with metadata information in the headers to describe the variables in the files. I will include a README.md file in each compiled result folder for the different hull-shapes to further explain the naming convention of the sub-result folders in the folder.

-	*Dataset 3:* Post-processing scripts. The final dataset includes the Matlab scripts that analyze the output files from the PDS simulations. The names of these files describe the type of analysis being completed and are thoroughly commented. Most scripts included are creating labeled data visualizations which will be saved as both Matlab figures and .png files. 


# Storage and Security 

The dataset is neither sensitive or confidential for this project. The data being generated is based on simplistic wave energy converter models that can be recreated with knowledge of the model setup from the metadata generation. The data’s storage plan is the responsibility of the graduate student. To ensure the proper backup of the data collected through the numerical modeling, the data is stored on the graduate student’s box drive. Scripts and input files for the numerical models are managed through Github to ensure updates in code/files are stored properly through version control. 


# Access and data sharing 

There are no factors that limit the availability to share the data. As previously mentioned, the data being collected is not sensitive or confidential. The model input files, scripts, and post-processing data available via GitHub during the research process to track the code versions and any figures/data produced from the post-processing. The post-processing scripts are written in Matlab. The model input files are .ini file-type as required by Proteus, but are text-based files and can be opened by anyone without the software. The GitHub repository will have a CC-BY license. This gives others the ability to distribute, remix, adapt, and build on the work in the GitHub repository as long as the original work is properly cited.  The results from the numerical simulations will not be available in GitHub due to the large data size associated with running large number of simulations with different model configurations. 

# Archiving and preservation 

As previously mentioned, there are no requirements for data management or data preservation for this project. The data managers of this project will, however, compile the data from the numerical simulations and submit it to the Marine Hydrokinetic Data Repository (MHKDR) that is operated through the DOE. Based on the information from this online repository, there isn’t a specific timeframe that the data will be available for in the repository. There is an option to postpone public access for up to five years in this repository to provide research groups and developers time to publish work or advance their technology.   

The submission process for the MHKDR does not have any strict guidelines for submitting. They highly encourage large datasets to be zipped. There are no limits to the file size or the number of files uploaded for a single submission. Submitters are able to save progress to their submission up until they are ready to formally submit. Changes can be made until the dataset is publicly available. 


