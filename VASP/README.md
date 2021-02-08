1. Keywords for SCPC method

  1.1 VASP-5.4.4


    DOVCOR  =  T  ; to turn on the method

    INVCOR  =  10 ; the SCPC will be started on the INVCOR SCF cycle

    VCQTOT  = -1.0 ; formal defect charge

    VCDIEL   = 2.35 ; the macroscopic dielectric constant of the material 

    1.1.1 For Slab the vacuum should be set on the Z-direction only and 
    the interface position and broadening of the interface must be 
    given

      VCZLOW  =  0.15 ; lower interface boundary in crystaline coordinates
      VCZHIG  =  0.34 ; upper interface boundary in crystaline coordinates
      VCBROAD =  0.70 ; a broadening factor, usually 0.4 (ionic material) - 0.8 (covalent systems) 

    1.1.2 By the default the averaged dielectric profile, the rho-model and the corrective
    will be printed in the Z-direction only. It is possible to turn on/off the 
    averaged quantities in the X, Y and Z direction

      VCPRTX = F ; print the averaged quantities on the X-direction
      VCPRTY = F ; same but in Y-direction  
      VCPRTZ = T ; same but in Z-direction

    1.1.3 For very covalent system, like organic periodic systems (C-diamond),
    the rho-model can suffer with some numerical instability due to small charge 
    spilling on the boundaries of the unit cell. We suggest to use a cutoff term
    to damp the rho-model fluctuations on the unit cell boundaries. 

      VCRXCUT = 0.1 ; damping region of the rho-model [0-0.1] and [0.9-1.0] will be added in the X-direction 
      VCRYCUT = 0.1 ; the damping region is given in crystaline coordinate and it is symmetric
      VCRZCUT = 0.1 ; you don't need to set all the sides, only the closest to the origin.

  1.2 VASP-6.2

    For VASP-6.2 the input keywords are following the new rules in the INCAR files. 
    The example for a slab is given bellow :

      SCPC {
        USE   = T    ; turning on the SCPC method
        IN    = 1    ; starting on the first cycles
        QTOT  = 1.00 ; formal defect charge 
        ZLOW  = 0.22 ; lower interface boundary
        ZHIG  = 0.53 ; upper interface boundary
        DIEL  = 2.46 ; macroscopic dielectric
        BROAD = 0.40 ; broadening for the interface
        PRTX  = T    ; printing the averages on the X direction 
        RXCUT = 0.1  ; damping ragion on X direction for the model charge
        RYCUT = 0.1  ;
     }


2. Recommendations

   2.1 Only single point calculation. The SCPC, by the moment, cannot be used for ions/cell optimization. 
   You can turn on the SCPC method but there won't have any effect to the forces. 

   2.2 The unit cell must be orthogonal to be used with SCPC method.

   2.3 For 2D materials and slabs, the vacuum direction should be set on the Z-direction. 

   2.4 The SCPC depends on the grid quality; hence, you should consider to use PREC = Accurate 
   or increase in 25%-35% the default ENCUT and ENAUG should be set to twice of ENCUT value. 

   2.5 Do not use LREAL = Auto, only in very large cases. 

   2.6 To define the slab interfaces boundaries, you can consider 1-1.5A bellow and above the 
   frontier ion coordinates in the Z-direction. 

   2.7 Reasonable sizes for the material should be used in association to the SCPC method. 
   For 3D systems, try to use lattice larger than 15-20 Angstrom. For 2D/Slabs, the in-plane 
   lateral size should be larger than 15-20 Angstrom and the vacuum size should be 3-4 times 
   the thickness or the in-plane lateral sides. 
 
   2.8 You can use the uncorrected charged WAVECAR and CHGCAR as an initial guess to the SCPC method 
   when you have a localized defect. However, for negative defect (excess of electron) this is 
   not a good choice when you are modeling a 2D/SLAB material. For negative defect, you should start 
   SCPC after few SCF iterations INVCOR = 8, since the beginning. 

   2.9 You can also start the SCPC with a partial converged uncorreted charged system. You can run 
   the charged system with EDIFF = 1.0 or EDIFF = 0.1 then use the WAVECAR and CHGCAR to start SCPC
   method.     

   2.10 For 2D/SLAB negative defect with charge spilling and/or large potential bending in the vacuum 
   direction, you have to use the neutral defect as reference. The use of the pristine system as 
   reference didn't properly correct the charge spilling / potential bending. 

