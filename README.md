# BEst
BEst (Brain Entropy in space and time) singularity recipe

Here is a prelimary version of BEst singularity recipe for Singularity Hub integration.
https://neuroimage.usc.edu/brainstorm/Tutorials/TutBEst


to update container you need to create a release and attached installer package BEst_install of the tool BEst
Presently installer is built locally manually using Matlap Compiler pluging GUI or in console with
 
~~~~shell 
cd ~
git clone https://gitlab.com/multifunkimlab/best 
cd best
mcc -o BEst -W main:BEst -T link:exe -d ~/best/LAUNCH_ME_SCRIPT_BEst/for_redistribution -R '-logfile,mcc.log' -v ~/best/BEst.m -a ~/best/BEst.m -a ~/best/CODE -a ~/best/LAUNCH_ME_SCRIPT.m 
~~~~

Attach this file to release and commit something to triger rebuild

https://singularity-hub.org/collections/2087
