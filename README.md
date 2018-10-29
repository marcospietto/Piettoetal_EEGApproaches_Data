# Data and analysis code from Pietto et al (PLoS ONE, 2018)
These are the data and analysis code from Pietto et al (PLoS ONE, 2018). Analysis were carried out using Matlab and [EEGLAB v13.5.4b](https://sccn.ucsd.edu/eeglab/index.php). Also, for the analysis of temporal correlations with Detrended Fluctuation Analysis (DFA) we used the function available [here](https://la.mathworks.com/matlabcentral/fileexchange/19795-detrended-fluctuation-analysis), and for the wavelet denoising we use the [EP_den package](https://www2.le.ac.uk/centres/csn/software/ep_den) (Centre for Systems Neuroscience, University of Leicester, UK). For further details please refer to Pietto et al (PLoS ONE, 2018).

This project is part of a larger collaboration between the Unidad de Neurobiología Aplicada (CEMIC - CONICET, Argentina; http://pobrezaydesarrollocognitivo.blogspot.com/) and the Laboratorio de Inteligencia Artificial Aplicada (Instituto de Cs. de la Computación, Fac. de Cs. Exactas y Naturales, UBA - CONICET, Argentina; https://liaa.dc.uba.ar/). Our general goal is to study the influence of adverse environmental conditions on the organization and reorganization of the brain structure and function, and how it involves distinct neural systems at different levels of organization. Thus, we measure EEG in children from low socio-economic status contexts to evaluate the efficacy of interventions, aimed to enhance cognitive development in children facing unfavorable social conditions (see also Pietto ML, Kamienkowski JE, Lipina S "Electrophysiological approaches in the study of childhood poverty influence on cognition" (2017) book chapter in “Neuroscience and Social Science: The missing link” Springer Books).

# Experiments' code and Emotiv SDK's bindings for Python
Experiments' code and Emotiv SDK's bindings for Python are available in https://github.com/mathigatti/Emotiv-Experiments.

# How to cite us
#### Please, if you like it / use it cite us:
Pietto ML, Gatti M, Raimondo F, Lipina SJ, and Kamienkowski JE. "Electrophysiological approaches in the study of cognitive development outside the lab" (accepted, 2018)
#### And let us know!!
Marcos L. Pietto (marcos.pietto (arroba) gmail (dot) com)
Mathias Gatti (mathigatti (arroba) gmail (dot) com)
Federico Raimondo
Sebastian Lipina
Juan E. Kamienkowski (juank (arroba) dc (dot) com (dot) ar)

        
# Data
#### Go/NoGo Task
Data is organized in two files, one containing latency uncorrected data (gng/DATA.mat) and one containing latency corrected data (gng/DATA_den.mat). Each .mat file contains 

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

Data files are in EEGLAB format (.set/.fdt). Each file contains 14 electrodes (the original from Emotiv and the corresponding ones from Biosemi) and comprises different experiment time. Data were downsampled to 128Hz and re-referenced offline to the average reference accross the 14 electrodes. For further details on data collection and preprocessing please refer to Pietto et al (PLoS ONE, 2018).

