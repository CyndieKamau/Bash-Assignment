##### Question 1
How many processes are currently running on your system? Use ps and wc, the first line of output of ps is not a process!


`$ps wc`

-Output

```
PID TTY      STAT   TIME COMMAND
   1492 tty2     Ssl+   0:00 gdm-x-session
   1494 tty2     Sl+    0:24 Xorg
   1510 tty2     Sl+    0:00 gnome-session-b
   5337 pts/0    Ss     0:00 bash
   6161 pts/0    R+     0:00 ps

```

##### Question 2
Write a script that upon invocation shows the time and date, lists all logged-in users, and gives the system uptime. 
The script then saves this information to a logfile.

`$nano logintime.sh`

```
# This script upon invocation;
# Shows current time and date
# Lists all logged-in users
# Gives system uptime
# Saves this info to a logfile


#Current time and date
currentDateTime=`date +"%Y-%m-%d %T"`

#All logged in users
usersLogin=`who`

#System uptime
systemUptime=`uptime`


echo Current Date and Time is: ${currentDateTime}
echo All logged in users: ${usersLogin}
echo System Uptime: ${systemUptime}

```

`$bash logintime.sh`

-Output

```
Current Date and Time is: 2022-07-26 11:58:24
All logged in users: bionfo-lab-cmp1 :0 2022-07-26 10:12 (:0)
System Uptime: 11:58:24 up 1:49, 1 user, load average: 0.17, 0.33, 0.27


```

##### Question 3
Which command would you use in order to create an empty file in the current directory, let's say empty.txt?

`$touch empty.txt`

##### Question 4
You are in /home/icipe/  suppose this directory is empty. How do you create in only one command the whole path /home/icipe/Work/mini-project/RNA-Seq/?

`$mkdir -p Work/mini-project/RNA-Seq`

##### Question 5
Suppose your current working directory contains a file named seqs.txt. How do you rename this file into sequences.fasta? 
Does this have any effect on the content of the file, and if yes, what does it do?

`mv seqs.txt sequences.fasta`

There was no change in the file contents.

##### Question 6
How can you create in a single command a file containing the contents "Hello, world!" and named universal_greeting.txt?

`$echo "Hello, world!" > universal_greeting.txt`


##### Question 7
What about creating the same file but with filename "universal greeting.txt" (the filename contains a space)?

`$echo "Hello, world!" > universal\ greeting.txt`

##### Question 8
How can you use the commandline (on whichever machine you are now, that is connected to the internet) to download directly the 
file you can see on https://github.com/Fnyasimi/my-first-repo/blob/main/directory1/test.fa ? Be careful, you need to get the raw text file itself, 
not the full HTML page presenting it.

- Add '?raw=true' to https://github.com/Fnyasimi/my-first-repo/blob/main/directory1/test.fa

`$wget https://github.com/Fnyasimi/my-first-repo/blob/main/directory1/test.fa?raw=true`

`$ less test.fa`

-Output

```
>NM_001361694.1 Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant 9, mRNA
AGGGTTTCTCTGTGTAGCCCTGGCTGTCCTGGAACTCACTCTGTAGACCAGGCTGGCCTTGAACTCAGAAATCTGCCGGC
CTCTGCCTCCCAAGTGCTGGGATTAAAGGTGTGTGCCACCACAGCTCAGGGTTCTTTTTTATCATTAAAATAATTTATTA
CTTTTTAGTTCATGTACATTGGTGTTTCATCTGTGTGTGTCTGTATGAAGGCTTTGGATCCCCTGGAGTTACAGACAGTT
ATTAGCTGCCATGTGGGTGCTGGGAATTGAACCCAGATCCTCTGGAAGAGCAGCCAGTGCTCTTAACTGCTGAGCTATTT
CTCTCGCCCTGGCAGCTACTTTTCTATAGATTATTCTAATTATTTTATACAGATGAACTACAGGCTGGGGATGGGGAGAT
GGCTCACCAGGTGAGAGCCTTTGCCATGCAATGCCCAGAACCCAGGCTGGAAGGGAAGACCTGACCTCTACAGTCAGGCT
GCAGCACCCCTGCCCCATCATGCACATACACACATAAATAAAATAAAACCCAAATGGACTCATACAGTATTTGCCTTTGT
GACTAGCTTATTTTATTGAGCAATTTCACCCATAGCATTTCAAATAGAACAGCTTCAAGTGTACAGCAAAATTAAATAGA
TGGTACAAGGGTTTCCTAAATGTCTCCTGCCCTTGATATATTGCTTACCCCTCTCTTAAATGTTTCACTTCCTAAATAAT
ACCTATGTGAGGTAATGCATATTTAATTGGCTAGATTTTATCATTTATGATGTGTATATAATTTTCAAATAGCATGCTGT
ATATGATAAATAGTTTTATCTCTCTATTTGAAATACAAATTAAACTTTACAAAGACTTCACAGCGTCTCCTGTTTATTGC
AGGGGATATGTTCACTGGACTTCAGCAGACACCTAAGACTGGATAGTAGTAACCTAAGCCACAGTCTAGTCGCTCACTGT
GGCCATAACATTTTAGCTACTTCCCTCCACCTTCATGTAGCTCCTGTGCATGTTTTCGTTTATACCTTAATATTTCACTT
TTAGGAGGCATTGATAGAAGTGAAACTACATCTGATTCCAAATGCTACTTGTTCATTGTTGATACATAAGAAAGCATTTA
TTTATTTATGTATCTACCACATCCTACTTGTTGTTCAATCCAGGAGTCTTTGGTTGATCACCTTTATATGTAGACAGTCA
TGCCATGCAAAAACAGTTGTGTTTTCCTTCTCAGAGGCCCCTCTCCTGCTTTATCTTCCTCTTTGCTCCGCCCTCTCTCT
CTTGCCCTCCCTTACCACTGTTGCCTCCTTTCCTTTCCTTTTTTCCTTTTCCTTTTTCTTGTGGTTTTCCGAGACAGGGT
TTCTCCGTATAACCCTGACTGTCCTGGAACTCTCTGCCTCCCGAGTGCTGGGATTAAAGGCGTGCACCACCACCGCCCGG
GTGTCTCCTTTTCTTTTATTGTTCTTTTCTTTGTTCTTTTACTACATAAACTGAGTTCCAGTATAATGTTGACAATAGAA
GACATCCTTTTCTTGCTCCTGATTTTAATGGGAAAGGTCGAATGGTATGTGGTTCATGTAGACCACATTTTGTTTCCCTC
TCACCCATTGATGGACACTTGGGTAGCTTCCATTTTTGGCTGTTGTGAATAATGCTGCTATGAACATGGGTGTGCACAGA
GCTCTCTGAGACGCTGCTTTCAGTCCTTCTGGCAGTAGATCTTCATGGAGGAGCACGGAGTGACCCAAACTGAACACATG
GCTACCATAGAAGCCCATGCAGTGGCCCAGCAAGTCCAGCAGGTCCATGTAGCCACGTACACTGAGCACAGTATGCTAAG
...............
```

##### Question 9
How can you count the number of lines in this text file (test.fa)? How do you count the number of sequences?

- Count no of lines in text file

`$ wc -l test.fa `

- Output

`10,281`

- Count no of sequences

`grep -v ">" test.fa | wc -l`

- Output

`10,181`

##### Question 10. 
Extract only the identifier lines from this file, and write them into a file called "identifiers.txt".

`$grep "^>" test.fa >identifiers.txt`

`less identifiers.txt`

-Output

```
>NM_001361694.1 Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant 9, mRNA
>NM_001361695.1 Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant 10, mRNA
>NM_001164226.1 Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant 1, mRNA
>NM_010938.4 Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant 6, mRNA
>AK082580.1 Mus musculus 0 day neonate cerebellum cDNA, RIKEN full-length enriched library, clone:C230066G05 product:nuclear respiratory factor 1, full insert sequence
>XM_021165121.1 PREDICTED: Mus caroli nuclear respiratory factor 1 (Nrf1), transcript variant X5, mRNA
>XM_021165122.1 PREDICTED: Mus caroli nuclear respiratory factor 1 (Nrf1), transcript variant X6, mRNA
>AK029034.1 Mus musculus 10 days neonate skin cDNA, RIKEN full-length enriched library, clone:4732483G17 product:nuclear respiratory factor 1, full insert sequence
>AK014494.1 Mus musculus 14 days embryo liver cDNA, RIKEN full-length enriched library, clone:4432414E03 product:nuclear respiratory factor 1, full insert sequence
>NM_001361693.1 Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant 8, mRNA
>NM_001361692.1 Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant 7, mRNA
>XM_011241048.1 PREDICTED: Mus musculus nuclear respiratory factor 1 (Nrf1), transcript variant X8, mRNA
.......

```



##### Question 11. 
How can you process the file you got from question 8 to replace all its uppercase "A" letters into lowercase "a" letters, leaving the rest untouched?

`$grep "A" test.fa | tr [A] [a]`
 
 - Output
 
 ```
 CaGCTCTGGCaGaaCaCGCCCCTGCGCCaCaGGaGGTTaaTTCaGaaCTGCCaCCTCTCaCCaTCGaTGGGaTTCCaGTC
TCTGTGGaCaaaaTGaCCCaGGCTCaGCTTCGGGCaTTTaTCCCaGaGaTGCTCaaGTaTTCCaCaGGTCGaGGGaaaCC
aGGCTGGGGGaaaGaaaGCTGCaaGCCTaTCTGGTGGCCaGaaGaCaTCCCaTGGGCTaaTGTCCGCaGTGaTGTCCGCa
CaGaaGaGCaaaaaCaaaGGGTTTCaTGGaCCCaGGCaTTaCGGaCCaTaGTTaaaaaTTGTTaTaaGCaaCaTGGGCGG
GaGGaTCTTTTaTaTGCTTTTGaaGaTCaGCaaaCaCaaaCTCaGGCCaCCaCCaCaCaCaGTaTaGCTCaTCTCGTaCC
aTCaCaGaCCGTaGTaCaGaCCTTCaGCaaCCCTGaTGGCaCCGTGTCGCTCaTCCaGGTTGGTaCaGGGGCaaCaGTaG
CCaCaTTGGCTGaTGCTTCaGaaCTGCCaaCCaCaGTCaCTGTTGCCCaaGTGaaTTaCTCTGCTGTGGCTGaTGGaGaG
GTGGaaCaaaaTTGGGCCaCGTTaCaGGGCGGTGaaaTGaCCaTCCaGaCGaCGCaaGCaTCaGaGGCCaCCCaGGCGGT
aGCaTCaCTGGCaGaaGCCGCaGTGGCaGCTTCTCaGGaGaTGCaaCaGGGaGCCaCTGTCaCCaTGGCCCTCaaCaGTG
aaGCTGCCGCCCaTGCTGTCGCCaCTCTGGCTGaaGCCaCCTTaCaaGGTGGGGGaCaGaTaGTCCTGTCTGGGGaaaCC
GCaGCaGCCGTCGGaGCaCTTaCTGGaGTCCaaGaTGCTaaTGGCCTGGTCCaGaTTCCTGTGaGCaTGTaCCaGaCTGT
GGTaaCCaGCCTCGCCCaGGGCaaCGGGCCGGTGCaGGTGGCCaTGGCCCCaGTGaCCaCCaGGaTaTCGGaCaGCGCaG
TCaCCaTGGaTGGCCaGGCTGTGGaGGTGGTGaCCTTGGaaCaGTaGCGTGGaGCTCTaTCaTGGCaGCGTTTTTTaGTC
TaCTTCaGaaTTTTTTaCaTGTTTGCaGaGGTGCaaTCaaaTGGaaTTaaGTCTCTCGaCTTGGaaaGaaaGTTTTGGTa
......

```



##### Question 12. 
In one command, ask for the display of all identifier lines from the same file test.fa without wrapping the lines, i.e. by having all lines displayed on your screen effectively start with the character '>'.
 
 `$less -S identifiers.txt`
 
 - Output

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



##### Question 13.  
Can you write a very short script (possibly one single commandline) to extract from the same file the species names?


`$cut -d ' ' -f 2-4 identifiers.txt | cut -d : -f 2 | sed 's/^ *//g' | cut -d ' ' -f 1,2` 

- Output

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
....

````



##### Question 14. 
Once this is done, how do you count the species names with their order of multiplicity (i.e. how many sequences belong to Mus musculus, how many to Homo sapiens, etc)?


`$cut -d ' ' -f 2-4 identifiers.txt | cut -d : -f 2 | sed 's/^ *//g' | cut -d ' ' -f 1,2 | sort |uniq -c | sort -n` 

-Output

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

##### Question 15
Write a loop in Bash producing all the integers from 1 to 30, one per line?

`$seq 1 30`

-Output

```
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
```


##### Question 16. 
Create at once 20 files called "trial1" to "trial20" and *then* rename them all by appending the suffix ".data". Of course, don't issue 20 commands, but just one.

`$touch trial{1..20} ; for f in trial* ; do mv $f $f.data ; done`

-Output

```

trial10.dat  trial12.dat  trial14.dat  trial16.dat  trial18.dat  trial1.dat   trial2.dat  trial4.dat  trial6.dat  trial8.dat
trial11.dat  trial13.dat  trial15.dat  trial17.dat  trial19.dat  trial20.dat  trial3.dat  trial5.dat  trial7.dat  trial9.dat

```

##### Question 17
Try this with the command "expr 1 / 0", whose purpose is to calculate the integer result of 1 divided by 0. What happens? Why?

`expr 1 / 0`

- Output

`expr: division by zero`

-A positive or negative number when divided by zero is a fraction with the zero as denominator.

##### Question 18
How can you separately redirect the standard output and the standard error streams into two separate files?

`$ nano script.sh`

```
#This script is used to show a standard output (stdout) and standard error (stderr) stream

# stdout stream
echo "This is a stdout stream"

#This command will output a stderr stream
cat bad-filename.txt

```

`$ bash script.sh`

- Output

```
This is a stdout stream
cat: bad-filename.txt: No such file or directory

```

- Here we will redirect the stdout and stderr streams to different files.

`bash script.sh 1> stdout.txt 2> stderr.txt`

`cat stdout.txt`

- Output

`This is a stdout stream`

`cat stderr.txt`

- Output

`cat: bad-filename.txt: No such file or directory`

##### Question 19
Write a Bash script asking "What's your name?", then waiting for you (the user) to enter you name and press Enter, 
following what the program displays some text according to the following pattern:
"Good morning/day/evening, your_name!
It's now current_time on this lovely day of current_day." and it exits.

`nano user-input.sh`

```
#This script upon invocation;
#Asks the user to input their name

#Depending on the time, greets them appropriately;'Good morning/afternoon/evening'

#Shows them the current time and date

echo "What's your name?"

#`read` command converts a user's input to a variable

read name

#This command is used to show only the current hour

h=`date +%H`

#Command greets user appropriately depending on the current hour(variable h)

if [ $h -lt 12 ]; then

  echo Good morning $name
  
elif [ $h -lt 18 ]; then

  echo Good afternoon $name
  
else

  echo Good evening $name
  
fi

#
current_time=`date +"%T"`

current_date=`date +"%Y-%m-%d"`

echo It is now ${current_time} on this lovely day of ${current_date}.

```

`$ bash user-input.sh`

`What is your name?`

The user then inputs their name. Depending on the time, it will greet either 'good morning/afternoon/evening'

-Output

```
What's your name?
Cyndie
Good afternoon Cyndie
It is now 13:53:41 on this lovely day of 2022-07-26.

```

##### Question 20
Suppose your current working directory is /home/icipe/Linux/Exercises/. What is the command that will enable to move to /home/icipe/Fun_stuff/?

`$ cd ../../`

`mkdir Fun_stuff`

`cd Linux/Exercises`

`cd ../../Fun_stuff`

`pwd`

-Output

`/home/icipe/Fun_stuff`
