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


### Tutorial 2 - Using ProteinMPNN to design protein sequence

ProteinMPNN is a deep learning model that uses a graph neural network (GNN) to design the sequence of a protein given the backbone atom locations. 

The main input options for ProteinMPNN are:

| input | description | example | notes |
|---|---|---|---|
| `pdb_input` | path to PDB file | `1ABCD.pdb` | must have all the backbone atoms: N, CA, C, O |
| `chains_to_design` | chains in which the sequence is designed | `A` designs chain A, `A B` designs chain A & B | If a chain in the PDB file is not listed, it is ignored entirely |
| `chains_to_fix` | chains in which the sequence is fixed | same as above | The sequence and structure of the fixed chains will be used as context for determining the structure of the designed chains. |
`residues_to_design` | residues for which sequence is designed |  `1 2 3 6, 1 5 6 8` designs positions 1,2,3,6 on chain A and 1,5,6,8 on chain B |  **the fixed residue numbers begin from 1 (the first residue in the structure), and do not refer to the resnums in the PDB file** |
`residues_to_fix` | residues for which sequence is fixed | same as above | use either `residues_to_fix` or `residues_to_design` not both|
`score_only`| do not redesign sequence, score the given sequence of designed chains/residues | `0` = false, `1` = true | required if using ProteinMPNN to score sequences |
`save_probs` |  whether to save a probability matrix of the output sequence | `0` = false, `1` = true | |


Here are some examples of how we might use ProteinMPNN to achieve different goals:

![ProteinMPNN_diagram](https://github.com/jmou2/PaviaProteinDesign/blob/main/03_Wednesday/proteinmpnn_diagram.png?raw=true)

| design goal | `chains_to_design` | `chains_to_fix` | `residues_to_design` | 
|---|---|---|---|
| design or re-design the sequence of a protein structure | `A` | n/a | n/a | 
| redesign part of a protein chain while keeping rest of sequence fixed | `A` | n/a |`50 51 52 53 54 55 56 57 58 59 60` |
| design a peptide binder | `B` | `A` | n/a | 
| design a binding interface | `A B` | n/a | `55 57 59, 2 5 8` |
