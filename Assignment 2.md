




##### 10. Extract only the identifier lines from this file, and write them into a file called "identifiers.txt".
```
grep "^>" test.fa >identifiers.txt

```





##### 11. How can you process the file you got from question 8 to replace all its uppercase "A" letters into lowercase "a" letters, leaving the rest untouched?





##### 12. In one command, ask for the display of all identifier lines from the same file test.fa without wrapping the lines, i.e. by having all lines displayed on your screen effectively start with the character '>'.
 
 ``` 
 less -S identifiers.txt
 
 ```

```
>XM_011723889.1 PREDICTED: Macaca nemestrina nuclear respiratory factor 1 (NRF1), transcript variant X12, mRNA
>XM_011939585.1 PREDICTED: Colobus angolensis palliatus nuclear respiratory factor 1 (NRF1), transcript variant X2, mRNA
>XM_015134911.1 PREDICTED: Macaca mulatta nuclear respiratory factor 1 (NRF1), transcript variant X3, mRNA
>XM_011723890.1 PREDICTED: Macaca nemestrina nuclear respiratory factor 1 (NRF1), transcript variant X13, mRNA
>XM_011995878.1 PREDICTED: Mandrillus leucophaeus nuclear respiratory factor 1 (NRF1), transcript variant X2, mRNA
>XM_015134912.1 PREDICTED: Macaca mulatta nuclear respiratory factor 1 (NRF1), transcript variant X4, mRNA
>XM_003803318.3 PREDICTED: Otolemur garnettii nuclear respiratory factor 1 (NRF1), mRNA
>NM_001164227.1 Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant 2, mRNA
>AK037697.1 Mus musculus 16 days neonate thymus cDNA, RIKEN full-length enriched library, clone:A130038J21 product:SIMILAR TO NUCLEAR RESPIRATORY FACTOR 1 homolog [Mus musculu>
>XM_016958154.2 PREDICTED: Pan troglodytes nuclear respiratory factor 1 (NRF1), transcript variant X7, mRNA
>XM_021936263.1 PREDICTED: Papio anubis nuclear respiratory factor 1 (NRF1), transcript variant X10, mRNA
>XM_003813488.3 PREDICTED: Pan paniscus nuclear respiratory factor 1 (NRF1), transcript variant X4, mRNA
>XM_003896587.4 PREDICTED: Papio anubis nuclear respiratory factor 1 (NRF1), transcript variant X11, mRNA
>XM_003951129.3 PREDICTED: Pan troglodytes nuclear respiratory factor 1 (NRF1), transcript variant X9, mRNA
>XM_001155756.5 PREDICTED: Pan troglodytes nuclear respiratory factor 1 (NRF1), transcript variant X8, mRNA
>XM_017957164.2 PREDICTED: Papio anubis nuclear respiratory factor 1 (NRF1), transcript variant X12, mRNA
>XM_021673680.1 PREDICTED: Aotus nancymaae nuclear respiratory factor 1 (NRF1), transcript variant X1, mRNA
>XM_010378768.1 PREDICTED: Rhinopithecus roxellana nuclear respiratory factor 1 (NRF1), transcript variant X1, mRNA
>XM_010378771.1 PREDICTED: Rhinopithecus roxellana nuclear respiratory factor 1 (NRF1), transcript variant X4, mRNA
>XM_017321441.1 PREDICTED: Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant X6, mRNA
>XM_021673683.1 PREDICTED: Aotus nancymaae nuclear respiratory factor 1 (NRF1), transcript variant X2, mRNA
>XM_010378770.1 PREDICTED: Rhinopithecus roxellana nuclear respiratory factor 1 (NRF1), transcript variant X3, mRNA
>XM_010378769.1 PREDICTED: Rhinopithecus roxellana nuclear respiratory factor 1 (NRF1), transcript variant X2, mRNA
>NM_001164230.1 Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant 5, mRNA
>XM_024250195.1 PREDICTED: Pongo abelii nuclear respiratory factor 1 (NRF1), transcript variant X1, mRNA
>XM_006505006.3 PREDICTED: Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant X5, mRNA
>XM_010378772.1 PREDICTED: Rhinopithecus roxellana nuclear respiratory factor 1 (NRF1), transcript variant X5, mRNA
>XM_024250197.1 PREDICTED: Pongo abelii nuclear respiratory factor 1 (NRF1), transcript variant X3, mRNA
>XM_024250196.1 PREDICTED: Pongo abelii nuclear respiratory factor 1 (NRF1), transcript variant X2, mRNA
>L22454.1 Homo sapiens nuclear respiratory factor-1 (NRF-1) mRNA, complete cds
>AK134483.1 Mus musculus 11 days embryo head cDNA, RIKEN full-length enriched library, clone:6230412K09 product:nuclear respiratory factor 1, full insert sequence
>U02683.1 Homo sapiens alpha palindromic binding protein mRNA, complete cds

```



##### 13.  Can you write a very short script (possibly one single commandline) to extract from the same file the species names?

```
cut -d ' ' -f 2-4 identifiers.txt | cut -d : -f 2 | sed 's/^ *//g' | cut -d ' ' -f 1,2 

```

```
Mus musculus
Mus musculus
Mus musculus
Mus musculus
Mus musculus
Mus caroli
Mus caroli
Mus musculus
Mus musculus
Mus musculus
Mus musculus
Mus musculus
Mus musculus
Mus pahari
Rattus norvegicus
Peromyscus maniculatus
Mus musculus
Mus musculus
Mus musculus
Mus musculus
Mus pahari
Cricetulus griseus
Mesocricetus auratus
Rattus norvegicus
Nannospalax galili
Nannospalax galili
Peromyscus maniculatus
Mus musculus
Cricetulus griseus
Castor canadensis
Marmota marmota
Microtus ochrogaster
Ictidomys tridecemlineatus
Heterocephalus glaber
Heterocephalus glaber
Heterocephalus glaber
Mus musculus
Mus musculus
Ictidomys tridecemlineatus
Chinchilla lanigera
Chinchilla lanigera

````



##### 14. nce this is done, how do you count the species names with their order of multiplicity (i.e. how many sequences belong to Mus musculus, how many to Homo sapiens, etc)?

``` 
cut -d ' ' -f 2-4 identifiers.txt | cut -d : -f 2 | sed 's/^ *//g' | cut -d ' ' -f 1,2 | sort |uniq -c | sort -n 

```
```
1 Castor canadensis
      1 Cebus capucinus
      1 Ceratotherium simum
      1 Colobus angolensis
      1 Equus asinus
      1 Equus caballus
      1 Equus przewalskii
      1 Galeopterus variegatus
      1 Mandrillus leucophaeus
      1 Mesocricetus auratus
      1 Microcebus murinus
      1 Microtus ochrogaster
      1 Otolemur garnettii
      1 Pan paniscus
      2 Aotus nancymaae
      2 Chlorocebus sabaeus
      2 Cricetulus griseus
      2 Macaca fascicularis
      2 Marmota marmota
      2 Mus caroli
      2 Mus pahari
      2 Nannospalax galili
      2 Peromyscus maniculatus
      2 Rattus norvegicus
      3 Heterocephalus glaber
      3 Homo sapiens
      3 Macaca nemestrina
      3 Pan troglodytes
      3 Papio anubis
      3 Pongo abelii
      4 Ictidomys tridecemlineatus
      4 Macaca mulatta
      5 Chinchilla lanigera
      5 Rhinopithecus roxellana
      6 Cercocebus atys
     24 Mus musculus
```

##### 16. Create at once 20 files called "trial1" to "trial20" and *then* rename them all by appending the suffix ".data". Of course, don't issue 20 commands, but just one.

``` 
touch $(seq -f "trial%g.data" 1 20)

```

