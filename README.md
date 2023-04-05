[![INFORMS Journal on Computing Logo](https://INFORMSJoC.github.io/logos/INFORMS_Journal_on_Computing_Header.jpg)](https://pubsonline.informs.org/journal/ijoc)

# Distributionally Robust Bilevel Programming

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
  url =           {https://github.com/INFORMSJoC/2022.0168},
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


## Description

The goal of this software is to demonstrate the effect of cache optimization.

## Building

In Linux, to build the version that multiplies all elements of a vector by a
constant (used to obtain the results in [Figure 1](results/mult-test.png) in the
paper), stepping K elements at a time, execute the following commands.

```
make mult
```

Alternatively, to build the version that sums the elements of a vector (used
to obtain the results [Figure 2](results/sum-test.png) in the paper), stepping K
elements at a time, do the following.

```
make clean
make sum
```

Be sure to make clean before building a different version of the code.

## Results

Figure 1 in the paper shows the results of the multiplication test with different
values of K using `gcc` 7.5 on an Ubuntu Linux box.

![Figure 1](results/mult-test.png)

Figure 2 in the paper shows the results of the sum test with different
values of K using `gcc` 7.5 on an Ubuntu Linux box.

![Figure 1](results/sum-test.png)

## Replicating

To replicate the results in [Figure 1](results/mult-test), do either

```
make mult-test
```
or
```
python test.py mult
```
To replicate the results in [Figure 2](results/sum-test), do either

```
make sum-test
```
or
```
python test.py sum
```

## Ongoing Development

This code is being developed on an on-going basis at the author's
[Github site](https://github.com/tkralphs/JoCTemplate).

## Support

For support in using this software, submit an
[issue](https://github.com/tkralphs/JoCTemplate/issues/new).
