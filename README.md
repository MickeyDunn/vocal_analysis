Vocal Analysis Codez
=====================

match_bout_behaviours.py
-------------------------

This script matches up Avisoft output on bout times, and ELAN output on behaviour times. It matches a behaviour for each bout (if any), by finding which bouts occur entirely within the time bounds of a behavioural event. Will process many files in a batch and produces a single file as output. Provided to the program is a directory location for all bout time files, another for behaviour time files, another for the excel sheet that contains their time offset (which must be in seconds in cell Z2) and optionally, the location to save the output file to. Each matching pair of bout and behaviour files *must* start with the same identifier. The program will expect the excel sheet with the time sync info to be nested in another directory, below the one given at the command line.

To use this from the CLI:

    $ python match_bout_behaviours.py "<bout file directory>" "<behaviour file directory>" "<sync file directory>" "<output directory (optional)>"

directory locations may be relative or absolute. It is especially important to enclose them in quotes if executing this on a windows machine from bash.
  
------------------------------------------------------------------

Mickey's interpretation of these instructions (validating that she actually knows how to use the thing): 

Once within the vocal_analysis folder on your machine, begin by entering "python match_bout_behaviours.py" into the bash terminal. Leave a space, then enter "[file path leading to the folder containing the LBL file of interest from Avisoft]" "[file path leading to the folder containing the weird output of interest from ELAN]" "[file path leading to the folder containing ALL synchronization files (this is the "AudioVideoSynchronization" folder - the program will seek out the matching sync folder and file depending on what identifier the other two files use)." Optionally, finish the command with "[location where you want the output to go]." If you don't include a final output destination, the Excel file the code spits out will be in the vocal_analysis folder. 

If successfully run, this code identifies bouts that fall completely within a behavioural event, and matches the bout with the behaviour. The output is an Excel spreadsheet with one column containing behaviours and a neighboring column with associated bout numbers. The contents of these bouts can then be analyzed with regard to their respective behavioural contexts. 