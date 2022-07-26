## 13.  Can you write a very short script (possibly one single commandline) to extract from the same file the species names?

```
cut -d ' ' -f 2-4 identifiers.txt | cut -d : -f 2 | sed 's/^ *//g' | cut -d ' ' -f 1,2 

```

## 14.

``` 
cut -d ' ' -f 2-4 identifiers.txt | cut -d : -f 2 | sed 's/^ *//g' | cut -d ' ' -f 1,2 | sort |uniq -c | sort -n 

```

16. 

``` 
touch $(seq -f "trial%g.data" 1 20)

```
