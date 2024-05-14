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
Upload `coiled_coil_start.pdb` into pymol. Make mutations to stabilize the structure. Download the sequence of the protein after the mutations you made by saving as a fasta file.

#### Step 2 - Alphafold/Colabfold
Use the online [colabfold notebook](https://colab.research.google.com/github/sokrypton/ColabFold/blob/main/AlphaFold2.ipynb) to do predict the structure of the sequence. Look at the confidence of the prediction (the pLDDT). Load the predicted structure into pymol and look at how different it is from the original.

#### Step 3 - Repeat! 
Based on the folded structure of the protein and the confidence prediction, go back to step 1 and make more mutations to your already-mutated sequence. Continue folding/mutating until you achieve a structure that is highly confidently predicted to fold into a coiled coil.

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
- save fasta file

