# Topological Data Analysis

Repository with information about the course Topological Data Analysis with Persistent Homology. 

Professor [Raphaël Tinarrage](https://raphaeltinarrage.github.io/)

Course website: [https://raphaeltinarrage.github.io/EMAp.html](https://raphaeltinarrage.github.io/EMAp.html)

Course notes: [SummerCourseTDA](https://raphaeltinarrage.github.io/files/EMAp/SummerCourseTDA.pdf)

Exercises and main definitions: [notes](https://lucasmoschen.github.io/files/disciplines/topological-data-analysis/exercises.pdf)

# Table of Contents

- [Topological Data Analysis](#topological-data-analysis)
- [Table of Contents](#table-of-contents)
  - [Abstract](#abstract)
  - [How to use](#how-to-use)
  - [Tutorials](#tutorials)
    - [Tutorial 1](#tutorial-1)
    - [Tutorial 2](#tutorial-2)
    - [Tutorial 3](#tutorial-3)

Abstract
---

This is a topic from applied mathematics with the objective of analyze
datasets using techniques from topology. This framework is insensitive to a
particular metric and provides dimensionality reduction and robustness to
noise. In this course, we aim to understand the basic topological concepts as
topological space and apply it using Python. The tutorials are written by the
professor. 

How to use 
---

For running this project you'll need: 

1. [Clone](https://git-scm.com/docs/git-clone) this repository in your
   machine. 
2. Install
   [Anaconda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html),
   [Python](https://docs.python-guide.org/starting/install3/linux/) and
   [JupyterLab](https://jupyter.org/install). 
3. Create the environment with the same `environment.yml` file, just using
   `conda` command. [More
   details](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-from-an-environment-yml-file).


After that, enter in the jupyter environment and run the notebooks as you
wish. 

Tutorials 
---

### Tutorial 1

In this tutorial, we implement the concept of triangulation of topological spaces. It's a simplicial complex homeomorphic to the space. This simplicial complex is a combinatorial representation with finite points. For instance, the representation of a triangle graph is a triangulation of the circle. Here we use the library [NetworkX](https://networkx.org/) to draw the graph representation. 

![circle](images/circle-triangulation.png)

We can also represent the torus triangulation. 

![torus](images/torus-triangulation.png)

After these, with the library [GUDHI](https://gudhi.inria.fr/), we can calculate the number of connected componentes and the Euler characteristic. We can see the behavior of these characteristics in the Erdős–Rényi graph. 

![erdos](images/graph-erdos-n-components.png)

### Tutorial 2 

Were we study the concept of Homology, t-thickening and the Betti curves, that
are related, with "holes" in each dimension. For example, $\beta_0$ indicates
the number of connected components, $\beta_1$ the number of circular holes and
$\beta_2$ empty volumes. In the practice, we only have a finite number of
points in some space and with topology inference one can understand the
homology of these points. For example, consider some points of the circle and
its thickening with $t = 0.2$.

![](images/thickening-circle.png) 

Observe with that value we have one connected component, but does not have a
hole. Therefore it's homotopy equivalent to a point. Below we see the first
Betti Curve of an a series of data points with a lot of noisy. For each $t$ we
calculate the Betti Number of a triangulation of the t-thickening. We can
infer the real first Betti number is 2. 

![](images/betti-curve-1-torus.png)

We also consideres two interesting datasets: one with images and another with
proteins. Please see the notebooks for more details. 

### Tutorial 3 

In this tutorial we apply persistent homology. We start building a filtration
using the `SimplexTree` object and with that we can compute the persistence
(barcodes) of the simplicial complex. The `Gudhi` library helps plotting the
persistance barcode and diagram as you can see (this is a simple example
without noise):

![persistence](images/persistence-barcode-diagram.png)

With this barcode one can infer the Betti numbers of this, in special $\beta_0
= 1$ and $\beta_1 = 1$ (a circle). 

However the dataset may have noisy and outliers as we have seen in the Betti
curves.

<img src = "images/circle-noisy.png" width = 250>

However with the Persistence Barcode we still can infere it's a circle!

<img src = "images/persistence-barcode-diagram2.png" width = 600>

We've applied this knowledge to interesting datasets and one of them involved
a time series of a played note by a flue and a clarinet. We wanted to
understand if they were topologically different. In order to do that we
transform the data embedding in a higher dimension considering the points
being part of the initial sequence, what we call time delay. For example, for
the clarinet we observed, for a small sample:

The first image is the time series, while the second id its embedding. We
observe its a circle, what is pretty interesting 

<img src = "images/clarinet.png" width = 600>

For more details, consult the notebook and the notes! 