# GRAD521_DMPMankle_2021

#Context Of the Project for this DMP:

To date, ocean wave energy research has largely focused on the design, optimization, and testing of utility-scale wave energy converters (WECs). The main challenge with designing and implementing this technology into grid systems is the cost. One avenue to innovate wave energy technology without the large costs of the grid-scale technology is to research the design process of a small-scale WEC and how the process may differ from the large-scale technology. A crucial step in the design process of WECs is the numerical modeling. With large-scale modeling, frequency domain modeling is typically used. This calculates the hydrodynamic coefficients of WEC bodies using linear wave theory. The benefits to using frequency domain modeling is that it has a relatively low computational cost. With small-scale WECs, frequency-domain modeling may not accurately represent the nonlinear interactions the small-scale WEC might experience in a range of wave conditions. This is due to the relative size of the small-scale WEC and its interactions with incoming waves of the same magnitude as the large-scale WEC. Linear wave theory will not always apply to smaller WECs, which is why time-domain modeling might be the better option when designing small-scale WECs. 

The goal of this project is to understand if frequency-domain modeling can be used with a small-scale WEC by comparing the performance of three different hull-shapes for a two-body point absorber WEC. The three hull shapes used in this study are a cylinder, a sphere, and a truncated pyramid. We wanted WEC hull-shapes with increasing complexity to better understand the limitations of using frequency-domain modeling. In this project two different modeling tools are being used. The first is the frequency-domain, boundary element method solver, NEMOH, which calculates the hydrodynamic coefficients of the different point-absorber configurations. The second is a time-domain modelling software ProteusDS. In this comparison there are three different sets of data being compared for each of the three hull shapes. All three datasets for the three hull shapes include various responses from a simulation run through ProteusDS. The outputs of interest for this project include the 6-degrees of freedom linear and rotational responses which include: positions [m], velocities [m/s], and accelerations [m/s2] of the WEC bodies. Other outputs from each simulation include information on the incoming waves, like sea height [m], sea pressure [Pa], sea current [m/s]. 

The first dataset category is the frequency domain model that uses NEMOH to calculate the linear buoyancy and the hydrodynamic coefficients of the point absorber WEC. The hydrodynamic coefficients can then be imported into a Proteus model and used to run a simulation of the WEC using the linear frequency domain information. In this case, Proteus is just being used as a post-processing tool to output the frequency-domain data in the time domain for comparison. The second dataset category is the time domain model that calculates all of the required outputs in Proteus. In this dataset the WEC buoyancy calculation is non-linear. This is also used to calculate the hydrodynamic coefficients of the WEC within Proteus. The third category is a hybrid simulation where Proteus calculates the non-linear buoyancy and the NEMOH generated hydrodynamic coefficients are used for the simulations. For this project, each dataset is comprised of the outputs from a 60-second simulation where the data was collected each 0.01 second. We also are comparing three different wave conditions, all with the same wave period of 4 seconds. The wave heights increase from 5 cm to 10 cm and finally 20 cm. Each dataset includes N-number of folder from each simulation for three different hull shapes and the three different wave conditions.  For each dataset category there is approximately 3.4 GB of data files. 

One of the results we’ll being using in the comparison between the three datasets is the power performance of the two-body point absorbers. That is calculated using the velocities of the bodies and the damping coefficient of the power take off (PTO) unit. The PTO in this project is modeled as a linear spring-damper system. With WEC technology, there is an optimal value of the damping coefficient before the power performance of the WEC starts to decrease. Another result we will likely use is the relative motion of the point-absorbers for the different datasets. By investigating a range of wave heights, we should see more instabilities in the relative motions with the frequency domain modeling as the wave heights increase. This is because the non-linear interactions with the WEC and the waves will increase as the wave heights increase. All data from the simulations will be analyzed using MATLAB. A majority of the data will be representing using figures. The power performance of each dataset and for each hull-shape will be represented as both power curves and power over time. The power curves indicate the mean power performance of each damping coefficient values for a given shape and wave condition. The relative velocity and relative positions will also be represented in figures. If any further detail is needed for a specific output, a table of values may be created for better clarity. 
