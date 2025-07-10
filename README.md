Dear reader,

within our here installed github project directory. We publish the code generated to solve our specific questions. You can download and modify the published code as desired given the citation of the person who generated it: René Buschow (buschow@molgen.mpg.de, 0049 30 8413 1663, Imaging Core Facility),  and Nadine Brombacher (brombach@molgen.mpg.de, 0049 030 8413 1563, High-Resolution Neurogenetics) both Max Planck Institute for Molecular Genetics, 14195 Berlin - Germany. 

Purpose aka a methode part:

Rectangular regions of interest (ROIs) were manually placed over the entire cortical area in Fiji, ensuring that the shorter edge was aligned parallel to both the ventricular zone (VZ) and the cortical plate (CP). To standardize spatial orientation across all samples, the ROIs were automatically rotatedA_roi_orientate_export.txt using a custom Fiji script"A_roi_orientate_export.txt". Each rotation was visually inspected "B_roi_orientation_check.txt" and quality-controlled by an experimenter to ensure accurate alignment. A downstream Fiji macro was used to export "C_roi_nuclei_channel_export.txt" the nuclear counterstain signal within each ROI, which served as the input for cell segmentation using Cellpose"D_cellpose_nuclei_tissue_segmentation.pipeline". This process allowed for the identification and labeling of individual nuclei.
Segmented images, together with an additional label image marking NPM1-positive nucleoli, were combined with the raw fluorescence data and converted into text-based formats"E_pixel_lists_export.txt". These files contained pixel-wise positional and intensity information for the NPM1 (channel 1), LaminB1 (channel 2), and DNA (channel 3) signals. Based on the segmentation output, further quantitative parameters including total intensity per channel, cell area, and nucleolar features such as number, size, and average intensity were extracted using custom-written R scripts "F_statistics_from_pixel_lists.txt".
All results were compiled into structured cell-by-cell matrices "G_rbinder.txt", with each row representing a single segmented cell and its associated quantitative features. These matrices facilitated downstream data visualization, statistical analysis, and data comparision. 

DEMO-Data: Raw Image data for the documentated pipelin as well as pixelwise expression/morphometrics/profiles can be found here : https://nc.molgen.mpg.de/cloud/index.php/s/QXPp3b6sJjBkwG6 . NOTE: The here shared data is a tif export from its original .czi format without any compression or modification. 

We are ready and happy to share way more raw data, but please be aware/prepared that many of our experiments are imaging based and therefore often exceeed 10,20... gb. We have the the infrastructure to share it over own online repositories but our data policy is encouraging us to better archive data than cloud share it on a long term. But feel free to contact René or Adriano for more.

Further, the order within the pipeline is alphabetical starting at A, ending on G. All script relay on each other and has to follow that order. We promise we wrote all the code by ourselve however to enhance the readability for the user, intend more structure we feeded ChatGTP with out spagetthi code and got back well the here shown commented and intendend version.


Codeblocks in FIJI/imagej are:

A_roi_orientate_export.txt
B_roi_orientation_check.txt
C_roi_nuclei_channel_export.txt
E_pixel_lists_export.txt

Version: The code was generated in FIJI version 1.53v, the creator of the code used base functionalities therefore it should work in almost all version. Only expansion here was the use of the morpholib library (David Legland, Ignacio Arganda-Carreras, Philippe Andrey; MorphoLibJ: integrated library and plugins for mathematical morphology with ImageJ. Bioinformatics 2016; 32 (22): 3532-3534. doi: 10.1093/bioinformatics/btw413) 

System Requirements: The scripts were generated under Windows 10 but should work under Linux & MAC as well (not tested).

Installation: Copy or open Code in any ImageJ/FIJI instance


Codeblock in Arivis are:

D_cellpose_nuclei_tissue_segmentation.pipeline

Version: The pipeline was set up in arivis Vision4D 4.1.2 running under a commercial license. Purpose of the code was the output of a label image of segmented nuclei within a tissue (here brain) enviroment. This block can be replaced by any open source tool that enales the output of a label image, within the identical dimensionality as the original image.

System Requirements: arivisVision 4D is a propietary software running exclusively under Windows (hgere 10) , rewquires software license fees as well as a suitable GPU.

Installation: Import Pipeline into the analysis module of arivis.


Codeblock in R

F_statistics_from_pixel_lists.txt
G_rbinder.txt

Version: The code was generated in R 4.4.0 runbning under Windows 10. The full code consist of base functionalities in the R-enviroment and should be compatible with any Version.

System Requirements: The scripts were generated under Windows 10 but should work under Linux & MAC as well (not tested).

Installation: Copy or open Code in any R instance


