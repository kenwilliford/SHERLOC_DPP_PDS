# SHERLOC Data Processing and Visualization

A data processing and visualization pipeline for publicly available SHERLOC data in the PDS archive

![Mars_Perseverance_NLF_0017_0668452386_425ECM_N0030578NCAM00183_01_290J](https://github.com/kenwilliford/SHERLOC_DPP_PDS/assets/132492136/a8a93f8e-f782-403a-b590-36d92a05c6ab)
*Mars 2020 Sol 17, SHERLOC (and the coring drill) on Mars, at the end of the rover's robotic arm.* Image credit [NASA/JPL-Caltech](https://mars.nasa.gov/mars2020/multimedia/raw-images/NLF_0017_0668452386_425ECM_N0030578NCAM00183_01_290J).

![PIA23621](https://github.com/kenwilliford/SHERLOC_DPP_PDS/assets/132492136/888bbe9e-169e-4834-adbf-d4f56715243b)
*Mars 2020 SHERLOC instrument prior to launch.* Image credit: [NASA/JPL-Caltech](https://mars.nasa.gov/resources/24778/close-up-of-nasas-mars-2020-rovers-sherloc-instrument/).

This program is hosted at: https://github.com/kenwilliford/SHERLOC_DPP_PDS

Description: These Jupyter Notebooks process and visualize data from the NASA Mars 2020 SHERLOC instrument, an ultraviolet fluorescence and Raman spectrometer and imaging system mounted on the robotic arm of the Perseverance rover. Output products include raw and baseline-subtracted spectra, Gaussian peak fits for spectral features associated with common mineral classes, and maps of these candidate mineral detections overlain on the highest resolution images available from the Mars 2020 rover. Example output products from SHERLOC analysis of the Mars target Dragons_Egg_Lake can be found in the Jupyter Notebooks. *Note: these files are provided as functional examples only -- mineral classes mapped in these files are not scientifically confirmed detections, which would require further analysis of individual peaks etc.*

More information about SHERLOC and its data can be found at the SHERLOC archive on the PDS Geosciences Node here: https://pds-geosciences.wustl.edu/missions/mars2020/sherloc.htm. This notebook assumes some familiarity with SHERLOC and its data structure as described in the SHERLOC PDS User Guide: https://pds-geosciences.wustl.edu/m2020/urn-nasa-pds-mars2020_sherloc/document/sherloc_user_guide.pdf.

This repository has a subfolder called sol_00861 containing example input files (PDS archived data from the Sol 861 detail_1 scan of Dragons_Egg_Lake) that can be downloaded and used to run the code in the notebook.

Instructions:

1. Ensure spectral calibration table (spec_cal.csv) is in the current working directory (same folder as this notebook).
2. Ensure data files are in a subfolder labelled as in the PDS archive (e.g. /sol_00861).
- RRS (dark-subtracted spectra) file (e.g. ss__0861_0743401635_545rrs__0420000srlc11374w104cgnj02.csv)
- RLS (laser shot position table) file (e.g. ss__0861_0743401635_545rls__0420000srlc11374_104___j02.csv)
- ACI image (e.g. SC3_0861_0743401530_113ECM_N0420000SRLC11374_0000LMJ01.PNG)
3. Define variables in PARAMETERS cell below.
4. Sequentially read descriptions and run each cell below, or (if confident with parameter settings, etc.) simply Run All Cells to transform data, remove cosmic rays, baseline fit and subtract (both before and after cosmic ray removal), and attempt Gaussian peak fitting in the spectral region where Raman peaks from common minerals occur.
5. Once the code in SHERLOC_DPP_PDS_KHW.ipynb is complete and the file at target/sol_target_scan_multifits.csv has been created, manually inspect Gaussian fits and note any peak_ids_to_reject.
6. Open SHERLOC_DPP_PDS_manual_KHW.ipynb, define peak_ids_to_reject, and run the code in that notebook to generate maps with preliminary mineral detections.

These notebooks were created by Ken Williford and tested using Python 3.11.4.
