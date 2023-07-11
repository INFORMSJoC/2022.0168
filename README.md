[![INFORMS Journal on Computing Logo](https://INFORMSJoC.github.io/logos/INFORMS_Journal_on_Computing_Header.jpg)](https://pubsonline.informs.org/journal/ijoc)

# [Distributionally Robust Bilevel Programming](https://doi.org/10.1287/ijoc.2022.0168)

This archive is distributed in association with the [INFORMS Journal on
Computing](https://pubsonline.informs.org/journal/ijoc) under the [GNU GPLv3](LICENSE).

The software and data in this repository are a snapshot of the software and data
that were used in the research reported on in the paper 
[Decision Rule Approaches for Pessimistic Bilevel Linear Programs under Moment Ambiguity with Facility Location Applications](https://doi.org/10.1287/ijoc.2022.0168) by A. Goyal, Y. Zhang, and C. He. 
The snapshot is based on 
[this SHA](https://github.com/tkralphs/JoCTemplate/commit/f7f30c63adbcb0811e5a133e1def696b74f3ba15) 
in the development repository. 

## Cite

To cite the contents of this repository, please cite both the paper and this repo, using their respective DOIs.

https://doi.org/10.1287/ijoc.2022.0168

https://doi.org/10.1287/ijoc.2022.0168.cd

Below is the BibTex for citing this snapshot of the respoitory.

```
@article{Goyal2023decision,
  author =        {Goyal, Akshit and Zhang, Yiling and He, Chuan},
  publisher =     {INFORMS Journal on Computing},
  title =         {{Decision Rule Approaches for Pessimistic Bilevel Linear Programs under Moment Ambiguity with Facility Location Applications}},
  year =          {2023},
  doi =           {10.1287/ijoc.2019.2022.0168.cd},
  note =          {Available for download at https://github.com/INFORMSJoC/2022.0168},
}  
```

## Content

This repository includes

1. Sample instance data for the facility location problem.
2. Source files containing Matlab scripts of the cutting-plane method.
3. Files containing sample results for instances of the facility location problem.

<!--1. Files describing the data formats and results.-->

### Data files

The instance settings are described in the [manuscript](https://doi.org/10.1287/ijoc.2022.0168) (including parameter choices and procedures to generate random variables). In the folder [data](data), we provide sample data files of one instance, including [random demand](data/ksi_in-sample.csv) $\xi$, and objective coefficients of the random demand ([leader's coefficient](data/C.csv) $C$ and [follower's coefficient](data/V.csv) $V$).

### Source files
There are three files.

1. [GenResults_InSample.m](src/GenResults_InSample.m): it takes four inputs -- the number of locations $d$, the set of potential locations for building stores $s$, the set of stores operated by Company A $t$, and the maximum number of stores Company B can operate $r$. This function runs the cutting-plane algorithm by calling functions from the two files listed below.
2. [BDmaster_LDRsUB_SDPbyS_lemma.m](src/BDmaster_LDRsUB_SDPbyS_lemma.m): it solves the relaxed problem.
3. [BDsubprob_LDRsUB_SDPbyS_lemma.m](src/BDsubprob_LDRsUB_SDPbyS_lemma.m): it solves the subproblem.

### Results

The results directory contains a sample result file and files with parameter settings obtained by running [GenResults_InSample.m](src/GenResults_InSample.m). 
1. [C_Veq0_gamma1_mat.csv](results/C_Veq0_gamma1_mat.csv): the values of $\gamma_1$ in the moment-based ambiguity set.
2. [C_Veq0_gamma2_mat.csv](results/C_Veq0_gamma2_mat.csv): the values of $\gamma_2$ in the moment-based ambiguity set.
3. [C_Veq0_insamp_obj.csv](results/C_Veq0_insamp_obj.csv): the objective values of the DRBP using the $\gamma$-values in the two files above.



