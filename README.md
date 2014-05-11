TBranchBinary
==============

1.TBranchBinary, a new class developed by Christopher Crawford (now prof of Physics at Univ of Kentucky)

   *Allows one to interpret binary files as ntuples without actually reading them into an ntuple.
   *Gives access to all features of TTree.
   *Access to any ROOT classes.


2.TBranchBinary directory contains TBranchBinary library with make file.
The included files are:
 *In Library: The TBranchBinary library with make file.
 *In Analysis: A macro to plot the data (data_plot_v2.C)
 *In Data: A small data file produced by our ADC (with sinusoidal(1volt, 60 Hz) applied on channel-1, ADC running at 10KHz sample rate ) (file name "000")
 *In Sample_output: Some output files how you will see if you can run the macro (data_plot_v2.C) successfully.


3.Steps to be followed:
------------------------
*To Compile:
From terminal , go to the extracted TBranchBinary Library directory where you have "makefile"
Then from terminal type"make"
This will create addition files(Dic and .o files) in */Library/src/libN3HE/ and the libN3HE.so file in */Library/lib/ .
libN3HE.so is the binary file that will serve as your library.


*To load the library source the bin/thisN3HE.sh file before doing analysis (I.E. run ". /path/to/N3HE/bin/thisN3HE.sh").  It's convenient to put this source command into your ~/.bash_profile or ~/.bashrc file:
........................................................
if [ -f /path/to/N3HE/bin/thisN3HE.sh ]; then
        . /path/to/N3HE/bin/thisN3HE.sh
fi
.......................................................
In that case it would not matter which directory you are doing your analysis, You are free do the analysis from any directory as the library is loaded in the terminal itself.

*From a new terminal go to the analysis directory("TBranchBinary_ver_2/Analysis").and issue the command:
" root data_plot_2.C  -l " 
(without inverted comma)
*3 windows will pop-up giving the plot of the data in 000 file.
--- One windows giving histogram plotted manually (i.e. filling histogram for each data point)
--- One window giving the same histogram but this time using Ntuple/TTree .
--- Another window giving 1D Ntuple plot of the data
--- The terminal will also print the values for channel one of the ADC.


