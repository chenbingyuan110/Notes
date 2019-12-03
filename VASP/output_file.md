## Output文件
### OSZICAR
```
1       N       E                   dE          d eps       ncg    rms      rms(c)
2 DAV:   1     0.363606608360E+02    0.36361E+02   -0.98834E+02    24   0.195E+02
3 DAV:   2     0.815260584647E+00   -0.35545E+02   -0.35545E+02    48   0.327E+01
4 DAV:   3    -0.364886031610E-02   -0.81891E+00   -0.81561E+00    24   0.117E+01
5 DAV:   4    -0.123886775924E-01   -0.87398E-02   -0.79838E-02    36   0.110E+00
6 DAV:   5    -0.123956401569E-01   -0.69626E-05   -0.69631E-05    24   0.349E-02    0.307E-01
7 DAV:   6    -0.134138210989E-01   -0.10182E-02   -0.18030E-03    36   0.222E-01    0.155E-01
8 DAV:   7    -0.135108544930E-01   -0.97033E-04   -0.22625E-04    24   0.934E-02
9   1 F= -.13510854E-01 E0= -.11021795E-01  d E =-.746718E-02
```
#### 第一行
+ `N` 代表电子步的迭代步数,本例中里面有7个电子步。
+ `E` 代表当前电子步的体系能量;
+ `dE` 该步和上一步体系能量的差值;
+ `d eps` the change in the bandstructure energy;本征值的变化
+ `ncg`  the number of evaluations of theHamiltonian acting onto a wavefunction;波函数的优化次数
+ `rms`  the norm of the residuum of the trialwavefunctions (i.e. their approximate error)
+ `rms(c)` the difference between input andoutput charge density.

#### 最后一行
```
1 F= -.13510854E-01 E0= -.11021795E-01  d E =-.746718E-02
```
+ `F`前面的`1`代表离子步的步数，当前只有1步
+ `F=` 是体系的总能量，与`OUTCAR`中 `free energy  TOTEN` 后面的值相等
+ `E0` 后面的能量对应`OUTCAR`中 `energy(sigma->0)`后面的能量，**计算完成后的体系的能量**

### OUTCAR
开头分别展示`INCAR`、`POSCAR`、`KPOINTS`、`POTCAR`的相关信息
#### INCAR和POTCAR的部分信息
```
 INCAR:
 POTCAR:    PAW_PBE O 08Apr2002
 POTCAR:    PAW_PBE O 08Apr2002
   VRHFIN =O: s2p4
   LEXCH  = PE
   EATOM  =   432.3788 eV,   31.7789 Ry

   TITEL  = PAW_PBE O 08Apr2002
   LULTRA =        F    use ultrasoft PP ?
   IUNSCR =        1    unscreen: 0-lin 1-nonlin 2-no
   RPACOR =    1.200    partial core radius
   POMASS =   16.000; ZVAL   =    6.000    mass and valenz
:
 vasp.5.4.1 05Feb16 (build Mar 19 2019 01:13:45) complex

 executed on           IFC91_ompi date 2019.03.20  18:28:46
 running on    4 total cores
 distrk:  each k-point on    4 cores,    1 groups
 distr:  one band on NCORES_PER_BAND=   1 cores,    4 groups
```

#### POSCAR基本信息，包括坐标格式、原子位置、晶胞的形状大小
```
 POSCAR: O atom in a box
  positions in cartesian coordinates
  No initial velocities read in
 exchange correlation table for  LEXCH =        8
   RHO(1)=    0.500       N(1)  =     2000
   RHO(2)=  100.500       N(2)  =     4000

-------------------------------------------------------

 ion  position               nearest neighbor table
   1  0.000  0.000  0.000-

  LATTYP: Found a simple cubic cell.
 ALAT       =     8.0000000000

  Lattice vectors:

 A1 = (   8.0000000000,   0.0000000000,   0.0000000000)
 A2 = (   0.0000000000,   8.0000000000,   0.0000000000)
 A3 = (   0.0000000000,   0.0000000000,   8.0000000000)
```
#### K点信息
```
Found      1 irreducible k-points:

Following reciprocal coordinates:
           Coordinates               Weight
 0.000000  0.000000  0.000000      1.000000

Following cartesian coordinates:
           Coordinates               Weight
 0.000000  0.000000  0.000000      1.000000
```
#### 详细计算参数（下面示例为部分内容）
```
 Dimension of arrays:
   k-points           NKPTS =      1   k-points in BZ     NKDIM =      1   number of bands    NBANDS=      8
   number of dos      NEDOS =    301   number of ions     NIONS =      1
   non local maximal  LDIM  =      4   non local SUM 2l+1 LMDIM =      8
   total plane-waves  NPLWV =  64000
   max r-space proj   IRMAX =      1   max aug-charges    IRDMAX=   1821
   dimension x,y,z NGX =    40 NGY =   40 NGZ =   40
   dimension x,y,z NGXF=    80 NGYF=   80 NGZF=   80
   support grid    NGXF=    80 NGYF=   80 NGZF=   80
   ions per type =               1
 NGX,Y,Z   is equivalent  to a cutoff of   8.31,  8.31,  8.31 a.u.
 NGXF,Y,Z  is equivalent  to a cutoff of  16.62, 16.62, 16.62 a.u.


 I would recommend the setting:
   dimension x,y,z NGX =    39 NGY =   39 NGZ =   39
 SYSTEM =  O atom
 POSCAR =  O atom in a box

 Startparameter for this run:
   NWRITE =      2    write-flag & timer
   PREC   = normal    normal or accurate (medium, high low for compatibility)
   ISTART =      0    job   : 0-new  1-cont  2-samecut
   ICHARG =      2    charge: 1-file 2-atom 10-const
   ISPIN  =      1    spin polarized calculation?
   LNONCOLLINEAR =      F non collinear calculations
   LSORBIT =      F    spin-orbit coupling
   INIWAV =      1    electr: 0-lowe 1-rand  2-diag
   LASPH  =      F    aspherical Exc in radial PAW
   METAGGA=      F    non-selfconsistent MetaGGA calc.
```
#### 本计算的文字描述，任务类型
```
Static calculation
charge density and potential will be updated during run
non-spin polarized calculation
Variant of blocked Davidson
Davidson routine will perform the subspace rotation
perform sub-space diagonalisation
   after iterative eigenvector-optimisation
modified Broyden-mixing scheme, WC =      100.0
initial mixing is a Kerker type mixing with AMIX =  0.4000 and BMIX =      1.0000
Hartree-type preconditioning will be used
using additional bands            5
reciprocal scheme for non local part
use partial core corrections
calculate Harris-corrections to forces
  (improved forces if not selfconsistent)
use gradient corrections
use of overlap-Matrix (Vanderbilt PP)
Gauss-broadening in eV      SIGMA  =   0.01
```
#### 体积大小，K点数目信息
```
energy-cutoff  :      400.00
volume of cell :      512.00
    direct lattice vectors                 reciprocal lattice vectors
   8.000000000  0.000000000  0.000000000     0.125000000  0.000000000  0.000000000
   0.000000000  8.000000000  0.000000000     0.000000000  0.125000000  0.000000000
   0.000000000  0.000000000  8.000000000     0.000000000  0.000000000  0.125000000

length of vectors
   8.000000000  8.000000000  8.000000000     0.125000000  0.125000000  0.125000000



k-points in units of 2pi/SCALE and weight: KPOINTS
 0.00000000  0.00000000  0.00000000       1.000

k-points in reciprocal lattice and weights: KPOINTS
 0.00000000  0.00000000  0.00000000       1.000

position of ions in fractional coordinates (direct lattice)
 0.00000000  0.00000000  0.00000000

position of ions in cartesian coordinates  (Angst):
 0.00000000  0.00000000  0.00000000
```
#### 计算所需的内存信息
```
maximum and minimum number of plane-waves per node :      9315     9315

maximum number of plane-waves:      9315
maximum index in each direction:
  IXMAX=   13   IYMAX=   13   IZMAX=   13
  IXMIN=  -13   IYMIN=  -13   IZMIN=  -13

WARNING: aliasing errors must be expected set NGX to  54 to avoid them
WARNING: aliasing errors must be expected set NGY to  54 to avoid them
WARNING: aliasing errors must be expected set NGZ to  54 to avoid them
aliasing errors are usually negligible using standard VASP settings
and one can safely disregard these warnings

serial   3D FFT for wavefunctions
parallel 3D FFT for charge:
   minimum data exchange during FFTs selected (reduces bandwidth)


total amount of memory used by VASP on root node    44539. kBytes
========================================================================

  base      :      30000. kBytes
  nonl-proj :        745. kBytes
  fftplans  :       4661. kBytes
  grid      :       8832. kBytes
  one-center:          3. kBytes
  wavefun   :        298. kBytes

    INWAV:  cpu time    0.0000: real time    0.0000
Broyden mixing: mesh for mixing (old mesh)
  NGX = 27   NGY = 27   NGZ = 27
 (NGX  = 80   NGY  = 80   NGZ  = 80)
 gives a total of  19683 points

initial charge density was supplied:
charge density of overlapping atoms calculated
number of electron       6.0000000 magnetization
keeping initial charge density in first step
```
#### 开始电子步迭代过程
```
----------------------------------------- Iteration    1(   1)  ---------------------------------------


    POTLOK:  cpu time    0.0880: real time    0.0882
    SETDIJ:  cpu time    0.0018: real time    0.0018
     EDDAV:  cpu time    0.0313: real time    0.0314
       DOS:  cpu time    0.0001: real time    0.0001
    --------------------------------------------
      LOOP:  cpu time    0.1219: real time    0.1220

 eigenvalue-minimisations  :    16
 total energy-change (2. order) : 0.3846838E+02  (-0.9672571E+02)
 number of electron       6.0000000 magnetization
 augmentation part        6.0000000 magnetization

 Free energy of the ion-electron system (eV)
  ---------------------------------------------------
  alpha Z        PSCENC =         0.27139542
  Ewald energy   TEWEN  =       -91.92708002
  -Hartree energ DENC   =      -281.84385743
  -exchange      EXHF   =         0.00000000
  -V(xc)+E(xc)   XCENC  =        26.06853627
  PAW double counting   =       346.54947689     -348.34814756
  entropy T*S    EENTRO =        -0.00000000
  eigenvalues    EBANDS =       -44.56514455
  atomic energy  EATOM  =       432.26319604
  Solvation  Ediel_sol  =         0.00000000
  ---------------------------------------------------
  free energy    TOTEN  =        38.46837506 eV

  energy without entropy =       38.46837506  energy(sigma->0) =       38.46837506


--------------------------------------------------------------------------------------------------------
```
#### 迭代结束，输出主要结果：费米能级以及能带信息。
```
average (electrostatic) potential at core
 the test charge radii are     0.7215
 (the norm of the test charge is              1.0000)
      1 -83.5439



E-fermi :  -8.9012     XC(G=0):  -0.8046     alpha+bet : -0.1463


k-point     1 :       0.0000    0.0000    0.0000
 band No.  band energies     occupation
     1     -23.8440      2.00000
     2      -8.9042      1.33333
     3      -8.9042      1.33333
     4      -8.9042      1.33333
     5      -0.4679      0.00000
     6       1.8630      0.00000
     7       1.8630      0.00000
     8       1.8630      0.00000
```
#### 体系的坐标，各个方向力的大小，以及总的能量
```
------------------------ aborting loop because EDIFF is reached ----------------------------------------


    CHARGE:  cpu time    0.0148: real time    0.0150
    FORLOC:  cpu time    0.0042: real time    0.0042
    FORNL :  cpu time    0.0027: real time    0.0027
    STRESS:  cpu time    0.0366: real time    0.0365
    FORCOR:  cpu time    0.0847: real time    0.0848
    FORHAR:  cpu time    0.0194: real time    0.0194
    MIXING:  cpu time    0.0037: real time    0.0036
    OFIELD:  cpu time    0.0000: real time    0.0000

  FORCE on cell =-STRESS in cart. coord.  units (eV):
  Direction    XX          YY          ZZ          XY          YZ          ZX
  --------------------------------------------------------------------------------------
  Alpha Z     0.27140     0.27140     0.27140
  Ewald     -30.64236   -30.64236   -30.64236     0.00000     0.00000     0.00000
  Hartree    93.90332    93.90332    93.90332    -0.00000    -0.00000    -0.00000
  E(xc)     -27.94707   -27.94707   -27.94707    -0.00000     0.00000    -0.00000
  Local    -147.84549  -147.84549  -147.84549    -0.00000     0.00000    -0.00000
  n-local   -20.54950   -20.54950   -20.54950    -0.00000    -0.00000    -0.00000
  augment     5.55386     5.55386     5.55386     0.00000     0.00000     0.00000
  Kinetic   126.51130   126.51129   126.51128    -0.00000     0.00000    -0.00000
  Fock        0.00000     0.00000     0.00000     0.00000     0.00000     0.00000
  -------------------------------------------------------------------------------------
  Total      -0.74455    -0.74455    -0.74455    -0.00000     0.00000    -0.00000
  in kB      -2.32989    -2.32989    -2.32989    -0.00000     0.00000    -0.00000
  external pressure =       -2.33 kB  Pullay stress =        0.00 kB


 VOLUME and BASIS-vectors are now :
 -----------------------------------------------------------------------------
  energy-cutoff  :      400.00
  volume of cell :      512.00
      direct lattice vectors                 reciprocal lattice vectors
     8.000000000  0.000000000  0.000000000     0.125000000  0.000000000  0.000000000
     0.000000000  8.000000000  0.000000000     0.000000000  0.125000000  0.000000000
     0.000000000  0.000000000  8.000000000     0.000000000  0.000000000  0.125000000
```

```
 POSITION                                       TOTAL-FORCE (eV/Angst)
 -----------------------------------------------------------------------------------
      0.00000      0.00000      0.00000         0.000000      0.000000      0.000000
 -----------------------------------------------------------------------------------
    total drift:                               -0.000000     -0.000000     -0.000000


--------------------------------------------------------------------------------------------------------



  FREE ENERGIE OF THE ION-ELECTRON SYSTEM (eV)
  ---------------------------------------------------
  free  energy   TOTEN  =        -0.02147094 eV

  energy  without entropy=       -0.00604471  energy(sigma->0) =       -0.01375782



--------------------------------------------------------------------------------------------------------

```
#### 计算的内存和时间等信息
```
writing wavefunctions
    LOOP+:  cpu time    1.4662: real time    1.4674
   4ORBIT:  cpu time    0.0000: real time    0.0000

total amount of memory used by VASP on root node    44539. kBytes
========================================================================

  base      :      30000. kBytes
  nonl-proj :        745. kBytes
  fftplans  :       4661. kBytes
  grid      :       8832. kBytes
  one-center:          3. kBytes
  wavefun   :        298. kBytes



General timing and accounting informations for this job:
========================================================

                 Total CPU time used (sec):        2.570
                           User time (sec):        2.199
                         System time (sec):        0.371
                        Elapsed time (sec):        3.504

                  Maximum memory used (kb):       76420.
                  Average memory used (kb):           0.

                         Minor page faults:        15941
                         Major page faults:           37
                Voluntary context switches:          270
```

### CONTCAR
包含了VASP计算中最后一步几何优化的结构信息
```
1	O
2	   1.00000000000000
3	     7.5000000000000000    0.0000000000000000    0.0000000000000000
4	     0.0000000000000000    8.0000000000000000    0.0000000000000000
5	     0.0000000000000000    0.0000000000000000    8.9000000000000004
6	   O
7	     2
8	Direct
9	  0.0000000000000000  0.0000000000000000 -0.0016273517369704
10	  0.0000000000000000  0.0000000000000000  0.1372902730852836
11
12	  0.00000000E+00  0.00000000E+00  0.00000000E+00
13	  0.00000000E+00  0.00000000E+00  0.00000000E+00
```
使用分数坐标（Direct坐标），需要转化为笛卡尔坐标
> xy两个方向不用考虑，z方向的坐标相减即可:  
(0.1372726038964550-(-0.0016546263683629))\*8.9 = 1.2364523493568791 （Å）
