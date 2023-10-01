# VASPKIT生成KPOINT文件


- **vaspkit输入文件和计算步骤**

利用vaspkit输出能带计算的精确K点，只需要POSCAR文件

```
vaspkit --> 3 --> 303
```

- **vaspkit输出文件结构**

```
.
├── HIGH_SYMMETRY_POINTS
├── INCAR
├── KPATH.in
├── POSCAR
├── POTCAR
├── PRIMCELL.vasp
└── SYMMETRY

```

1. Do NOT forget to copy PRIMCELL.vasp to POSCAR 
2. 将 KPATH.in 文件复制粘贴成 KPOINTS 文件
3. 修改INCAR文件，主要设置如下
 ```
 ISTART=1
 ICHARG=11
 LCHARG = .FALSE.
 LORBIT=11 # or 10,算投影能带有用
 ```
4. 将修改后的 INCAR、POTCAR、POSCAR 、KPOINTS 以及 CHGCAR 重新提交计算



- **vaspkit输出KPOINTS信息**

```
(base) [root@iZ2zehkhkwkx4pmvvjw2dlZ 01_V2PC]# vaspkit
 
            \\\///         
           / _  _ \         Hey, you must know what you are doing.
         (| (o)(o) |)       Otherwise you might get wrong results.
 o-----.OOOo--()--oOOO.------------------------------------------o
 |         VASPKIT Standard Edition 1.4.1 (26 Apr. 2023)         |
 |         Core Developer: Vei WANG (wangvei@icloud.com)         |
 |      Main Contributors: Gang TANG, Nan XU & Jin-Cheng LIU     |
 |  Online Tutorials Available on Website: https://vaspkit.com   |
 o-----.oooO-----------------------------------------------------o
        (   )   Oooo.                          VASPKIT Made Simple
         \ (    (   )     
          \_)    ) /      
                (_/       
 ===================== Structural Utilities ======================
 1)  VASP Input-Files Generator    2)  Mechanical Properties      
 3)  K-Path for Band-Structure     4)  Structure Editor           
 5)  Catalysis-ElectroChem Kit     6)  Symmetry Analysis          
 7)  Materials Databases           8)  Advanced Structure Models  
 ===================== Electronic Utilities ======================
 11) Density-of-States             21) Band-Structure             
 23) 3D Band-Structure             25) Hybrid-DFT Band-Structure  
 26) Fermi-Surface                 28) Band-Structure Unfolding   
 31) Charge-Density Analysis       42) Potential Analysis         
 51) Wave-Function Analysis        62) Magnetic Properties        
 65) Spin-Texture                  68) Transport Properties       
 ======================== Misc Utilities =========================
 71) Optical Properties            72) Molecular-Dynamics Kit     
 74) User Interface                78) VASP2other Interface       
 91) Semiconductor Kit             92) 2D-Material Kit            
 0)  Quit                                                         
 ------------>>
3
 ===================== K-Path Options ============================
 301) 1D Structure                                                
 302) 2D Structure                                                
 303) Bulk Structure                                              
 304) K-Path for Wannier90 Code                                   
 305) K-Path for Phonopy Code                                     
 306) K-Path for CP2K Code                                        
 309) Visualize K-Path in First Brillouin Zone                    
 
 0) Quit                                                          
 9) Back                                                          
 ------------>>
303
 +---------------------------- Tip ------------------------------+
     See An Example in vaspkit/examples/seek_kpath/GaAs_bulk.        
  The suggested K-Path is only for the standardized primtive cell.
 +---------------------------------------------------------------+
 -->> (01) Reading Structure from POSCAR File...
 +-------------------------- Summary ----------------------------+
                           Prototype: ABC2
           Total Atoms in Input Cell:   8
     Lattice Constants in Input Cell:   3.074   3.074  10.896
        Lattice Angles in Input Cell:  90.000  90.000 120.000
       Total Atoms in Primitive Cell:   8
 Lattice Constants in Primitive Cell:   3.074   3.074  10.896
    Lattice Angles in Primitive Cell:  90.000  90.000 120.000
                      Crystal System: Hexagonal
                       Crystal Class: 6/mmm
                     Bravais Lattice: hP
            Extended Bravais Lattice: hP2
                  Space Group Number: 194
                         Point Group: 27 [ D6h ]
                       International: P6_3/mmc
                 Symmetry Operations:  24
                    Suggested K-Path: (shown in the next line)
 [ GAMMA-M-K-GAMMA-A-L-H-A|L-M|H-K ]
 +---------------------------------------------------------------+
 -->> (02) Written HIGH_SYMMETRY_POINTS File for Reference.
 -->> (03) Written PRIMCELL.vasp file.
 -->> (04) Written KPATH.in File for Band-Structure Calculation.
 o----------------------------WARNING----------------------------o
 | Do NOT forget to copy PRIMCELL.vasp to POSCAR unless you know |
 |   what you are doing. Otherwise you might get wrong results!  |
 o---------------------------------------------------------------o
 -->> (05) Written INCAR file!
 +-------------------------- Summary ----------------------------+
 POTCAR Type: PBE
 Number of Elements: 3
 POTCAR File No.1: [ POTCAR_V_sv ], Valence Electron: 13.0
 POTCAR File No.2: [ POTCAR_P ], Valence Electron: 5.0
 POTCAR File No.3: [ POTCAR_C ], Valence Electron: 4.0
 Total Atoms: 8
 Total Valence Electrons: 70.0
 +---------------------------------------------------------------+
 -->> (06) Written POTCAR File with the Recommended Potential!
 o---------------------------------------------------------------o
 |                       * ACKNOWLEDGMENTS *                     |
 | Other Contributors (in no particular order): Peng-Fei LIU,    |
 | Xue-Fei LIU, Dao-Xiong WU, Zhao-Fu ZHANG, Tian WANG, Qiang LI,|
 | Ya-Chao LIU, Jiang-Shan ZHAO, Qi-Jing ZHENG, Yue QIU and You! |
 | Advisors: Wen-Tong GENG, Yoshiyuki KAWAZOE                    |
 :) Any Suggestions for Improvement are Welcome and Appreciated (:
 |---------------------------------------------------------------|
 |                          * CITATIONS *                        |
 | When using VASPKIT in your research PLEASE cite the paper:    |
 | [1] V. WANG, N. XU, J.-C. LIU, G. TANG, W.-T. GENG, VASPKIT: A|
 | User-Friendly Interface Facilitating High-Throughput Computing|
 | and Analysis Using VASP Code, Computer Physics Communications |
 | 267, 108033, (2021), DOI: 10.1016/j.cpc.2021.108033           |
 o---------------------------------------------------------------o

```

# VASPKIT导出能带数据

```
 ===================== Structural Utilities ======================
 1)  VASP Input-Files Generator    2)  Mechanical Properties      
 3)  K-Path for Band-Structure     4)  Structure Editor           
 5)  Catalysis-ElectroChem Kit     6)  Symmetry Analysis          
 7)  Materials Databases           8)  Advanced Structure Models  
 ===================== Electronic Utilities ======================
 11) Density-of-States             21) Band-Structure             
 23) 3D Band-Structure             25) Hybrid-DFT Band-Structure  
 26) Fermi-Surface                 28) Band-Structure Unfolding   
 31) Charge-Density Analysis       42) Potential Analysis         
 51) Wave-Function Analysis        62) Magnetic Properties        
 65) Spin-Texture                  68) Transport Properties       
 ======================== Misc Utilities =========================
 71) Optical Properties            72) Molecular-Dynamics Kit     
 74) User Interface                78) VASP2other Interface       
 91) Semiconductor Kit             92) 2D-Material Kit            
 0)  Quit                                                         
 ------------>>
21
 ============================ Band Options =======================
 211) Band-Structure                                              
 212) Projected Band-Structure of Only-One-Selected Atom          
 213) Projected Band-Structure of Each Element                    
 214) Projected Band-Structure of Selected Atoms                  
 215) Projected Band-Structure by Element-Weights                 
 216) The Sum of Projected Band for Selected Atoms and Orbitals   
                                                                  
 0)   Quit                                                        
 9)   Back                                                        
 ------------>>
211
 -->> (01) Reading Input Parameters From INCAR File...
 +---------------------------------------------------------------+
 |       >>> The Fermi Energy will be set to zero eV <<<         |
 +---------------------------------------------------------------+
 -->> (02) Reading Fermi-Energy from DOSCAR File...
 -->> (03) Reading Structure from POSCAR File...
 -->> (04) Reading Energy-Levels From EIGENVAL File...
 -->> (05) Reading K-Path From KPOINTS File...
 -->> (06) Written KLABELS File!
 +---------------------------- Tip ------------------------------+
 If You Want to Get Fine Band Structrue by Interpolating Method.
 You CAN set GET_INTERPOLATED_DATA = .TRUE. in ~/.vaspkit file.
 +---------------------------------------------------------------+
 -->> (07) Written BAND.dat File!
 -->> (08) Written REFORMATTED_BAND_UP/DW.dat Files!
 -->> (09) Written KLINES.dat File!
 +-------------------------- Summary ----------------------------+
 +---------------------------------------------------------------+
 -->> (10) Written BAND_GAP File!

```



# VASPKIT导出态密度数据

```
 ===================== Structural Utilities ======================
 1)  VASP Input-Files Generator    2)  Mechanical Properties      
 3)  K-Path for Band-Structure     4)  Structure Editor           
 5)  Catalysis-ElectroChem Kit     6)  Symmetry Analysis          
 7)  Materials Databases           8)  Advanced Structure Models  
 ===================== Electronic Utilities ======================
 11) Density-of-States             21) Band-Structure             
 23) 3D Band-Structure             25) Hybrid-DFT Band-Structure  
 26) Fermi-Surface                 28) Band-Structure Unfolding   
 31) Charge-Density Analysis       42) Potential Analysis         
 51) Wave-Function Analysis        62) Magnetic Properties        
 65) Spin-Texture                  68) Transport Properties       
 ======================== Misc Utilities =========================
 71) Optical Properties            72) Molecular-Dynamics Kit     
 74) User Interface                78) VASP2other Interface       
 91) Semiconductor Kit             92) 2D-Material Kit            
 0)  Quit                                                         
 ------------>>
11
 ============================ DOS Options ========================
 111) Total Density-of-States                                     
 112) Projected Density-of-States of Selected One Atom            
 113) Projected Density-of-States of Each Element                 
 114) Projected Density-of-States of Selected Atoms               
 115) Projected Density-of-States of Selected Atoms and Orbitals  
 116) Local Density-of-States of Each Element                     
 117) Total Density-of-States from EIGENVAL File                  
 118) Projected Density-of-States from EIGENVAL and PROCAR Files  
 119) Projected Density-of-States of Specified K-Indexes            
 120) Projected Density-of-States of Specified Band-Indexes         
                                                                  
 ====================== Real-Space DOS Options ===================
 123) 3D Spatially-Resolved DOS in Specified Energy Range   
 124) 3D Spatially-Resolved Magnetic DOS in Specified Energy Range
 125) 2D Plane-Averaged Spatially-Resolved DOS                    
 126) 2D Plane-Averaged Spatially-Resolved Magnetic DOS           
                                                                  
 0)   Quit                                                        
 9)   Back                                                        
 ------------>>
113
 -->> (01) Reading Input Parameters From INCAR File...
 +---------------------------------------------------------------+
 |       >>> The Fermi Energy will be set to zero eV <<<         |
 +---------------------------------------------------------------+
 -->> (02) Reading Fermi-Energy from DOSCAR File...
 -->> (03) Reading DOS Data From DOSCAR File...
 -->> (04) Reading Structure from POSCAR File...
 -->> (05) Written PDOS_V_UP/DW.dat Files!
 -->> (06) Written IPDOS_V_UP/DW.dat Files!
 -->> (07) Written PDOS_P_UP/DW.dat Files!
 -->> (08) Written IPDOS_P_UP/DW.dat Files!
 -->> (09) Written PDOS_C_UP/DW.dat Files!
 -->> (10) Written IPDOS_C_UP/DW.dat Files!
```




# 参考资料

- https://zhuanlan.zhihu.com/p/526969630
- https://zhuanlan.zhihu.com/p/564983969











