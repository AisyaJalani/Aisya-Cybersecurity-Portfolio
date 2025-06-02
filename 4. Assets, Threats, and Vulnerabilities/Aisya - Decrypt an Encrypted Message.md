# Decrypt an Encrypted Message

## Scenario

In this scenario, all of the files in your home directory have been encrypted. You’ll need to use Linux commands to break the Caesar cipher and decrypt the files so that you can read the hidden messages they contain.

In this process you will be using basic Linux Bash shell commands to:

  * List hidden files
  * Decrypt a Caesar cipher
  * Decrypt an encrypted file
  

  > Note: The lab starts with you logged in as user analyst, with your home directory, /home/analyst, as the current working directory.

#### 1. Read the contents of a file

The lab starts in your home directory, `/home/analyst`, as the current working directory.
  

<img width="719" alt="A11 of your data has been encrypted  To recover your data, you will need to so" src="https://github.com/user-attachments/assets/945cd520-04a0-4377-ae56-c85043a9ca2b" />


  * The `ls` command is used to list the filed in the current directory. It will output content of the files in the directory `Q1.encrypted` and `README.txt`, and a subdirectory, `caesar`.
  * The `cat` command is to to list the contents of the `README.txt` file which contains message that the caesar subdirectory contains a hidden file.


#### 2. Find a hidden file

<img width="716" alt="Pasted Graphic 63" src="https://github.com/user-attachments/assets/b8841bf7-8cac-42f3-b467-a020d82cf734" />


  * The `cd` command is used to change to the `caesar` subdirectory.
  * The `ls -a` command is used to list all files, including hidden files. Hidden files in Linux can be identified by their name starting with a period (.).

<img width="716" alt="Pasted Graphic 64" src="https://github.com/user-attachments/assets/129754ea-9513-400b-b9f1-9bd294388c25" />

  * Use the `cat` command to list the contents of the `.leftShift3` file.
  * The message in the `.leftShift3` file is scrambled. This is because the data has been encrypted using a Caesar cipher. This cipher can be solved by shifting each alphabet character to the left or right by a fixed number of spaces.

<img width="718" alt="Pasted Graphic 65" src="https://github.com/user-attachments/assets/d88394c1-c308-42bc-a30c-59ff89e59f60" />

  * To decrypt the file, the command `tr "d-za-cD-ZA-C"` `"a-zA-Z"` translates all the lowercase and uppercase letters in the alphabet back to their original position. The first character set, indicated by `"d-za-cD-ZA-C"`, is translated to the second character set, which is `"a-zA-Z"`.


#### 3. Decrypt a file

<img width="717" alt="Pasted Graphic 68" src="https://github.com/user-attachments/assets/edd4ad80-f970-4856-a110-b6da1040f134" />

  * The `openssl` command reverses the encryption of the file with a secure symmetric cipher, as indicated by `AES-256-CBC`. The `-pbkdf2` option is used to add extra security to the key, and `-a` indicates the desired encoding for the output. The `-d` indicates decrypting, while `-in` specifies the input file and `-out` specifies the output file. The `-k` specifies the password, which in this example is `ettubrute`.
  * The new file `Q1.recovered` in the directory listing is the decrypted file and contains a message.

<img width="718" alt="then you" src="https://github.com/user-attachments/assets/c9060e39-5ed8-4e82-9246-ff19e4a86321" />

  * The `cat` command is to list the contents of the `Q1.recovered` file.

