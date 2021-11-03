# Linux Command Cheatsheet
### File Zip/Unzip
Unzipping gz File 
```
gzip -d file.gz
```
Unzipping gz File and keep original file 
```
gzip -dk file.gz
```
Open a `.gz` file with `gunzip`
```
gunzip file.gz
```

### CSV File Information
Get Row and column number of a file
```
awk -F',' ' { print NF }' emoji620vec-1.csv | uniq -c
# Output
731691 102
```
Replace One Char with another
```
sed -i "s/\t/,/g" input_file # inplace
sed "s/\t/,/g" input_file.csv > output_file.csv # new file
sed "s/'//g" input_file.csv > output_file.csv # new file
```
Insert a line begining of a file
```
sed -i '1s/^/insert this\n/' file_name
```
Get rows that contains only x (here x=13) number of columns
```
awk -F'\t' 'NF==13 {print}' infile  > newfile
```
Remove first line of a file
```
sed -i '1d' file.txt
sed -i '1s/^/1584755 621\n/' file_name
```
Split a file
```
split -l 500 source.txt newfile # by line numbers
split -b 40k source.txt newFile # by file size

```
Test
```
awk -F',' ' { print NF }' emoji620vec-1.csv | uniq -c
```
