# PyMOL Exercises

The following exercises reinforce the essential commands and workflows
introduced in the PyMOL teaching guide.

Each task should be completed using PyMOL commands rather than the
graphical menus whenever possible.

Structure recommended for the exercises:

Ubiquitin (PDB ID: 1UBQ)

Load the structure:

    fetch 1ubq

------------------------------------------------------------------------

# Exercise 1 --- Basic Visualization

1.  Load the structure 1UBQ.
2.  Hide all default representations.
3.  Display the protein as a cartoon representation.
4.  Set the background color to white.

Commands that may be useful:

    hide everything
    show cartoon
    bg_color white

------------------------------------------------------------------------

# Exercise 2 --- Coloring Chains

1.  Identify whether the structure contains multiple chains.
2.  Color each chain with a different color.
3.  Rotate the structure to inspect the full fold.

Example command:

    color red, chain A

------------------------------------------------------------------------

# Exercise 3 --- Selecting Residues

1.  Select residues 10--20.
2.  Display these residues as sticks.
3.  Color them yellow.

Suggested commands:

    select region, resi 10-20
    show sticks, region
    color yellow, region

------------------------------------------------------------------------

# Exercise 4 --- Distance Measurement

Measure the distance between:

-   the alpha carbon of residue 10
-   the alpha carbon of residue 50

Example syntax:

    distance resi10/CA, resi50/CA

Observe the measured distance displayed in the viewer.

------------------------------------------------------------------------

# Exercise 5 --- Surface Visualization

1.  Display the protein surface.
2.  Set the transparency to 0.4.
3.  Keep the cartoon representation visible.

Commands:

    show surface
    set transparency, 0.4

------------------------------------------------------------------------

# Exercise 6 --- Ligand Identification (General Task)

Load a protein structure that contains a ligand (for example a PDB entry
from the Protein Data Bank).

Tasks:

1.  Identify the ligand.
2.  Display it as sticks.
3.  Highlight nearby residues within 4 Å.

Commands that may help:

    select ligand, organic
    show sticks, ligand
    select pocket, byres ligand around 4
    show sticks, pocket

------------------------------------------------------------------------

# Exercise 7 --- Publication Image

Create a publication-quality image:

1.  Show the protein as cartoon.
2.  Color the protein cyan.
3.  Show any ligand as sticks and color it orange.
4.  Render the scene.
5.  Export the image as PNG.

Example commands:

    ray 2000,2000
    png structure.png, dpi=300

------------------------------------------------------------------------

# Optional Exploration

Consult the PyMOL Wiki for additional commands and examples:

https://pymolwiki.org/Main_Page

Try implementing:

-   secondary structure coloring
-   electrostatic surfaces
-   multiple structure alignment
