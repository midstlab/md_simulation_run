## Giving an MD simulation by using wrappers
#### Warning: This tutorial assumes that you did tutorials of VMD and NAMD, and you have an idea about Python programming language.
1. Preparation of the system    
    1. AutoPSF process
    2. Solvation (putting protein in a waterbox)
    3. Ionization (setting the system to a 0.15 molar solution)  
2. Performing the MD simulation with a configuration file
***
### Requirements:
- Python: prody and numpy packages
- VMD
- NAMD
---
### Step by step giving the MD simulation
1. Download the pdb structure, inspect it and delete anything unnecessery like crystal waters (if you are sure). In the following steps, scripts find any *PDB* file in the directory and run their codes by using that file or files (batch jobs).
2. You will use VMD for prep:  
  By writing *vmd -dispdev text -e autopsf_batch.tcl* to terminal you can perform AutoPSF, solvation and ionization processes. Please see the inside of *autopsf_batch.tcl* file. You will see each command seperately. Now, you have a protein in a waterbox with a minimum distance of 10 Angstrom to the protein. The system is izotonic (0.15 molar) with KCl salt. Please be careful about the topology files.  
3. To write a configuration file, you will use *config_generator.py*; you should set timesteps of minimization and MD simulation.
4. You can use *config_file_jobgen.py* script to write multiple namd2 terminal command for configuration files you wrote, again please take a look at number of cores in this file.
