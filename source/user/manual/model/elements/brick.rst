.. _stdBrick::

stdBrick Element
^^^^^^^^^^^^^^^^

This command is used to construct an eight-node brick element object, which uses the standard isoparametric formulation.

.. function:: element stdBrick $eleTag $node1 $node2 $node3 $node4 $node5 $node6 $node7 $node8 $matTag <$b1 $b2 $b3>

.. csv-table:: 
   :header: "Argument", "Type", "Description"
   :widths: 10, 10, 40

   $eleTag, |integer|,	unique element object tag
   $node1 .. $node8, 8 |integer|, nodes of brick (ordered as shown in fig below)
   $matTag, |integer|, tag of nDMaterial
   $b1 $b2 $b3, |listFloat|, optional: body forces in global x,y,z directions

.. note::

   The valid queries to a Brick element when creating an ElementRecorder object are 'forces', 'stresses,' ('strains' version > 2.2.0) and 'material $matNum matArg1 matArg2 ...' Where $matNum refers to the material object at the integration point corresponding to the node numbers in the isoparametric domain.
This element can only be defined in -ndm 3 -ndf 3

 .. admonition:: Example 

   The following example constructs a brick element with tag **1** between nodes **1, 2, 3, 4, 5, 6, 7, 8** with an nDMaterial of tag **1** and body forces given by varaiables **b1, b2, b3**.

   1. **Tcl Code**

   .. code-block:: tcl

      element stdBrick 1 1 2 3 4 5 6 7 8 1 $b1 $b2 $b3

   2. **Python Code**

   .. code-block:: python

      element('stdBrick',1,2,3,4,5,6,7,8,1, b1, b2, b3)

Code Developed by: **Edward Love, Sandia National Laboratories**