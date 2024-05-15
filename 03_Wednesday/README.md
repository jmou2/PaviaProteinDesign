## Day 3: User-Guided Protein Design

All slides will be on the [dropbox](https://www.dropbox.com/scl/fo/vuxoqeknepm0tpyx1wcmy/ANFlm2jiOpafGzb12vklr44?rlkey=49zv6kti2tapr0jafcwhdrym6&e=2&dl=0).


### Schedule


| time | activity | slides/links |
|---|---|---|
| 2-3p | Tutorial 1 - Designing Coiled Coil proteins with AlphaFold |  |
| 3-4p | Paper Lecture 1 | [Robust deep learning-based protein sequence design using ProteinMPNN](https://www.science.org/doi/10.1126/science.add2187) |
| 3-5p | Tutorial 2 - ProteinMPNN |  |
| 5-6p | Final Project Discussion |  |



### Tutorial 1 - Designing Coiled Coil proteins with AlphaFold

#### Step 1 - Make mutations
Upload `coiled_coil_start.pdb` into pymol. Make mutations to stabilize the structure using pymol's mutation wizard. Download the sequence of the protein after the mutations you made by saving as a fasta file ("save filename.fasta, objectname").

#### Step 2 - Alphafold/Colabfold
Use the online [colabfold notebook](https://colab.research.google.com/github/sokrypton/ColabFold/blob/main/AlphaFold2.ipynb) to predict the structure of the sequence. Is the best prediction still a 4-helix bundle? If not, start over from Step 1 and make different mutations until you get a predicted 4-helix bundle. The goal is to mutate the protein to increase the confidence of the prediction (the pLDDT) and maintain the same protein fold. Load the predicted structure into pymol and look at how different it is from the original.

#### Step 3 - Repeat! 
Load your newly predicted structure into pymol. If it is still a 4-helix bundle and has a higher pLDDT than your previously predicted structure, continue optimizing the sequence for the structure through mutations in Pymol. Then predict the structure of the new sequence as in Step 2. Continue folding/mutating until you achieve a 4-helix bundle structure in which AlphaFold2 is highly confident.

### Suggested design goals
1. Mutate core residues to optimize van der Waals packing between sidechains. Use mutations to minimize the "void volume" (internal cavities).
2. Maintain hydrophobic residues in the interior and hydrophilic residues on the exterior of the protein
3. Form "salt-bridges" (i.e. electrostatic interactions between oppositely charged residues) between helices where you can
4. More advanced: change the sequence in the loop regions. Instead of GGG loops, mutate to residues that might also favor loop formation by 1) breaking the helix, 2)packing with the rest of the protein, or 3) interacting favorably with the helix backbone atoms.

#### Tips for pymol visualizations:

To show inside cavities:
- go to command panel --> show surface 
- "settings" --> "surface" --> "cavities and pockets only"
- type `set transparency, 0.5`

To make mutations:
- "wizard" --> "mutagenesis" --> "protein"
- click on a residue
- "no mutation" --> pick an amino acid of your choice
- click through different rotamers using arrows on bottom right
- "apply"
- save fasta file ("save filename.fasta, objectname")

