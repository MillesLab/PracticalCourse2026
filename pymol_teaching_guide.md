# Introduction to PyMOL

PyMOL is a molecular visualization system widely used in structural
biology, biochemistry, and bioinformatics. It allows researchers to
inspect molecular structures, produce publication-quality images, and
analyze structural interactions such as binding sites and distances
between atoms.

Official documentation and community reference:
https://pymolwiki.org/Main_Page

This short guide introduces the essential commands and concepts required
to begin working productively with PyMOL.

------------------------------------------------------------------------

### 1. Loading Molecular Structures

PyMOL commonly works with structures from the Protein Data Bank (PDB).

Load a local structure:

    load structure.pdb

Fetch a structure directly from the Protein Data Bank:

    fetch 1ubq

The fetched structure will appear in the viewer immediately.

------------------------------------------------------------------------

### 2. Navigation

Mouse controls:

  Action      Mouse
----------- --------------
  Rotate      Left mouse
  Translate   Middle mouse
  Zoom        Right mouse

Reset the camera:

    reset

Center the view on a structure:

    center

------------------------------------------------------------------------

### 3. Molecular Representations

Different graphical representations highlight different structural
aspects.

Show a representation:

    show <representation>, selection

Hide a representation:

    hide <representation>, selection

Important representations:

Cartoon representation (commonly used for proteins):

    show cartoon

Sticks representation (useful for ligands and side chains):

    show sticks

Sphere representation (space-filling atoms):

    show spheres

Surface representation:

    show surface

------------------------------------------------------------------------

### 4. Coloring Structures

Color the entire object:

    color blue

Color a specific chain:

    color red, chain A
    color green, chain B

Color atoms according to element; in blue for example:

    util.cbab

------------------------------------------------------------------------

### 5. Selections

Selections allow specific atoms or residues to be manipulated.

Basic syntax:

    select name, selection_expression

Example:

    select active_site, resi 45+67+89

Common selection keywords:

  Keyword    Meaning
---------- ------------------
  chain A    chain identifier
  resi 45    residue number
  resn ATP   residue name
  name CA    alpha carbon

Example:

    select helix_region, resi 10-30

------------------------------------------------------------------------

### 6. Measuring Distances

Distance between two atoms:

    distance atom1, atom2

Example:

    distance resi45/CA, resi78/CA

Delete a measurement:

    delete dist01

------------------------------------------------------------------------

### 7. Working with Ligands

Select organic molecules:

    select ligand, organic

Show ligand as sticks:

    show sticks, ligand

Display residues near the ligand:

    select pocket, byres ligand around 4
    show sticks, pocket

------------------------------------------------------------------------

### 8. Surfaces and Transparency

Display protein surface:

    show surface

Adjust transparency:

    set transparency, 0.5

------------------------------------------------------------------------

### 9. Producing Figures

Set background color:

    bg_color white

Render high-quality image:

    ray 2000,2000

Save image:

    png figure.png, dpi=300

------------------------------------------------------------------------

### 10. Saving Sessions

Save work:

    save session.pse

Load session later:

    load session.pse

------------------------------------------------------------------------

### Summary

Essential PyMOL skills include:

1.  Loading structures
2.  Switching molecular representations
3.  Coloring molecules
4.  Creating selections
5.  Measuring structural features
6.  Generating publication-quality figures

Further reference and advanced usage examples can be found at:

https://pymolwiki.org/Main_Page
