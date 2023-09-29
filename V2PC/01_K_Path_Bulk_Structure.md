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





