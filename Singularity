
# bootstraping from docker image is faster and includes more dependencies
Bootstrap: docker
#From: ubuntu:latest
From: python:latest


# alternatively we can bootstrap directly from the repo, but installation will be longer
#BootStrap: debootstrap
#OSVersion: bionic
#MirrorURL: http://us.archive.ubuntu.com/ubuntu/


%setup
	# Runs from outside the container during Bootstrap
	touch ${SINGULARITY_ROOTFS}/tacos.txt


#%environment

#%files
#	requirements.txt
	
%post
	# Install the commonly used packages (from repo)


%appenv FabSim_installation
	fabsim_INSTALL_DIR=$PWD
	echo ""
	echo "appenv FabSim_installation"
	echo ""
%appinstall FabSim_installation
	echo ""
	echo "appinstall FabSim_installation"
	echo ""

%apprun FabSim_installation
	# to make sure that PATH will be set
	echo ""
	echo "apprun FabSim_installation"
	echo ""
	#echo 'export PYTHONPATH=$PYTHONPATH:${fabsim_INSTALL_DIR}' >> ${SINGULARITY_ROOTFS}/tacos.txt

# sudo rm fabsim.img ; sudo singularity build  fabsim.img Singularity2
# singularity apps fabsim.img
# singularity run --app FabSim_installation fabsim.img --dir jdfjf
# singularity run fabsim.img


# The difference between exec and run is that exec runs the command you write directly but run passes whatever you write to the script you've written in %runscript
%runscript
	echo "PYTHONPATH = " $PYTHONPATH


