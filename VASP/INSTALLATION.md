1. INSTALLATION

    (a) preparation

       %cd 5.4.4
       %git apply ../vasp-scpc.patch
       %cp ../vcor.F ./scr
       %cp ../makefile.scpc ./arch
       %ln -s ./arch makefile.include

    (b) edition of makefiles

       -- check the makefile.include to add the right path
          for the external libraries for the Poisson and Isolate potential
          solver

       -- edit the variables at makefile.include to point your own
          installation

      #SCPC METHOD
        LIBEXT     = /auto/tms7/chagasda1/opt/trunk/libext
        DLMGROOT   = $(LIBEXT)/dl_mg_2.0.2
        PSPFFTROOT = $(LIBEXT)/pspfft-1.0
        INCS      +=-I$(DLMGROOT)/lib
        INCS      +=-I$(PSPFFTROOT)/include
        LLIBS     +=-Wl,--start-group $(DLMGROOT)/lib/libdlmg.a -Wl,--end-group
        LLIBS     +=-Wl,--start-group $(PSPFFTROOT)/lib/libpspfft.a -Wl,--end-group
      #SCPC METHOD


    (c) you can compile your own version of vasp-scpc

        %make

