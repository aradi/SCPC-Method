Some bugs/crashes and numerical issues have been reported by different users for
the charged defect calculations in slab/2D systems, in special when high values of
the macroscopic dielectric constant is used.

After some analysis and testing, an action is needed to fix some bugs in the current version
of the SCPC method in VASP-5.4.4 and VASP-6.2.0. In addition, minor other corrections are
taking places into these corrective patches.

Hence, I would like to invite you to download and update your revisions of the SCPC method
to the latest revision (rev7) in which the modifications were made:

(a) VASP-5.4.4 and VASP-6.2.0

An important updating into the routine which calculates the isolated potential is released to fix
the main behaviour and the numerical stability of the charged defects calculations for slabs/2D
systems using the SCPC method.

A test case is provided here to verify if the new patches are working properly with the new release
for calculating the dangling bond VH(-) defect in the top of the H-Silicon (100) slab model.
This test is crashing in current version of the SCPC method in VASP-5.4.4 and VASP-6.2.0.
After updating your version to the rev7., it should be possible to run with this calculation.

(b) For VASP-6.2.0

We have also included some additional correction into the reader routine to read the damping factor
that is missing in the previous version. Also, the citation note printed in the SCPCOUT file was updated.

(c) For VASP-5.4.4

We have added the citation note into the VCOROUT file that was missing the current revision.

Please apply the revision 7 SCPC patch into your original SCPC.F/VCOR.F files.

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
