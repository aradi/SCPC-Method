 Issue: the damping factor is not being read from the input
        section. 

 Minor correction: applying a patch to fix the reader section

 Version: rev6 at VASP-6.2

 (1) first make a copy of your current version in the src directory of VASP-6.2
  
       % cd src
       % cp scpc.F scpc.F.origina.rev6
 
 (2) get the fix patch from here

 (3) apply the patch

      %patch scpc.F  missing_damp_vasp62.txt
