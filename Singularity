BootStrap: docker
From: conda/miniconda2

%label
    Maintainer remi-andre.olsen@scilifelab.se

%post
    apt-get update
    apt-get install -y git build-essential autoconf automake
    cd /opt

    # nthits
    git clone https://github.com/bcgsc/ntHits.git
    cd ntHits
    ./autogen.sh
    ./configure
    make
    make install
    cd ..

    # ntedit
    git clone https://github.com/bcgsc/ntEdit.git
    cd ntEdit
    make ntedit
    mv ntedit /usr/local/bin/

    apt-get clean
    rm -rf /var/lib/apt/lists/*
