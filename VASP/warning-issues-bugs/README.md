
* [ Mar.01.2021 ] Kpoints parallelism is broken on the current version 
  of SCPC(rev6) at VASP-5.4.4 and probably at VASP-6.2. It is recommended 
  not to use the KPAR keyword in conjunction with the SCPC method.
  The parallelism of the bands is working fine; hence, the user can continue 
  using the NPAR keyword with SCPC. The authors thank to Soungmin Bae 
  and Hannes Raebiger for their contribution on reporting the bug/issue 
  with KPAR keyword with SCPC.

* [ Mar.15.2021] The SCPC cannot be used with the non-collinear keyword.
  The vasp_ncl with SCPC is broken. By the moment, you cannot use 
  non-collinear magnetization. The authors thank to Jing Zhan and 
  prof. Dr. Qihang Liu from the Southern Univ. of Science and Technology 
  Shenzhen. for their contribution on reporting the bug/issue with the 
  non-collinear version of SCPC.  

