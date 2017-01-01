# Install and test setup

1. Install packages:

    sudo apt-get install binutils-msp430 gcc-msp430 msp430-libc mspdebug

2. With board connected, check USB connection:

    lsusb
    
        note: expecting to see e.g.: Bus 001 Device 013: ID 0451:f432 Texas Instruments, Inc. eZ430      Development Tool

3. Check communication with microcontroller:

    mspdebug rf2500

        note: rf2500 = launchpad board

    md 0xf800 2048

        note: memory dump 2048 bytes starting at 0xf800

    exit

# Compile and upload

1. Get a hello world main.c from somewhere, e.g.:

    git clone https://github.com/simplyembedded/msp430_launchpad.git

2. Compile:

    msp430-gcc -mmcu=msp430g2231 main.c

        note, -mmcu must match!

        produces a.out by default

3. Upload and run:

    mspdebug rf2500

    prog a.out

    run
