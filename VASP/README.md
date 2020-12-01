1. Keywords for SCPC method

  1.1 VASP-5.4.4


    DOVCOR  =  T  ; to turn on the method

    INVCOR  =  10 ; the SCPC will be started on the INVCOR SCF cycle

    VCQTOT  = -1.0 ; defect formal charge

    VDIEL   = 2.35 ; the macroscopic dielectric constant of the material 

    1.1.1 For Slab the vacuum should be set on the Z-direction only and 
    the interface position and broadening of the interface must be 
    give

      VCZLOW  =  0.15 ; lower interface boundary in crystaline coordinates
      VCZHIG  =  0.34 ; upper interface boundary in crystaline coordinates
      VCBROAD =  0.70 ; a broadening fact, usually 0.4 (ionic material) - 0.8 (covalent systems) 

    1.1.2 By the default the averaged dielectric profile, the rho-model and the corrective
    will be printed in the Z-direction only. It is possible to turn on/off the 
    averaged quantities in the X, Y and Z direction

      VCPRTX = F ; print the averaged quantities on the X-direction
      VCPRTY = F ; same but in Y-direction  
      VCPRTY = T ; same but in Z-direction

    1.1.3 For very covalent system like organic periodic systems (C-diamond)
    the rho-model can suffer with some numerical instability due to small charge 
    spiling on the boundaries of the unit cell. We suggest to use a cutoff term
    to damp the rho-model fluctuation on the unit cell boundaries. 

      VCRXCUT = 0.1 ; damping region of the rho-model [0-0.1] and [0.9-1.0] will be added in the X-direction 
      VCRYCUT = 0.1 ; the damping region is given in crystaline coordinate and it is symmetric
      VCRZCUT = 0.1 ; you don't need to set all the sides, only the closest to the origin.

