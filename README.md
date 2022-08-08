# BiP-DBP
Standalone packages and datasets of BiP-DBP

# Pre-requisite:
- Python(3), java(1.8),numpy(1.20 or higher), pytorch(1.5 or higher)
- SANN software (https://github.com/newtonjoo/sann)
- NCBI nr90 database (ftp://ftp.ncbi.nlm.nih.gov/blast/db/FASTA/)
- PSIPRED(psiped321) software(https://i12r-studfilesrv.informatik.tu-muenchen.de/wiki/index.php/Psipred)
- HHblits tool(http://toolkit.genzentrum.lmu.de/hhblits/)
- Linux system (suggested CentOS 7)
# Installation:
- First, download compressed packages in (https://github.com/wwzll123/TPSO/tree/main/Standalone_Program)
- second, download the FileUnion.jar in (https://github.com/wwzll123/TPSO/tree/main/FileSplit)
- third, union these compressed packages using FileUnion.jar by typing the following command
```
# [packages folder path] should be the path that contains files of TPSO_DBP.tar.gz_0 ~ TPSO_DBP.tar.gz_20.
$ java -jar FileUnion.jar [packages folder path] ./TPSO_DBP.tar.gz
```
- fourth, uncompress the generated file of TPSO_DBP.tar.gz.
- fifth, provide executable permissions for file of './jar/tools/blast-2.2.26/blastpgp'.


# Set config
The files of “Config.properties” and "config.ini" should be set as follows:

* Config.properties
 ```
DBS_PRED_MODEL=./jar/model/dbs/dbs.mod
BLAST_BIN_DIR=./jar/tools/blast-2.2.26
BLASTPGP_EXE_PATH=./jar/tools/blast-2.2.26/blastpgp

#Need change
SANN_RUNNER_PATH=Absolute_Path_SANN_Installtion/SANN/sann/bin/sann.sh
BLASTPGP_DB_PATH=Absolute_Path_nr_Installtion/nr
```
* config.ini
 ``` 
[PATH]

#Need change
BiP_HOME=Absolute_Path_BiP-DBP_Installtion/BiP_DBP
PSIPRED_HOME=Absolute_Path_PSIPRED_Installtion/psipred321
HHBLITS_EXE=Absolute_Path_HHsuite_Installtion/hhsuite-3.0-beta.3-Linux/bin/hhblits
HHBLITS_DB=Absolute_Path_uniclust_Installtion/uniclust30_2018_08_hhsuite/uniclust30_2018_08/uniclust30_2018_08
 ```
 
 # Running
- You should make sure your query protein sequences in the file of './workFolder/seqs.fa'.
- than, enter the following command lines on Linux System.
 ``` 
 $ python main.py
``` 
- the predicted result will be generated in file of './workFolder/querys.jun_res'.
- The first column is the prediction result, 0 means non-DBP, 1 means DBP. The second column is the probability of being predicted as a positive sample. The third column is the probability of being predicted as a negative sample.
  
# Note
- Files of .dbs_prob, .sa and .opssm are generated in './jar/example'.
- The .ss and .hhm file generated by PSIPRED is generated in './workFolder'.
- If you already have these files, just put them into the corresponding folder, then the feature generator will not run. This will greatly reduce the prediction time.
- If you have any question, please send email to z804908905@163.com.
- All the best to you!

# Reference
[1] Jun Hu, Wen-Wu Zeng, Ning-Xin Jia, Shi-Jian Dong, Dong-Jun Yu, and Gui-Jun Zhang. Improving DNA-Binding Protein Prediction using Two-Stage Light Neural Network based on Bidirectional Long Short-Term Memory. Submitted.
 
