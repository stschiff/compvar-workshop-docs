Principal Components Analysis (PCA)
===================================

Principal components analysis (PCA) is one of the most useful techniques to visualise genetic diversity in a dataset. The methodology is not restricted to genetic data, but in general allows breaking down high-dimensional datasets to two or more dimensions for visualisation in a two-dimensional space.

Genotype Data
-------------

This lesson is also our first contact with the genotype data used in this and most of the following lessons. The dataset that we will work with contains 3,902 individuals, each represented by 593,124 single nucleotide polymorphisms (SNPs). Those SNPs have exactly two different alleles, and each individual has one of four possible values at each genotype: homozygous reference, heterozygous, homozygous alternative, or missing. Those four values are encoded 2, 1, 0 and 9 respectively. 

The data is laid out as a matrix, with columns indicating individuals, and rows indicating SNPs. The data itself comes in the so-called "EIGENSTRAT" format, which is defined in the `Eigensoft package`_ used by many tools used in this workshop. In this format, a genotype dataset consists of three files, usually with the following file endings:

*.snp
  The file containing the SNP positions. It consists of six columns: SNP-name, chromosome, genetic positions, physical position, reference allele, alternative allele.
*.ind
  The file containing the names of the individuals. It consists of three columns: Individual Name, Sex (encoded as M(ale), F(emale), or U(nknown)), and population name.
*.geno
  The file containing the genotype matrix, with individuals laid out from left to right, and SNP positions laid out from top to bottom.
  
.. _Eigensoft package: https://github.com/DReichLab/EIG

.. admonition:: Exercise

  Explore the three files used in the workshop. They are located unser ``~/share/genotype_data``. You can use the bash terminal, and use ``less -S <FILENAME>`` to view each file and skim through it to get a feeling for the data. Alternatively, you can create use a Bash notebook, use ``cd`` as above, and then use the unix tools ``head`` in combination with ``cut`` to show portions of the files (see solutions notebook ``02_pca_bash``).

.. admonition:: Exercise

  Confirm that there are 3,902 individuals in the dataset. (Advanced) Count how many different populations there are. Hint: You can use the Unix tools ``awk '{print $3}'``, ``sort`` and ``uniq -c`` to achieve that (see solutions notebook ``02_pca_bash``).

How PCA works
-------------

To understand how PCA works, consider a single individual and its representation by its 593,124 markers. Formally, each individual is a point in a 593,124-dimensional space, where each dimension
can take only the three possible genotypes indicated above, or have missing data. To visualise this high-dimensional dataset, we would like to project it down to two dimensions. But as there are many ways to project the shadow of a three-dimensional object on a two dimensional plane, there are many (and even more) ways to project a 593,124-dimensional cloud of points to two dimensions. What PCA does is figuring out the "best" way to do this project in order to visualise the major components of variance in the data.

Running ``smartPCA``
--------------------

For actually running the analysis, we use a software called ``smartPCA`` from the `Eigensoft package`_. As many other tools from this and related packages, ``smartPCA`` reads in a parameter file which specifies its input and output files and options.


