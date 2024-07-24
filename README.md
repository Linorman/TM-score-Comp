# TM-score-Comp
TM-score-Comp: a quick and accurate algorithm for measuring quality of complex structure predictions of proteins, nucleic acids, and small molecule ligands

Structural comparison between native and predicted structures is the gold-standard way for accessing the quality of 3D structure predictions. As structure prediction advances to include complex structures with different molecule types, developing structure comparison methods to accurately assess predictions for diverse molecules (proteins, nucleic acids, small molecules) in various forms (monomers, oligomers, and polymers) is critical for advancing structural bioinformatics. However, the existing structure comparison methods cannot directly evaluate predicted complexes consisting of proteins, nucleic acids, and small molecule ligands, nor can they provide optimal/suboptimal molecule mappings for homologous polymers within a limited timeframe. We have developed a new and open-source structure comparison method, TM-score-Comp, to quickly and accurately measure the quality of structure predictions of complexes composed of one or more molecule types, such as proteins, DNAs, RNAs, and small molecule ligands. Large-scale benchmarks demonstrated consistent advantages of TM-score-Comp over state-of-the-art methods in the assessment of 3D structure predictions of different molecule types and runs more than 5 times faster on average, especially for those with homologous molecules. Detailed analyses demonstrated that the main advantage of TM-score-Comp lies in the molecule mapping algorithm can always give an optimal/suboptimal molecule mapping results in fast, resulting the improvement of the accuracy and speed of the complex structure comparison process. The on-line web server and source code of TM-score-Comp are made freely available at https://zhanglab.comp.nus.edu.sg/TM-score-Comp/ for academical use.

## Installation:

* Download this repository at https://github.com/jun-csbio/TM-score-Comp.git. Then, uncompress it and run the following command lines on Linux System.

~~~
  $ cd TM-score-Comp-main
  $ chmod 777 ./install.sh
  $ ./install.sh
~~~

* If the package cannot work correctly on your computational cluster, you should install the dependencies via running the following commands:

~~~
  $ cd e2eatp-main
  $ pip install -r requirements.txt
~~~

## Run example
~~~
  $ python predict.py -sf example/results/ -seq_fa example/seq.fa
~~~

## Result

* The prediction result file (e.g., "3J8YK.pred") of each protein (e.g., 3J8YK) in your input fasta file (-seq_fa) could be found in the folder which you input as "-sf".
* There are four columns in each prediction result file. The 1st column is the residue index. The 2nd column is the residue type. The 3rd column is the predicted probablity of the corresponding residue belonging to the class of ATP-binding residues. The 4th column is the prediction result ('B' and 'N' mean the predicted ATP-binding and non-ATP-binding residue, respectively). For example:

~~~
Index    AA    Prob.    State
    0     A    0.001    N
    1     E    0.000    N
    2     S    0.007    N
    3     N    0.001    N
    4     I    0.000    N
    5     K    0.000    N
    6     V    0.000    N
    7     M    0.003    N
    8     C    0.000    N
    9     R    0.984    B
   10     F    0.000    N
   11     R    0.993    B
   12     P    0.990    B
   13     L    0.001    N
   14     N    0.001    N
   15     E    0.000    N
   16     S    0.005    N
   17     E    0.000    N
   18     V    0.000    N
   19     N    0.001    N
~~~

## Predicted Database on Uniprot
* If you have installed this package, you can find that there is a predicted ATP-binding residues database for all 207,892 human proteins in UniProt (up to 2023-07-10).

~~~
  $ cd e2eatp-main/uniprot/
~~~

## Update History:

- Add a new data set     2023-11-26
- First release          2023-07-12

## Tips

* <b>This package is only free for academic use</b>. If you have any question, please email Jun Hu: junh_cs@126.com

## References
