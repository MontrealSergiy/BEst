# BY USING THIS RECIPE YOU ACCEPT THE MATLAB RUNTIME LICENcES
# you need install matlab runtime in graphic mode to read the current licence agreement


Bootstrap: docker
From: ubuntu:16.04

%labels
MAINTAINER S.Boroday

%environment
    MCR_ROOT=/usr/local/MATLAB/MATLAB_Runtime/v95
    BEST_DIR=/usr/local/Multi_FunkIm_lab/BEst/application
    LAUNCH_BEST="$BEST_DIR $MCR_ROOT"
    export BEST_DIR 
    export MCR_ROOT
    export LAUNCH_BEST

# %files
    # ./BEst_.install /tmp/BEst_.install
    # ./best/DATA /DATA


%help
#     you need to have installer of the tool BEst and data to use

Example
   $BEST_DIR/run_BEst.sh $MCR_ROOT MMEG.mat GMEG.mat vtcConn.mat sources cMEM "MEG" "1 1.9" "0 0.9"  normalization adaptive clusteringMethod static mspWindow 10 mspThresholdMethod arbitrary mspThreshold 0 neighborhoodOrder 4 spatialSmoothing 0.6 activeMeanInit 2 activeProbaInit 3 lambdaInit 1 activeProbaThreshold 0 activeVarCoef 0.05 inactiveVarCoef 0 noiseCovMethod 2 optimMethod fminunc useParallel 0

...

%runscript

$BEST_DIR/run_BEst.sh $MCR_ROOT 

%post
echo "This section happens once after bootstrap to build the image."
mkdir -p DERIVATIVES
apt-get update
apt-get install unzip -y
apt-get install xorg -y --fix-missing
apt-get install wget -y --fix-missing
# chmod 0444 /DATA
chmod 777 /DERIVATIVES
wget https://gitlab.com/sergiyb/best-sing/raw/master/BEst_.install
chmod a+x BEst_.install
./BEst_.install -mode silent -agreeToLicense yes
rm BEst_.install
apt-get install python -y

wget https://gitlab.com/sergiyb/best-sing/raw/master/data_best_toolbox/GMEG.mat
wget https://gitlab.com/sergiyb/best-sing/raw/master/data_best_toolbox/MMEG.mat
wget https://gitlab.com/sergiyb/best-sing/raw/master/data_best_toolbox/vtcConn.mat





