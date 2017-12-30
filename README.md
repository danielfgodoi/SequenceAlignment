# README #

### What is this repository for? ###

This code is used to align and compare two FASTA sequences, in global, local and semiglobal algorithms studied in Bioinformatics.

Note: It was requested to have only one file, so all the classes and methods are in SequenceAlignment.cpp.

### Input ###

Compile the source using the G++ command
```
#!command
g++ -o SequenceAlignment SequenceAlignment.cpp -Wall -pedantic -ansi
```

Note: Your FASTA files need to have 70 characters in each line, for example: 
```
#!fasta
>AB010874 Homo sapiens gene da proteina ribossomal L41
TTCGCCTTTCTCTCGGCCTTAGCGCCATTTTTTTGGGTGAGTGTTTTTTGGTTCCTGCGTTGGGATTCCG
TGTACAATCCATAGACATCTGACCTCGGCACTTAGCATCATCACAGCAAACTAACTGTAGCCTTTCTCTC
TTTCCCTGTATAAACCTCTGCGCCATGAGAGCCAAGGTGAGCGGTTCCTGGTAGTAAGCTTGGGAGGTAG
GAGTTGGCGAGTAGTAGCGGGGAGACGAAGGCAAGTCCGCCATACCTCCTGAACTACTGGGTTTCAAGGG
TGCCCAAGAGCTGGTGGGAGAGAGAAGGTAGTTTGTGAGAGAGCTAGCGGTTAAGTGCTATGGGTAGAGA
```

Now you're ready to execute the script. Here we have some configuration needed.

Format: <executable file> [-g,-l,-s] -u <1st sequence> -v <2nd sequence> -i <w(a,a)> -d <w(a,b)> -e <w(-,b) or w(a,-)>

[-g,-l,-s] is the algorithm you want to use, global, local or semiglobal.

-u and -v is to define the 1st and 2nd sequence, respectively.

-i, -d and -e is to define the score for each comparison; -i is for equal, -d for different and -e is for spaces.
```
#!command
./SequenceAlignment -g -u u.fasta -v v.fasta -i 2 -d 1 -e -2

If you are using Windows, consider removing the "./"
```

### Output ###

The output format is the sequences aligned with the signs "|" for equal, "!" for different and " " for spaces and the similarity in the end as "similaridade".
Here we have an example:

```
#!command
seq1 GGCAGATTCCCCCTAGACCCGCCCGCACCA
      !|| !|!|!|!| | !|!|!|||| !|||
seq2 -CCA-CTGCACTC-A-CCGCACCCG-GCCA
seq1 TGGTCAGGCATGCCCCTCCTCATCGCTGGG
      !!|!!!|  ||   !|!!|!!|!| !|!!
seq2 -ATTTTTG--TG---TTTTTAGTAG-AGAC
seq1 CACAGCCCAGAGGGTATAAACAGTGCTGGA
     !|!|!!|||!|!!|  |!||||!!!!!|!!
seq2 TAAATACCATATAG--TGAACACCTAAGAC
seq1 GGCTGGCGGGGCAGGCCAGCTGAGTCCTGA
     ||!!|||!!!|!| !||||!!!!!|!|!||
seq2 GGGGGGCCTTGGA-TCCAGGGCGATTCAGA
seq1 GCAGCAGCCCAGCGCAGCCACCGAGACACC
     | !|| !||!!!||!|||!!!|| |  | !
seq2 G-GGC-CCCGGTCGGAGCTGTCG-G--A-G
seq1 ATGAGAGCCCTCACACTCCTCGCCCTATTG
     || !||||!|!|!|!!||| ||!!!|!|!!
seq2 AT-TGAGCGCGCGCGGTCC-CGGGATCTCC
seq1 GCCCTGGCCGCACTTTGCATCGCTGGCCAG
     |!|!!|| | | | |!|!!!|!|!|||!!!
seq2 GACGAGG-C-C-C-TGGACCCCCGGGCGGC
seq1 GCAGGTGAGTGCCCCCACCTCCCCTCAGGC
     |!||!||!| |  |!|!!|!|||| |!||!
seq2 GAAGCTGCG-G--CGCGGCGCCCC-CTGGA
seq1 CGCATTGCAGTGGGGGCTGAGAGGAGGAAG
     !||  !|| |!|!!!!||| |!!| |!!!|
seq2 GGC--CGC-GGGACCCCTG-GCCG-GTCCG
seq1 CACCATGGCCCACCTCTTCTCACCCCTTTG
     | !||!|!!|!!|!!!!||!||!!!| !!|
seq2 C-GCAGGCGCAGCGGGGTCGCAGGGC-GCG
seq1 GCTGGCAGTCCCTTTGCAGTCTAACCACCT
     || ||  ||!||!!!|| | !!!|!!!|!!
seq2 GC-GG--GTTCCAGCGC-G-GGGATGGCGC
seq1 TGTTGCAGGCTCAATCCATTTGCCCCAGCT
     || |!|!!|!!!!| ||!!!!||!!!!||!
seq2 TG-TCCGCGGAGGA-CCGGGCGCTGGTGCG
seq1 CTGCCCTTGCAGAGGGAGAGGAGGGAAGAG
     | |||| ||!!|| !|| ||!!|||  !||
seq2 C-GCCC-TGTGGA-AGA-AGCTGGG--CAG
seq1 CAAGCTGCCCGAGACGCAGGGGAAGGAGGA
     ||| | | !|| | ||  !!!!!|!|| !|
seq2 CAA-C-G-TCG-G-CG--TCTACACGA-CA
seq1 TGAGGGCCCTGGGGATGAGCTGGGGTGAAC
      || ||||||  ||| !||!||!||!!!!|
seq2 -GA-GGCCCT--GGA-AAGGTGCGGCAGGC
seq1 CAGGCTCCCTTTCCTTTGCAGGTGCGAAGC
     !!|||!|||   ||   ||     |    |
seq2 TGGGCGCCC---CC---GC-----C----C
seq1 CCAGCGGTGCAGAGTCCAGCAAAGGTGCAG
     ||||!||!!|!!!!|||  |!|||!!!|!!
seq2 CCAGGGGCCCTCCCTCC--CCAAGCCCCCC
seq1 GTATGAGGATGGACCTGATGGGTTCCTGGA
     |!|!|!|!!| !||| !|  !||||||
seq2 GGACGCGCCT-CACC-CA--CGTTCCT---
seq1 CCCTCCCCTCTCACCCTGGTCCCTCAGTCT
       || |!| !!!| |||  | |||  |!||
seq2 --CT-CGC-AGGA-CCT--T-CCT--GGCT
seq1 CATTCCCCCACTCCTGCCACCTCCTGTCTG
       || ||||!|!!|!!!!||||!|| |||
seq2 --TT-CCCCGCCACGAAGACCTACT-TCT-
seq1 GCCATCAGGAAGGCCAGCCTGCTCCCCACC
      ||  || !!!||  | ||||  !!|| ||
seq2 -CC--CA-CCTGG--A-CCTG--AGCC-CC
seq1 TGATCCTCCCAAACCCAGAGCCACCTGATG
     !|!|||||!| ||!!||||||| |!!|  |
seq2 GGCTCCTCAC-AAGTCAGAGCC-CACG--G
seq1 CCTGCCCCTCTGCTCCACAGCCTTTGTGTC
     ||!|!!!!| !|| !!|| | |!!||!| |
seq2 CCAGAAGGT-GGC-GGAC-G-CGCTGAG-C
seq1 CAAGCAGGAGGGCAGCGAGGTAGTGAAGAG
     |!!|| !| !|| |||| !!| | | | !|
seq2 CTCGC-CG-TGG-AGCG-CCT-G-G-A-CG
seq1 ACCCAGGCGCTACCTGTATCAATGGCTGGG
     |||!|  |!|!| | |   |!!||!|!|!|
seq2 ACCTA--CCCCA-C-G---CGCTGTCCGCG
seq1 GTGAGAGAAAAGGCAGAGCTGGGCCAAGGC
     !|||| !!|!!!||| !|| |!||||!!!!
seq2 CTGAG-CCACCTGCA-CGC-GTGCCAGCTG
seq1 CCTGCCTCTCCGGGATGGTCTGTGGGGGAG
     |!!|!!!!!||||!!!|!| |!!!||!|||
seq2 CGAGTGGACCCGGCCAGCT-TCCAGGTGAG
seq1 CTGCAGCAGGGAGTGGCCTCTCTGGGTTGT
     |!||!||!|!| !|||!| |!||  ||!!!
seq2 CGGCTGCCGTG-CTGGGC-CCCT--GTCCC
seq1 GGTGGGGGTACAGGCAGCCTGCCCTGGTGG
     !|!|!|||!!|!|||!|!!|| !!| |!||
seq2 CGGGAGGGCCCCGGCGGGGTG-GGT-GCGG
seq1 GCACCCTGGAGCCCCATGTGTAGGGAGAGG
     |!!!|!| |!|!!!|!!|||!|||!!!!!|
seq2 GGGGCGT-GCGGGGCGGGTGCAGGCGAGTG
seq1 AGGGATGGGCATTTTGCACGGGGGCTGATG
     ||!!!||!|| !!|!|| | |!!|||!!||
seq2 AGCCTTGAGC-GCTCGC-C-GCAGCTCCTG
seq1 CCACCACGTCGGGTGTCTCAGAGCCCCAGT
      !!|||| | |!!|| ||!!!|!|||!!|
seq2 -GGCCAC-T-GCCTG-CTGGTAACCCTCG-
seq1 CCCCTACCCGGATCCCCTGGAGCCCAGGAG
      |||!!|!| !| |||| |||| !|!!!||
seq2 -CCCGGCAC-TA-CCCC-GGAG-ACTTCAG
seq1 GGAGGTGTGTGAGCTCAATCCGGACTGTGA
     !!!!|!| !||!!!!| !| | | ||| ||
seq2 CCCCGCG-CTGCAGGC-GT-C-G-CTG-GA
seq1 CGAGTTGGCTGACCACATCGGCTTTCAGGA
     |!|||| !||||!| || | |!|!||  !!
seq2 CAAGTT-CCTGAGC-CA-C-GTTATC--TC
seq1 GGCCTATCGGCGCTTCTACGGCCCGGTCTA
     || |  !|!| |!|||!!!|!!|| | ||!
seq2 GG-C--GCTG-GTTTCCGAGTACC-G-CTG
seq1 GGGTGTCGCTCTGCTGGCCTGGCCGGCAAC
     !!!|||!|!| !|!|||||  | |||!|!|
seq2 AACTGTGGGT-GGGTGGCC--G-CGGGATC
seq1 CCCAGTTCTGCTCCTCTCCAGGCACCCTTC
     ||||| !| | !||| |     | |||!|!
seq2 CCCAG-GC-G-ACCT-T-----C-CCCGTG
seq1 TTTCCTCTTCCCCTTGCCCTTGCCCTGACC
     |||  !!!|   !!!| |||!!|||  | !
seq2 TTT--GAGT---AAAG-CCTCTCCC--A-G
seq1 TCCCAGCCCTATGGATGTGGGGTCCCCATC
     !!!|||||!|!|!|!!|||!!!||!|!| !
seq2 GAGCAGCCTTCTTGCCGTGCTCTCTCGA-G
seq1 ATCCCAGCTGCTCCCAAATAAACTCCAGAA
     !|  |||  |!!!|!|!|!!|| !!| |
seq2 GT--CAG--GACGCGAGAGGAA-GGC-G--
seq1 G
     !
seq2 C
similaridade: 1203
```

### Who do I talk to? ###

Repo owner/admin: Daniel de Faria Godoi (<danielfgodoi@gmail.com>)