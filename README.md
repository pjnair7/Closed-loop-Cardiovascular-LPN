# Closed-loop Cardiovascular LPN

This repository contains **lumped parameter models (LPN)** of the cardiovascular system developed in **MATLAB Simulink**. These models are based on the work by **Broomé et al.** ([PubMed](https://pubmed.ncbi.nlm.nih.gov/23842033/)) and have been specifically tuned to represent **patients diagnosed with aortic coarctation**. The tuning is based on **non-invasive and invasive measurements** (e.g., catheterization reports).

The details of this work are part of a research study. The publication outlining the study is available at:  
[**DOI**](https://doi.org/10.1115/1.4068716)

---

## Repository Structure  

Each folder corresponds to a specific patient case and contains:  
- **`.slx` file** – The Simulink model of the cardiovascular system.  
- **`.mat` file** – The parameter set required to run simulations.  

---

## Running a Simulation  

1. Open **MATLAB** and navigate to the folder corresponding to the desired patient case.  
2. Load the `.mat` file into the workspace using:  

   ```matlab
   load('filename.mat')
3.	Open the .slx file in Simulink.
4.	Press Ctrl + D to update the model.
5.	Adjust the simulation time (top pane: “Stop Time”):
	•	Set a specific duration
	•	Use Inf to run indefinitely
6.	Press Ctrl + T to start the simulation.

Once a simulation has run, the output data is saved in the MATLAB workspace as a struct file named **`out`**

## Physiological State Adjustments

Each model is tuned for the patient’s resting state, but parameters for exercise conditions (up to 2× cardiac output (CO)) are available. These can be found in a table within the .slx file.

## Switching to Exercise State:

To modify the physiological state, update the parameters in “Manual Control Panel” with those provided in the table.

## Automated Parameter Tuning

Certain parameters can be dynamically adjusted:

### SVR/PVR Control
- The toggle for SVR control or PVR control dynamically adjusts the radii of the peripheral arteries to reach the target systemic vascular resistance (SVR) or pulmonary vascular resistance (PVR).
- The target values are set in the “SVR Target” box.
- The actual values are displayed in “SVR Measured”.

### SAP/DAP or SPP/DPP Control
- This control adjusts systemic or pulmonary compliance to match the desired pulsatility.
- Pulsatility is defined by the systolic/diastolic systemic or pulmonary pressure.

## Experimental Features (Not Recommended for Use)
UVV Control, SLVP Control, and SRVP Control are still under development. Their use is not recommended. Do not turn “Open Loop” on.
