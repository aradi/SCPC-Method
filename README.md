
# Self-Consistent Potential Correction Method

  Supercell models are often used to calculate the electronic structure of local
  perturbations from the ideal periodicity in the bulk or on the surface of a
  crystal or in wires. When the defect or adsorbent is charged, a jellium
  counter charge is applied to maintain overall neutrality, but the interaction
  of the artificially repeated charges has to be corrected, both in the total
  energy and in the one-electron eigenvalues and eigenstates. This becomes
  paramount in slab or wire calculations, where the jellium counter charge may
  induce spurious states in the vacuum. We present here a self-consistent
  potential correction scheme and provide successful tests of it for bulk and
  slab calculations.
  
## How to cite:

* The main method:
  
  > Mauricio Chagas da Silva, Michael Lorke, Bálint Aradi, 
  > Meisam Farzalipour Tabriz, Thomas Frauenheim, 
  > Angel Rubio, Dario Rocca, and Peter Deák
  >
  > "Self-Consistent Potential Correction for Charged Periodic Systems"
  >
  > Phys. Rev. Lett. 126, 076401 – Published 19 February 2021

  [https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.126.076401](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.126.076401)


* The external libraries

  * Poisson Solver
      
    > "DL_MG: A Parallel Multigrid Poisson and Poisson–Boltzmann Solver for 
    > Electronic Structure Calculations in Vacuum and Solution"
    > James C. Womack, Lucian Anton, Jacek Dziedzic, Phil J. Hasnip, 
    > Matt I. J. Probert, and Chris-Kriton Skylaris
    > J. Chem. Theory Comput. 2018, 14, 3, 1412–1432

    [https://pubs.acs.org/doi/abs/10.1021/acs.jctc.7b01274](https://pubs.acs.org/doi/abs/10.1021/acs.jctc.7b01274)

  * Isolate Potential 

    > "Parallel FFT-based Poisson solver for isolated three-dimensional systems"
    >     Reuben D.Budiardja and Christian Y.Cardalla
    >    Computer Physics Communications
    >    Volume 182, Issue 10, October 2011, Pages 2265-2275

    [https://doi.org/10.1016/j.cpc.2011.05.014](https://doi.org/10.1016/j.cpc.2011.05.014)


## Getting the SCPC method

### VASP-5.4.4

* To obtain a copy of the method patch for VASP release 5.4.4, please contact
  main authors by email.
    
* You must have an official VASP license and you must have a valid academic
  e-mail.

### VASP-6.2.0

It is already implemented in the official version of VASP-6.2.0.


### External libraries 

* To compile the SCPC method you should have installed the DL_MG and PSPFFT
  libraries to solve the poisson equations and the isolate potential.

* For the DL_MG (version 2.1.4), please visit the website 
  [https://bitbucket.org/dlmgteam/dl_mg_code_public/src/master/](https://bitbucket.org/dlmgteam/dl_mg_code_public/src/master/)

* For the PSPFFT (1.0.1), please visit the website

  [http://eagle.phys.utk.edu/pspfft/trac/](http://eagle.phys.utk.edu/pspfft/trac/)



## Recommendations/Notes

* Please note that SCPC cam only provide meaningful results if delta_rho(r),
  i.e.,the difference between the electron-distributions of the charged and the
  reference systems decays towards the cell boundary.
