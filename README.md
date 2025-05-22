# CrystallographicSignature
GUI for processing EBSD data to identify the crystallographic signature for UHP terranes

Published May 2025 

This script is a prototype and will be updated in the coming months. There are, therefore, quirks and areas in need of improvement as outline below. It was written using MatlabR2024b and Mtex 5.7.0 and therefore does not currently work for the most recent versions of Mtex. However, a new compatible version of the GUI will be made available as soon as possible. 

Instructions and notes for using the GUI

1.	Download and save locally the ‘Palisade_app1_2025.mlapp’ script.
2.	Prior to using the GUI, load, clean, and save your EBSD data as a _.mat_ file. When re-loaded into the workspace the variable must be called ‘_ebsd_’. 
3.	When ready to use the GUI, load EBSD data (.mat file) into the Workspace.
4.	To open the GUI, drag and drop the _‘Palisade_app1_2025.mlapp’_ into the command line.   
5.	Enter the minimum misorientation angle used to define a grain boundary (default is 15 degrees). 
6.	Click _‘Load EBSD data’_. Once the data is loaded the button will turn green. If no data is present in the workspace a message will be shown in the command line.
7.	Click ‘_Plot EBSD data_’ to plot a band contrast map. Once data is plotted the button will turn green. 
8.	Choose a half width, whether you want your data to be area weighted (recommended for natural samples), and then click _‘Plot’_. At this stage you can play around with different combinations of settings but each time you must press _‘Plot’_.  
9.	Visually identify the number of maxima in [c].  Enter this value into the _‘No. of Maxima’_ box and press _‘Identify Maxima’_. You can repeat this stage with different _‘n’_ values until you get the right fit. 
--> BUG NOTE: At this point, for each ‘n’ value you try a new pole figure will appear in a pop up. It is recommended to keep this figure open once you have settled       on an ‘n’ value. However, if trying multiple ‘n’ values you will be required to close outdated figures manually. 
10.	Once happy with the number of maxima press _‘Accept points’_. The button will go green once the points are accepted into the system. 
11.	Press _‘Calc. all angles’_ button to calculate the angle between all combinations of maxima pairs. This will print a table in the command line with all possible maxima combinations. Once values are calculated the button will turn green. From the table any maxima combinations with ~ 85° ± 5° misorientation can be identified as potential Japan Twins.   
--> BUG NOTE: Currently ‘_Calc. all angles_’ must be pressed before proceeding to compare the data in different maxima groups. 
12.	Compare the relationship between different maxima by choosing an ‘Ori-1’ and ‘Ori-2’ from the drop down and pressing _‘Compare’_. This will plot pole figures for [c] and {m} only using grains associated with those modal orientations. The angle between different [c] axis maxima will be calculated and displayed below the [c]-axis pole figure. The mean orientation of each grain will be displayed as a point overlain on the density plot. A pop-up figure with the grains associated with each maxima will appear. Again, you can play with different combinations, however each time you press _'Compare'_ a new pop-up figure will appear that will need to be manually closed. 
--> BUG NOTE: There is a current glitch in the code where if you want to compare ‘Ori-1’, that is, the default, with any other modal orientation you must first         change the ‘Ori-1’ drop down to some other orientation and then change it back to ‘Ori-1’. 
--> BUG NOTE: The first time you press _‘Compare_’, on the {m} pole figure it will first plot the mean [c] orientation of each grain. Click _‘Compare’_ twice to        get the correct plot. Not required for future comparisions. 
13.	If you have identified modal pairs which are Japan Twins, you can work out the probability that they are formed by random chance by typing the number of identified Japan Twin pairs into the _‘No. of identified Japan Twin’_ box and hitting _‘Calc. probability’_. 
14.	If you find a Japan Twin, click ‘_Export Data_’ to export the grains associated with each modal orientation. 
