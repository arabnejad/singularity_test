
# bootstraping from docker image is faster and includes more dependencies
Bootstrap: docker
#From: ubuntu:latest
From: python:latest


# alternatively we can bootstrap directly from the repo, but installation will be longer
#BootStrap: debootstrap
#OSVersion: bionic
#MirrorURL: http://us.archive.ubuntu.com/ubuntu/


#%setup
	# Runs from outside the container during Bootstrap

#%environment

#%files
#	requirements.txt
	
%post
	# Install the commonly used packages (from repo)

	# set default python version to 3
	# I did it in case of using singularity shell
	#rm /usr/bin/python
	#ln -s /usr/bin/python3 /usr/bin/python

	# Update to the latest pip (newer than repo)
#	pip install --upgrade pip

	# Now install dependencies
#	pip install fabric3 \
#				pyyaml \
#				pytest \
#				pytest-pep8 \
#				numpy

%appinstall FabSim_setup
	echo "appinstall FabSim_setup . . ."
	echo 'asdfsdff' >> app_FabSim_setup.txt
	echo ". . ."

%apprun FabSim_setup
	echo "apprun FabSim_setup . . ."
	python --version
	echo $PWD
	echo 'asdfsdff' >> apprun_FabSim_setup.txt
	pwd
	echo "${APPROOT_FabSim_setup}"
	echo ". . ."

# singularity run --app FabSim_setup fabsim.img

# The difference between exec and run is that exec runs the command you write directly but run passes whatever you write to the script you've written in %runscript
%runscript	

#	if [ ! -f deploy/machines_user.yml ]; then
#		echo "deploy/machines_user.yml not exist !!!"
#		cp deploy/machines_user_example.yml deploy/machines_user.yml
#		sed -i "s/your-username/`whoami`/g;s#~/Codes/FabSim#$PWD#g"  deploy/machines_user.yml
#	fi


	#echo pip
	#echo "PYTHONPATH="
	#echo $PYTHONPATH

	#echo "/fabsim_config/singularity_path.txt = "
	#cat /fabsim_config/singularity_path.txt
	#echo "--------"

