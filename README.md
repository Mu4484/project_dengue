# Shell practice to test your understanding of command line 
This project involves analysis of multiple FASTA files containing dengue virus sequence ,the operations done include ;counting lines,extracting headers,merging files,and basic formatting.

## project files and directories
-dengue.zip - file containing zipped FASTA files.
-unzipped_dengue - file containing unzipped FASTA files. 
-dengue_headers - file with extracted headers. 
-dengue_merged fasta - file containing all sequences combined.
-viruses.txt - file containing  viruses names extracted from headers.
-dengue_seq.txt - file containing sequences only.
-dengue_seq2.txt - file containing sequences in small letters.
-dengueseq1.fasta- this files upto denguseq5 contain the original sequences of the viruses. 


### Steps performed
1. Count files in the zipped file `dengue.zip`
	Command:
	unzip dengue.zip 

2. Count the number of lines in each file 
  	Command:
	wc -l dengueseq*.fasta
	Result: 42,115,94,113,157
3. Count the number of lines in all the files combined 
	Command:
	wc -l dengueseq*.fasta
	Result: 521
4. merge the files into one file and name it `dengue_merged.fasta`
	Command:
	cat dengueseq*.fasta > dengue_merged.fasta
5. count the number of headers in the new file `dengue_merged.fasta`
	command:
	grep '^>' dengue_merged.fasta
6. count the number of sequences the new file has 
	grep -c '^>' dengue_merged.fasta
7. Extract the headers and put them in a new file called `dengue_headers.txt`
	command:
	grep '^>' dengue_merged.fasta > dengue_headers.txt
8. Extract the name of the viruses 
	command:
	awk '{print $2}' dengue_headers.txt > viruses.txt
9. Extract unique identifiers
	command:
	awk '{print $1}' dengue_headers.txt > unique_identifiers
10. Extract sequences into dengue_seq.txt
	command:
	grep -v '^>' dengue_merged.fasta > dengue_seq.txt
11. Replace the sequences to lower case 
	command:
	sed 's/[A-Z]\l&/g' dengue_seq.txt > dengue_seq2.txt
12. which organism has the highest number of bases
	command:
	wc -m dengueseq*.fasta 

## Conclusion
I succesfully analyzed and processed multiple FASTA files containing dengue virus sequence .  









