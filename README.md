# DUAL-PECCS
http://www.dualpeccs.di.unito.it/

ACT-R Extension with Dual-PECCS - Version 0.1 - Jul-2-2015



DUAL-Peccs Extension of ACT-R

Authors:
Antonio Lieto, Daniele P. Radicioni and Valentina Rho.



Licensing
---------

Copyright on the files in this bundle is retained by the authors.

This work is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License. To view a copy of this license, visit http://creativecommons.org/licenses/by-nc-sa/4.0/.



General information
---------------------
This file integrates the information provided in the README_S1S2_eng (https://github.com/alieto/DUAL-PECCS/blob/master/README_DUAL-PECCS_core_S1S2_eng) about the following:

[1] ChunkEncoder.jar - for the conversion of a textual stimulus into a chunk representation;
[2] Extended_Java_ACT-R.jar - for running the extended ACT-R environment;
[3] files/actr_models - containing a file 'working_model.actr' and the template file for the automatic creation of models with ChunkEncoder.


Requirements and configuration
------------------------------
In order to run the software, some additional steps are required:
- Install WordNet 3.0;
- Create a database (e.g., by using phpmyadmin) named 'sistemas2cyc' to import the sql dump provided in 'files/database';
- Complete the configuration file 'config/user.properties' following the directions in the file, and taking into account that:
	[1] if the folder 'files' was not moved or changed, you do not need to change the properties 'knowledgebase.dir' and 'ontology.dir';
	[2] the file specified in 'xmlQuery.path' will be created or overwritten by the system to store the encoded stimulus.


Running ACT-R
-------------
To run the system, you must first open a terminal and change dir to the folder containing the main jar file 'Extended_Java_ACT-R.jar’, and the config directory, by using the command:
	> cd path/to/directory

You can run the extended ACT-R environment with the command:
	> Java -jar Extended_Java_ACT-R.jar

This command will execute ACT-R's graphical interface; then, using the File menu, you can open the model ‘files/actr_models/working_model.actr’ and run it in order to observe the communication with the S1S2 system.


Running ChunkEncoder
---------------------

The file ChunkEncoder.jar allows to encode a textual stimulus into a chunk-like format, so you can copy the chunk into the model of interest.

Navigate to the directory containing the file 'ChunkEncoder.jar' and the folder 'config':
	> cd path/to/directory

Run the command:
	> Java -jar ChunkEncoder.jar "The big carnivorous fur with yellow and black stripes"

The program will print out a converted chunk and, if the configuration files are successfully set, it will create a model 'new_model.actr' in the folder 'files/actr_models/' so you can directly open the new file in the ACT-R environment.
