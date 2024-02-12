# SHERLOC_DPP_PDS
Data processing pipeline for publicly available SHERLOC data in the PDS archive

This program is hosted at:

Description: This Jupyter Notebook will process and visualize data from the NASA Mars 2020 SHERLOC instrument, an ultraviolet fluorescence and Raman spectrometer and imaging system mounted on the robotic arm of the Perseverance rover. More information about SHERLOC and its data can be found at the SHERLOC archive on the PDS Geosciences Node here: https://pds-geosciences.wustl.edu/missions/mars2020/sherloc.htm. This notebook assumes some familiarity with SHERLOC and its data structure as described in the SHERLOC PDS User Guide: https://pds-geosciences.wustl.edu/m2020/urn-nasa-pds-mars2020_sherloc/document/sherloc_user_guide.pdf.

Instructions:

Ensure spectral calibration table (spec_cal.csv) is in the current working directory (same folder as this notebook).
Ensure data files are in a subfolder labelled as in the PDS archive (e.g. /sol_00861).
RRS (dark-subtracted spectra) file (e.g. ss__0861_0743401635_545rrs__0420000srlc11374w104cgnj02.csv)
RLS (laser shot position table) file (e.g. ss__0861_0743401635_545rls__0420000srlc11374_104___j02.csv)
ACI image (e.g. SC3_0861_0743401530_113ECM_N0420000SRLC11374_0000LMJ01.PNG)
Define variables in PARAMETERS cell below.
Sequentially read descriptions and run each cell below, or (if confident with parameter settings, etc.) simply Run All Cells to transform data, remove cosmic rays, baseline fit and subtract (both before and after cosmic ray removal), and attempt Gaussian peak fitting in the spectral region where Raman peaks from common minerals occur.
This notebook was created by Ken Williford and tested using Python 3.11.4
