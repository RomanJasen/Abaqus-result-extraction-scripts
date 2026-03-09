# Abaqus-result-extraction-scripts
A set of scripts made for extraction of forces and displacements from volumetric and shell elements in implicit and explicit abaqus analysis


IMPORTANT: I recommend a check on any and all results exported, assume an error can happen and exported force or displacement can be wrong. 

There is a playlist of tutorials for these scripts. The tutorials are not ideal, but should be sufficient to introduce the entire script structure. It is recommended to read this ReadMe too as there were some additional variants of scripts made for explicit analysis.

	General tutorial and overview - https://www.youtube.com/watch?v=g9gw_EXEesM&list=PLjdnR7Fv3RGjCVFS0ykvkd6-2jo0IHgPl&index=2
	Making of the model from the General tutorial - https://www.youtube.com/watch?v=stwDfm0-Hc0&list=PLjdnR7Fv3RGjCVFS0ykvkd6-2jo0IHgPl&index=8

Essentials:
  This GitHub contains a number of python scripts with a main goal to automate extraction of force and displacement data from Abaqus models. These are not finished and it is unclear if they will be finished. They are made by myself, an inexpirienced coder that is self taught, while an effort is made to make the code simple and show its structure as clear as possible, due to the fact i did not decide to write it from stratch again, it is somewhat suboptimal. Still, they do work and can be used efficently, after the initial period of testing and familiarisation. The scripts do a bad job in being a completed program for general use, but i was able to easily modify them for different tasks i needed, such as running a large number of pushover analysis with extraction of data from multiple cross sections.
The scripts exist to automate the workflow which happens in two stages, this is described in paragraph 1. There are multiple variants and versions depending on the expected workflow and depending on the model, described in paragraph 2 will explain different workflows present in the repository. There is a variant with GUI, described in paragraph 3.


Paragraph 1:
  With regards to script structure, there are 2 main steps conducted, with everything else being done either to support these, or as additional automation.
Step 1: extracting data from field output of abaqus and storing it into txt files as displacements and forces of CROSS-SECTIONS. 
Step 2: taking the data about cross sections and plotting them in what ever way is desired. In case of PIER elements this meant plotting difference of displacement, and one of the forces. In case of story drift it means plotting extreme values against story index, etc... 

Additional scripts and steps:
  -There is a script used to prepare the model for export of data, which creates surfaces used for extraction of forces. This is needed for Step 1
  -There is a script used to prepare an input_file.txt, which defines paths, locations, step name and other data
  -There is a script used to extract images of the analysis, this script adds files to the existing database of cross-section data
  -Running of analysis can be automated with a separate script, entirely independent from these



Paragraph 2:
Relevant to Step 1:
  With regards to the model, implicit and explicit analysis are different due to a small difference in the command line used to extract displacement of a node.
Relevant to Step 2:
  Since there are many ways to process data, there are multiple variants here. The main difference is in the question of how big is the analysed model. Is it is a benchmark with say about 10 cross sections, where some sort of pushover curve is needed, it is more optimal to use a smaller script, easier to edit and modify. If the model contains a whole building, with a large number of crossections, and aside from sectional hysteresis, extremes need to be plotted separatelly, a more comprehensive structure is needed, which is also more difficult to modify.

Paragraph 3:
  GUI was used for some attempts...It can work, but is generally not very practical. Essentially once the scripts work without GUI, it can be added to call and trigger the same functions used without GUI. The benefit is not needing to understand python to use it. The problem is another layer of lost flexibility.











