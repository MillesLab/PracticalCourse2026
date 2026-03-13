# PyMOL Exercises

The following exercises reinforce the essential commands and workflows
introduced in the PyMOL teaching guide.

Each task should be completed using PyMOL commands rather than the
graphical menus whenever possible.

We are using the structure we want to redesign during this practical
course. First find basic facts about the protein in UniProt.

https://www.uniprot.org/uniprotkb/P02976/entry

### Exercise --- Note some basic facts about Protein A

Note some facts about the protein from UniProt.

Record at least:

-   Organism
-   Protein length
-   Cellular location
-   Function
-   Any structural notes mentioned in the annotation

### Exercise --- Basic Visualization

1.  Load the structure from the folder `input_pdbs`. For redesign we are
    using the AlphaFold structure: `AF-P02976-F1-model_v6.pdb`. For now
    we use the file from the PDB: `1BDD`.
2.  Hide all default representations.
3.  Display the protein as a cartoon representation.
4.  Show and hide the surface.
5.  Show and hide residues.
6.  Explore the structure: center at different positions, translate,
    rotate, and zoom.

Commands that may be useful:

```
hide everything
show cartoon
show lines
show surface
```

Notice the alpha‑helical structure of Protein A. In the next section, we
will take one of these helices and graft it onto a newly designed
backbone.

------------------------------------------------------------------------

### Exercise --- Coloring Chains

1.  Identify whether the structure contains multiple chains.
2.  Color each chain with a different color.
3.  Rotate the structure to inspect the full fold.

Example command:

```
color red, chain A
```

------------------------------------------------------------------------

### Exercise --- Selecting Residues

1.  Select residues 10--20.
2.  Display these residues as sticks.
3.  Color them yellow.

Suggested commands:

```
select region, resi 10-20
show sticks, region
color yellow, region
```

------------------------------------------------------------------------

### Exercise --- Distance Measurement

Measure the distance between:

-   the alpha carbon of residue 10
-   the alpha carbon of residue 50

Example syntax:

```
distance resi10/CA, resi50/CA
```

Observe the measured distance displayed in the viewer.

------------------------------------------------------------------------

### Exercise --- Surface Visualization

1.  Display the protein surface.
2.  Set the transparency to 0.4.
3.  Keep the cartoon representation visible.

Commands:

```
show surface
set transparency, 0.4
```

------------------------------------------------------------------------

### Exercise --- Ligand Identification (General Task)

Load a protein structure that contains a ligand (for example a PDB entry
from the Protein Data Bank). For example:

```
1AI9
```

Tasks:

1.  Remove water for convenience.
2.  Identify the ligand.
3.  Display it as sticks.
4.  Highlight nearby residues within 4 Å.

Commands that may help:

```
remove sol
select ligand, organic
select ligand, not polymer.protein
select pocket, byres ligand around 4
show sticks, pocket
```

------------------------------------------------------------------------

### Exercise --- Publication Image

Create a publication-quality image:

1.  Show the protein as cartoon.
2.  Color the protein cyan.
3.  Show any ligand as sticks and color it orange.
4.  Render the scene.
5.  Export the image as PNG.

Example commands:

```
ray 2000,2000
png structure.png, dpi=300
```

------------------------------------------------------------------------

### Exercise --- Selecting a Helix (More Advanced)

Protein A consists primarily of alpha helices. Select one helix and
display it separately.

Tasks:

1.  Identify one helix visually.
2.  Select the residues belonging to that helix.
3.  Display only that helix as sticks or cartoon.
4.  Color the helix differently from the rest of the protein.

Hint:

Use residue ranges when creating selections.

Example:

```
select helix1, resi 20-35
show sticks, helix1
color red, helix1
```

You can also hide everything except the helix to inspect it more
clearly.

------------------------------------------------------------------------

### Exercise --- Finding Neighbouring Residues (More Advanced)

Often we want to know which residues interact with a specific region or
residue.

Tasks:

1.  Choose one residue (for example residue 25).
2.  Identify residues within 5 Å of this residue.
3.  Display those residues as sticks.
4.  Color them differently from the rest of the protein.

Hint:

PyMOL has powerful selection expressions using the keyword `around`.

Example:

```
select neighbors, resi 25 around 5
show sticks, neighbors
color orange, neighbors
```

Try visualizing how residues pack around each other in the helix bundle.

------------------------------------------------------------------------

### Optional Exploration

Consult the PyMOL Wiki for additional commands and examples:

https://pymolwiki.org/Main_Page

Try implementing:

-   secondary structure coloring
-   electrostatic surfaces
-   multiple structure alignment
