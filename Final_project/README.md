## Final Project Ideas


![Proj_1](https://github.com/jmou2/PaviaProteinDesign/blob/main/Final_project/proj_1.png?raw=true)

![Proj_2](https://github.com/jmou2/PaviaProteinDesign/blob/main/Final_project/proj_2.png?raw=true)

![Proj_3](https://github.com/jmou2/PaviaProteinDesign/blob/main/Final_project/proj_3.png?raw=true)

![Proj_4](https://github.com/jmou2/PaviaProteinDesign/blob/main/Final_project/proj_4.png?raw=true)


## Final Project Presentations

Each of you will have 10 minutes to present your project results. An example outline could be:
- An introduction to your design problem and why it is important. If you are using a natural protein, what does it do?
- Results of your design problem. What did you try? What structures were generated?
- Analysis of your results. What is the AlphaFold pLDDT and RMSD?

You may make 3-4 slides and/or PyMol scenes.

To make a scene, type `scene scene_name, store` in PyMol and an icon called `scene_name` will be created on the bottom left. This scene stores the position, coloring, and visible portions of your PyMol session. You will also want to save your pymol session: "save" --> "save session as" . This will create a `.pse` file that you can open in PyMol.

## Some Pymol tips

# How to save two proteins in one pdb file
1. Load two proteins in Pymol. (For this examples, let's call them protein1 and protein2.)
2. If they have the same chain ID, rename one of the chains (for example, of protein2) by typing: alter protein2, chain="B"
3. To save the two proteins in one pdb, type: save fusion.pdb, protein1 or protein2

# How to move coordinates of an object
To move the coordinates of a pymol object, let's say protein1, you would click in the righthand menu next to the "protein1" object name, A (for "Action"), then "drag coordinates". Then hold the "shift" key on your keyboard, and center-click your mouse on the protein1 object. While holding shift and the center mouse button, move the mouse to drag the protein. Once done, click "Done" in the righthand menu.


