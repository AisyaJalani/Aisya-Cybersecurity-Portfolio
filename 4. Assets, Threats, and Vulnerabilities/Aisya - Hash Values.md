# Create Hash Values

## Scenario

  In this scenario, you need to investigate whether two files are identical or different.

  This practice is how to 

  * Compute hashes using **sha256sum**
  * Display hashes using the **cat** command
  * Compare hashes using the **cmp** command.

#### 1. Generate hashes for files

  <img width="664" alt="Pasted Graphic 76" src="https://github.com/user-attachments/assets/75ad7074-8c11-4fea-9952-e3b70886ca58" />  

  * The `ls` command is used to list the contents of the directory. Output shows `file1.txt` and `file2.txt`, are listed.

  <img width="714" alt="Pasted Graphic 77" src="https://github.com/user-attachments/assets/4603fa80-f873-4e94-b9ec-c5fb0aebe0dd" />

  * The `cat` command is to display the contents of the `file1.txt` and `file2.txt` file. The output will show identical file content.

  <img width="716" alt="analyat@5590bb2bc8b3-$" src="https://github.com/user-attachments/assets/34f2e17e-a61e-40f0-a22a-c3ff60504284" />

  * The `sha256sum` command will generate two hashes written to separate files of the file1.txt and file2.txt file. The generate hash will determine that the files are actually different.
  
#### 2. Compare hashes

  * I used the `sha256sum` command to generate the hash of the `file1.txt` and `file2.txt` file, and send the output to a new file called `file1hash` and `file2hash`.

<img width="717" alt="Pasted Graphic 84" src="https://github.com/user-attachments/assets/ec5dcf45-8cea-4603-b1b6-5367787fab37" />

*  The `cat` command is used to display the hash values in the file1hash and file2hash files. Remember, the content in file1.txt and file2.txt previously appeared identical, but the hashes written to the file1hash and file2hash files are **completely** different.

<img width="717" alt="Pasted Graphic 85" src="https://github.com/user-attachments/assets/2485273c-4211-4550-bfa7-e528842921da" />

* The `cmp` command used to highlight the differences in the `file1hash` and `file2hash` files. The output shows that the hashes differ at the first character in the first line.

<img width="717" alt="Pasted Graphic 86" src="https://github.com/user-attachments/assets/d7981104-d0e9-4ce8-915d-b4e636fa38e7" />

