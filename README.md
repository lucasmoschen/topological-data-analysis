# Topological Data Analysis

Repository with information about the course Topological Data Analysis with Persistent Homology. 

Professor [Rapha¨el Tinarrage](https://raphaeltinarrage.github.io/)

Course website: [https://raphaeltinarrage.github.io/EMAp.html](https://raphaeltinarrage.github.io/EMAp.html)

Course notes: [SummerCourseTDA](https://raphaeltinarrage.github.io/files/EMAp/SummerCourseTDA.pdf)

Exercises and main definitions: [notes](https://github.com/lucasmoschen/topological-data-analysis/blob/main/notes/exercises.pdf)

# Table of Contents

1. [Abstract](#abstract)
2. [Tutorials](#tutorials)
   1. [Tutorial 1](#tutorial-1)

Abstract
---

This is a topic from applied mathematics with the objective of analyze
datasets using techniques from topology. This framework is insensitive to a
particular metric and provides dimensionality reduction and robustness to
noise. In this course, we aim to understand the basic topological concepts as
topological space and apply it using Python. The tutorials are written by the professor. 

Tutorials 
---

### Tutorial 1

In this tutorial, we implement the concept of triangulation of topological spaces. It's a simplicial complex homeomorphic to the space. This simplicial complex is a combinatorial representation with finite points. For instance, the representation of a triangle graph is a triangulation of the circle. Here we use the library [NetworkX](https://networkx.org/) to draw the graph representation. 

![circle](images/circle-triangulation.png)

We can also represent the torus triangulation. 

![torus](images/torus-triangulation.png)

After these, with the library [GUDHI](https://gudhi.inria.fr/), we can calculate the number of connected componentes and the Euler characteristic. We can see the behaviour of these characteristics in the Erdős–Rényi graph. 

![erdos](images/graph-erdos-n-components.png)
