
# VASP静态计算输出文件

:green_circle: **静态计算输出文件结构**


```
.
├── AECCAR0
├── AECCAR1
├── AECCAR2
├── CHG
├── CHGCAR
├── CONTCAR
├── DOSCAR
├── EIGENVAL
├── IBZKPT
├── INCAR
├── KPOINTS
├── LOCPOT
├── OSZICAR              # OSZICAR文件记录了每个迭代步骤的能量和电荷密度，因此它是判断计算是否收敛的重要指标.
├── OUTCAR
├── PCDAT
├── POSCAR
├── POTCAR
├── PROCAR
├── REPORT
├── slurm-2675593.out
├── sub.sh
├── vasprun.xml
├── WAVECAR
└── XDATCAR
```



:green_circle: **OSZICAR**

- **符号含义**

```
    N: 电子结构的迭代步数，通常被称为电子步。
    E: 当前电子步的体系能量。
    dE: 当前电子步和上一步体系能量的差值。
    d eps: 能带结构能量的变化。
    ncg: 作用于波函数的哈密顿量的评价数。
    rms: 试用波函数的残差的范数（即它们的近似误差）。
    rms©: 电荷密度残差（前几步电荷密度不参与迭代）。
```
DAV是blocked Davidson iteration scheme 的缩写，是一个电子自洽算法的缩写，RMM (residual minimization scheme) 和 CG （conjugate-gradient algorithm）等，这些是由INCAR中的ALGO参数决定

- **文件内容**

```
       N       E                     dE             d eps       ncg     rms          rms(c)
DAV:   1     0.262963906782E+03    0.26296E+03   -0.13606E+04  2304   0.140E+03
DAV:   2    -0.147719592593E+02   -0.27774E+03   -0.26887E+03  2384   0.300E+02
DAV:   3    -0.805108877868E+02   -0.65739E+02   -0.64315E+02  3744   0.132E+02
DAV:   4    -0.839490730879E+02   -0.34382E+01   -0.34294E+01  3104   0.324E+01
DAV:   5    -0.840274618995E+02   -0.78389E-01   -0.78495E-01  3160   0.523E+00    0.415E+01
DAV:   6    -0.681149709824E+02    0.15912E+02   -0.12273E+02  3448   0.642E+01    0.127E+01
DAV:   7    -0.678322667781E+02    0.28270E+00   -0.13214E+01  3464   0.237E+01    0.918E+00
DAV:   8    -0.676127626457E+02    0.21950E+00   -0.14812E+00  3504   0.791E+00    0.140E+00
DAV:   9    -0.675766178893E+02    0.36145E-01   -0.17189E-01  3304   0.256E+00    0.398E-01
DAV:  10    -0.675781648484E+02   -0.15470E-02   -0.81316E-02  3208   0.128E+00    0.288E-01
DAV:  11    -0.675770209933E+02    0.11439E-02   -0.89472E-03  3248   0.587E-01    0.204E-01
DAV:  12    -0.675771006993E+02   -0.79706E-04   -0.23153E-03  3088   0.236E-01    0.725E-02
DAV:  13    -0.675771007310E+02   -0.31732E-07   -0.91291E-05  2928   0.667E-02
   1 F= -.67577101E+02 E0= -.67577101E+02  d E =0.000000E+00  mag=    -0.0000
```

:green_circle: **OUTCAR**

- **文件内容**

OUTCAR 文件是 VASP 在计算过程中生成的主要输出文件之一，包含了大量的计算结果和过程记录。以下是 OUTCAR 文件中包含的一些信息:    

用于计算的输入参数的概述。    
电子步骤、Kohn-Sham本征值等电子结构信息。    
应力张量、原子受力等结构信息。   
局部电荷和磁矩等信息。  
介电性质等其他信息。    

OUTCAR 文件中包含的输出内容可以通过修改 INCAR 文件中的 NWRITE 标签来选择。

```
 vasp.5.4.4.18Apr17-6-g9f103f2a35 (build Nov 17 2020 17:54:46) complex          
  
 executed on             LinuxIFC date 2023.09.26  17:09:42
 running on   64 total cores
 distrk:  each k-point on    8 cores,    8 groups
 distr:  one band on NCORES_PER_BAND=   2 cores,    4 groups


--------------------------------------------------------------------------------------------------------


--------------------------------------- Iteration      1(  14)  ---------------------------------------


    POTLOK:  cpu time    0.0515: real time    0.0635
    SETDIJ:  cpu time    0.4765: real time    0.4766
     EDDAV:  cpu time    0.2827: real time    0.2836
 BZINTS: Fermi energy:  8.683970; 38.000000 electrons
         Band energy: 134.423518;  BLOECHL correction: -0.108454
       DOS:  cpu time    0.0149: real time    0.0149
    --------------------------------------------
      LOOP:  cpu time    0.8256: real time    0.8387

 eigenvalue-minimisations  :  3224
 total energy-change (2. order) :-0.3970183E-05  (-0.5334378E-05)
 number of electron      37.9999994 magnetization       0.0001839
 augmentation part        6.3731527 magnetization       0.0002006

 Free energy of the ion-electron system (eV)
  ---------------------------------------------------
  alpha Z        PSCENC =       140.25282115
  Ewald energy   TEWEN  =     -1636.51123608
  -Hartree energ DENC   =      -101.91636345
  -exchange      EXHF   =         0.00000000
  -V(xc)+E(xc)   XCENC  =      -146.59065512
  PAW double counting   =      3226.49321421    -3016.41118853
  entropy T*S    EENTRO =         0.00000000
  eigenvalues    EBANDS =       134.42351831
  atomic energy  EATOM  =      1329.85235582
  Solvation  Ediel_sol  =         0.00000000
  ---------------------------------------------------
  free energy    TOTEN  =       -70.40753370 eV

  energy without entropy =      -70.40753370  energy(sigma->0) =      -70.40753370


--------------------------------------------------------------------------------------------------------


  FREE ENERGIE OF THE ION-ELECTRON SYSTEM (eV)
  ---------------------------------------------------
  free  energy   TOTEN  =       -70.40753370 eV

  energy  without entropy=      -70.40753370  energy(sigma->0) =      -70.40753370
 


--------------------------------------------------------------------------------------------------------


    POTLOK:  cpu time    0.5294: real time    0.5295


--------------------------------------------------------------------------------------------------------


 stress matrix after NEB project (eV)
     -0.50749     -0.00000     -0.00000
      0.00000     -0.50749      0.00000
      0.00000      0.00000     -0.67546
  FORCES: max atom, RMS     0.042143    0.029800
  FORCE total and by dimension    0.084286    0.042143
  Stress total and by dimension    0.985565    0.675456
     LOOP+:  cpu time   12.0820: real time   12.2709
    4ORBIT:  cpu time    0.0000: real time    0.0000
 


 total charge     
 
# of ion       s       p       d       tot
------------------------------------------
    1        0.480   0.854   3.763   5.097
    2        0.480   0.854   3.795   5.129
    3        0.480   0.854   3.794   5.128
    4        0.480   0.854   3.765   5.099
    5        1.041   1.504   0.000   2.545
    6        1.038   1.505   0.000   2.543
    7        0.891   1.513   0.000   2.405
    8        0.891   1.513   0.000   2.404
--------------------------------------------------
tot          5.782   9.452  15.117  30.351
 


 magnetization (x)
 
# of ion       s       p       d       tot
------------------------------------------
    1       -0.000   0.000   0.000   0.000
    2        0.000  -0.000  -0.000  -0.000
    3       -0.000   0.000   0.000   0.000
    4        0.000   0.000  -0.000  -0.000
    5        0.000   0.000   0.000   0.000
    6        0.000  -0.000   0.000  -0.000
    7       -0.000  -0.000   0.000  -0.000
    8       -0.000   0.000   0.000   0.000
--------------------------------------------------
tot          0.000   0.000   0.000   0.000
 
 BZINTS: Fermi energy:  8.683970; 38.000000 electrons
         Band energy: 134.423518;  BLOECHL correction: -0.108454

 total amount of memory used by VASP MPI-rank0    49266. kBytes
=======================================================================

   base      :      30000. kBytes
   nonlr-proj:       4721. kBytes
   fftplans  :       2354. kBytes
   grid      :       6243. kBytes
   one-center:        124. kBytes
   wavefun   :       5824. kBytes
 
  
  
 General timing and accounting informations for this job:
 ========================================================
  
                  Total CPU time used (sec):       16.449
                            User time (sec):       14.631
                          System time (sec):        1.818
                         Elapsed time (sec):       16.883
  
                   Maximum memory used (kb):       85376.
                   Average memory used (kb):           0.
  
                          Minor page faults:        29744
                          Major page faults:            6
                 Voluntary context switches:         2545


```



