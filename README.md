# Data and analysis code from Pietto et al (PLOS ONE, 2018)
These are the data and analysis code from Pietto et al (PLOS ONE, 2018). Analysis were carried out using Matlab and [EEGLAB v13.5.4b](https://sccn.ucsd.edu/eeglab/index.php). Also, for the analysis of temporal correlations with Detrended Fluctuation Analysis (DFA) we used the function available [here](https://la.mathworks.com/matlabcentral/fileexchange/19795-detrended-fluctuation-analysis), and for the wavelet denoising we use the [EP_den package](https://www2.le.ac.uk/centres/csn/software/ep_den) (Centre for Systems Neuroscience, University of Leicester, UK). For further details please refer to Pietto et al (PLoS ONE, 2018).

This project is part of a larger collaboration between the Unidad de Neurobiología Aplicada (CEMIC - CONICET, Argentina; https://cemic.edu.ar/una.php/) and the Laboratorio de Inteligencia Artificial Aplicada (Instituto de Cs. de la Computación, Fac. de Cs. Exactas y Naturales, UBA - CONICET, Argentina; https://liaa.dc.uba.ar/). Our general goal is to study the influence of adverse environmental conditions on the organization and reorganization of the brain structure and function, and how it involves distinct neural systems at different levels of organization. Thus, we measure EEG in children from low socio-economic status contexts to evaluate the efficacy of interventions, aimed to enhance cognitive development in children facing unfavorable social conditions (see also Pietto ML, Kamienkowski JE, Lipina S "Electrophysiological approaches in the study of childhood poverty influence on cognition" (2017) book chapter in “Neuroscience and Social Science: The missing link” Springer Books).

# Experiments' code and Emotiv SDK's bindings for Python
Experiments' code and Emotiv SDK's bindings for Python are available in https://github.com/mathigatti/Emotiv-Experiments.

# How to cite us
#### Please, if you like it / use it cite us:
Pietto, M. L., Gatti, M., Raimondo, F., Lipina, S. J., & Kamienkowski, J. E. (2018). Electrophysiological approaches in the study of cognitive development outside the lab. Plos one, 13(11), e0206983.
#### And let us know!!
Marcos L. Pietto (marcos.pietto (arroba) gmail (dot) com)
Mathias Gatti (mathigatti (arroba) gmail (dot) com)
Federico Raimondo
Sebastian Lipina
Juan E. Kamienkowski (juank (arroba) dc (dot) com (dot) ar)

        
# Data
#### Go/NoGo Task
Data is organized in two files, one containing time uncorrected data (gng/DATA.mat) and one containing time corrected data (gng/DATA_den.mat). Each .mat file contains 

| Name    | Size      | Bytes    | Class  | Description                                                                                          |
|---------|-----------|----------|--------|------------------------------------------------------------------------------------------------------|
| BIODATA | 15607x128 | 15981568 | double | trials x times, average between F3/F4 channels.                                                      |
| BIOINFO | 15607x3   | 374568   | double | trials x information about the trial (Participant number, Trial number, Condition: 1 = Go; 2 = NoGo) |
| EMODATA | 15083x128 | 15444992 | double | trials x times, average between F3/F4 channels.                                                      |
| EMOINFO | 15083x3   | 361992   | double | trials x information about the trial (Participant number, Trial number, Condition: 1 = Go; 2 = NoGo) |
| times   | 1x128     | 1024     | double | 1 x times (in seconds)                                                                               |

Data presented here were segmented into 1000 msec epochs, between 200 msec before and 800 msec after the onset of the stimulus, downsampled to 128Hz, and re-referenced offline to the algebraic average of the P7 and P8 channels (the closest electrodes to the right and left mastoids). For further details on data collection and preprocessing please refer to Pietto et al (PLoS ONE, 2018).

#### Resting state
Data is organized in two folders, each containing files from biosemi and emotiv respectively.
File names codes 'Participant numer'_'Emotiv or Biosemi'_'Open or closed eyes'.set, for instance S01_EMO_CLOSED.set

Data files are in EEGLAB format (.set/.fdt). Each file contains 14 electrodes (the original from Emotiv and the corresponding ones from Biosemi) and comprises different experiment time. Data were downsampled to 128Hz and re-referenced offline to the average reference accross the 14 electrodes. For further details on data collection and preprocessing please refer to Pietto et al (PLOS ONE, 2018).


# Figures
Figures_Piettoetal_PLoSONE_2018.m file contains the code to create Figures 1 and 2 from Pietto et al (2018). It uses statcond.m function from EEGLAB and niceBars2.m (also included). In the same folder we also included the necessary summary data to create the figures,

* correctedERP_biosemi_emotiv.mat contains three variables to plot the time corrected ERPs: The mean values of amplitude (maERP) and standard errors (eaERP) of the epoch data, and the time window of the epoch in seconds (timese). maERP and eaERP are cell structures: maERP{1} and eaERP{1} correspond to the Biosemi system, and maERP{2} and eaERP{2} to the Emotiv system. Within each cell, the 2-D arrays contains values from each task condition (Go, NoGo, and NoGo-Go respectively) and all time-points.

* ERP_biosemi_emotiv.mat contains three variables to plot the time uncorrected ERPs: The mean values of amplitude (mERP) and standard errors (eERP) of the epoch data, and the time window of the epoch in seconds (times). The internal structure is the same as correctedERP_biosemi_emotiv.mat.

* allERP_biosemi_emotiv.mat file contains a cell with the mean amplitudes for each system (Biosem and Emotiv respectively) and each participant. Within each cell, the 3-D arrays contains values from each participant and each task condition (Go and NoGo respectively).

* DFA.mat file contains the DFA values from each participan across different time windows (max 280 seconds).

* Spectra.mat file contains a structure with the frequency spectrum (0-64 Hz) for each systems (Biosemi; Emotiv) and condition of resting-state (open; closed). Also, it includes channels names and frequency values.



