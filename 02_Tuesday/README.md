## Day 2: Introduction to protein design tools part 2

All slides will be on the [dropbox](https://www.dropbox.com/scl/fo/vuxoqeknepm0tpyx1wcmy/ANFlm2jiOpafGzb12vklr44?rlkey=49zv6kti2tapr0jafcwhdrym6&e=2&dl=0).

### Schedule


| time | activity | slides/links |
|---|---|---|
| 2-2:30p | Tutorial 1 - Electron Density |  |
| 2:30-3p | Paper Lecture 1 - AlphaFold 2 | [Highly accurate protein structure prediction with AlphaFold](https://www.nature.com/articles/s41586-021-03819-2)  |
| 3-4p | Tutorial 2 - ProDy and AlphaFold | [Part 1 - ProDy](https://github.com/jmou2/PaviaProteinDesign/blob/main/02_Tuesday/tutorial_2_intro_to_prody.ipynb) <br> [Part 2 - AlphaFold](https://github.com/jmou2/PaviaProteinDesign/blob/main/02_Tuesday/tutorial_2_alphafold.ipynb)
| 4-4:30p | Lecture 2 - Coiled Coils | |
| 4:30-5:30p | Tutorial 3 - Designing Coiled Coil proteins with AlphaFold |  |
| 5:30-6p | Introduction to Final Project |  |


### Tutorial 1 - Electron Density

In this tutorial, we will continue yesterday's exercise of looking at electron densities. 

In pymol, type the following:

`fetch 3ry2` - download the streptavidin-biotin complex structure 

`fetch 3ry2, type=2fofc` - download the electron density map

`fetch 3ry2, type=fofc` - download the omit map

Go to "wizard" --> "density"

### Tutorial 2 - ProDy and AlphaFold 

We will start with the [tutorial_2_intro_to_prody](https://github.com/jmou2/PaviaProteinDesign/blob/main/02_Tuesday/tutorial_2_intro_to_prody.ipynb) notebook. Open the notebook and click the 'open in Colab' button at the top and follow the instructions.

Next, we will do the alphafold task, [tutorial_2_alphafold](https://github.com/jmou2/PaviaProteinDesign/blob/main/02_Tuesday/tutorial_2_alphafold.ipynb). This notebook has many code sections where you will write your own code. You may wish to adapt code from the ProDy introduction notebook for this task.

If you feel you need an introduction to the Python programming language before this tutorial, try going through this intro to python notebook [here](https://colab.research.google.com/github/data-psl/lectures2020/blob/master/notebooks/01_python_basics.ipynb). 
