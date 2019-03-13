BootStrap: docker
From: ubuntu:16.04

%labels

    AUTHOR  Onur Yukselen <onur.yukselen@umassmed.edu>
    Version v1.0

%environment
    PATH=$PATH:/bin:/sbin:/data/sratoolkit.2.9.4-ubuntu64/bin
    export PATH

%post
    apt-get update 
    apt-get -y upgrade
    apt-get dist-upgrade
    apt-get -y install unzip libsqlite3-dev libbz2-dev libssl-dev python python-dev \
    python-pip git libxml2-dev software-properties-common wget tree vim sed \
    subversion g++ gcc gfortran libcurl4-openssl-dev curl zlib1g-dev build-essential libffi-dev  python-lzo
    ###################
    ## Python modules 
    ###################
	
	export LC_ALL=C
	pip install --upgrade pip==9.0.3
	pip install pysam
	pip install numpy scipy biopython
   
    ### SRA-toolkit
    mkdir /data && cd /data
    mkdir -p /project /nl /share 
    wget https://ftp-trace.ncbi.nlm.nih.gov/sra/sdk/2.9.4/sratoolkit.2.9.4-ubuntu64.tar.gz
    tar -xvzf sratoolkit.2.9.4-ubuntu64.tar.gz
     
    ###S3CMD
    apt-get -y upgrade
    apt-get -y install python-setuptools
    wget http://netix.dl.sourceforge.net/project/s3tools/s3cmd/1.6.0/s3cmd-1.6.0.tar.gz
    tar xvfz s3cmd-1.6.0.tar.gz
    cd s3cmd-1.6.0
    python setup.py install
