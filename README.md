#### ncbi-kit: download genome sequence from NCBI assembly database
<br>

#### 1. dependence

`rsync`, `wget`, `ascp`, `parallel`


#### 2. examples

a list assemblies: `assemblies.txt`

```text
GCF_900128725.1_BCifornacula_v1.0
GCF_002157365.2_ASM215736v2
GCF_003044255.1_ASM304425v1
GCF_009730575.1_ASM973057v1
GCF_016406305.1_ASM1640630v1
GCF_016406325.1_ASM1640632v1
GCF_017068195.1_ASM1706819v1
GCF_019599085.1_ASM1959908v1
GCF_019599125.1_ASM1959912v1
GCF_023159095.1_ASM2315909v1
GCF_023159115.1_ASM2315911v1
GCF_023159135.1_ASM2315913v1
GCF_900636665.1_43781_G01
GCF_006400955.1_ASM640095v1
```

CMD:

```sh
cd examples
../ncbi-kit  manifest assemblies.txt | grep "genomic" | ../ncbi-kit ascp - | parallel -j 20
```