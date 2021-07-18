
  VASP-5.4.4 and VASP-6.2.0

An importante updating into the routine which calculates the 
isolated potential was released to fix the behavior and the stability 
of the charged defects calculations for slabs/2D systems using the SCPC 
method. 

For VASP-6.2.0, we have also included some additional correction into the reader
routine to read the damping factor that was missing in the previous version
as well as we updated the citation note printed in the SCPCOUT file. 

For VASP-5.4.4, we have also included some additional information into the VCOROUT 
file how to cite the SCPC method 

A test case is provided here to verify if the new patches are working properly 
with the new release.

 (1) First, make a copy of your current version in the src directory of VASP

       <<<< VASP-6.2.0 >>>>

       % cd src
       % cp scpc.F scpc.F.orig.rev6
       
       or 

       <<<< VASP-5.4.4 >>>>

       % cd src
       % cp vcor.F vcor.F.orig.rev6


 (2) get the patch files by e-mail with the developers

 (3) apply the patch

      <<<< VASP-6.2.0 >>>>

      %patch scpc.F scpc-vasp62-rev7.patch

      or 

      <<<< VASP-5.4.4 >>>>

      %patch vcor.F scpc-vasp54-rev7.patch
