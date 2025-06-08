# Algorithm for file updates in Python


## Scenario

You are a security professional working at a health care company. As part of your job, you're required to regularly update a file that identifies the employees who can access restricted content. The contents of the file are based on who is working with personal patient records. Employees are restricted access based on their IP address. There is an allow list for IP addresses permitted to sign into the restricted subnetwork. There's also a remove list that identifies which employees you must remove from this allow list.

The task is to create an algorithm that uses Python code to check whether the allow list contains any IP addresses identified on the remove list. It should remove those IP addresses from the file containing the allow list.

## Description

At my organization, access to restricted content is controlled with an allow list of IP addresses.
The "allow_list.txt" file identifies these IP addresses. A separate remove list identifies IP
addresses that should no longer have access to this content. I created an algorithm to
automate updating the `allow_list.txt` file and remove these IP addresses that should no longer have access. The content of remove list are as follows:

* `192.168.97.225`
* `192.168.158.170`
* `192.168.201.40`
* `192.168.58.57`
<br/>

### 1. Open the file that contains the allow list

* First part of the algorithm, I opened the `allow_list.txt` file. I assigned this file name as a string to the `import_file` variable:

```
# Assign `import_file` to the name of the file 
import_file = "allow_list.txt"

# Build `with` statement to read in the initial contents of the file
with open(import_file, "r") as file: 
    ip_addresses = file.read()
```

* Then, I used a `with` statement to open the file.
* In the algorithm, the `with open(import_file, "r") as file:` statement is used to read the specified allow list file. This allows access to the stored IP addresses. The `with` statement ensures proper resource management by automatically closing the file upon exit. Here, `open()` `"r"` parameter denotes read mode, and `file` is assigned as a variable to hold the opened file object.
<br/>

### 2. Read the file contents

```
with open(import_file, "r") as file: 

# Use `.read()` to read the imported file and store it in a variable named `ip_addresses`
    ip_addresses = file.read()
```

The output:

```
ip_address
192.168.25.60
192.168.205.12
192.168.97.225
192.168.6.9
192.168.52.90
192.168.158.170
192.168.90.124
192.168.186.176
192.168.133.188
192.168.203.198
192.168.201.40
192.168.218.219
192.168.52.37
192.168.156.224
192.168.60.153
192.168.58.57
192.168.69.116
```

* To read the file contents, I used the `.read()` method to convert it into the string.
* Using the `.open()` function with mode `"r"` (read), I applied the `.read()` method inside the `with` statement to convert the contents of `allow_list.txt` into a string. This string was assigned to the variable `ip_addresses` for later data processing in the program.
<br/>

### 3. Convert the string into a list

```
# Use `.split()` to convert `ip_addresses` from a string to a list
    ip_addresses = ip_addresses.split()
```

The output:

```
['ip_address', '192.168.25.60', '192.168.205.12', '192.168.97.225', '192.168.6.9', '192.168.52.90', '192.168.158.170', '192.168.90.124', '192.168.186.176', '192.168.133.188', '192.168.203.198', '192.168.201.40', '192.168.218.219', '192.168.52.37', '192.168.156.224', '192.168.60.153', '192.168.58.57', '192.168.69.116']
```

* To remove individual IP addresses from the allow list, I used the `.split()` method to convert the `ip_addresses` string into a list to remove individual IP addresses from the allow list.
* The `.split()` function, when appended to a string variable like `ip_addresses`, converts its contents into a list. By default, it splits the string into list elements wherever whitespace is found. This process makes it easier to manipulate, such as removing IP addresses from the `ip_addresses` list. To store this list, I reassigned it back to the variable `ip_addresses`.
<br/>

### 4. Iterate through the remove list

```
# Build iterative statement
# Name loop variable `element`
# Loop through `ip_addresses`

for element in ip_addresses:
```
<br/>

* A `for` loop, initiated by the `for` keyword, iterates through a sequence (e.g., `ip_addresses`), applying specific code statements to each `element` within it. This effectively processes all items in the sequence.
<br/>

### 5. Remove IP addresses that are on the remove list

```
remove_list = ['192.168.97.225', '192.168.158.170', '192.168.201.40', '192.168.58.57']

for element in remove_list:
  # Build conditional statement
  # If current element is in `ip_addresses`,

  if element in ip_addresses:

    # then current element should be removed from `ip_addresses`

    ip_addresses.remove(element)

  print(ip_addresses)
```
<br/>

The output:

```
['ip_address', '192.168.25.60', '192.168.205.12', '192.168.6.9', '192.168.52.90', '192.168.90.124', '192.168.186.176', '192.168.133.188', '192.168.203.198', '192.168.218.219', '192.168.52.37', '192.168.156.224', '192.168.60.153', '192.168.69.116']
```

* To remove IP addresses from `ip_addresses` that are also present in `remove_list`, I implemented a `for` loop. Inside, a conditional check ensures the `element` exists in `ip_addresses` before applying `.remove(element)` to prevent errors, effectively removed unwanted IPs.
<br/>

### 6. Update the file with the revised list of IP addresses

```
# Convert `ip_addresses` back to a string so that it can be written into the text file
  ip_addresses = "\n".join(ip_addresses)

# Build `with` statement to rewrite the original file
  with open(import_file, "w") as file:

  # Rewrite the file, replacing its contents with `ip_addresses`
  file.write(ip_addresses)

# Build `with` statement to read in the updated file
with open(import_file, “r”) as file:

# Read in the updated file and store the contents in `revised_list`
revised_list = file.read()

# Display the contents of `revised_list`
print(revised_list)
```

The output:

```
ip_address 192.168.25.60 192.168.205.12 192.168.6.9 192.168.52.90 192.168.90.124 192.168.186.176 192.168.133.188 192.168.203.198 192.168.218.219 192.168.52.37 192.168.156.224 192.168.60.153 192.168.69.116
```

* Final step in the algorithm, I need to update the allow list file with the revised list of IP addresses. To do so, first convert the list back into a string. I used the `.join()` method for this.
* The `.join()` method converts an iterable the `ip_addresses` into a single string. It's applied to a separator string, in this case `("\n")`, which places each joined element on a new line. This resulting string is then passed to the `.write()` method for file output.

* Next, I used `with` statement and the `.write()` method to update the file.
* The `with open(import_file, "w") as file:` statement opens the specified file for writing, effectively overwriting its existing content. The `.write()` function is then called on the `file` object, passing the `ip_addresses` string as an argument. This rewrites "allow_list.txt" with the updated content, ensuring restricted access for removed IP addresses.
* The updated revised list of the IP address is then called on the `revised_list`.

### Summary

To summarize, I wrote an algorithm that removes IPs from a `remove_list` out of the `allow_list.txt` file. It reads the file into a string, splits it into a list `ip_addresses`, then iterates through `remove_list`, removing any matching IPs from `ip_addresses`. The updated list is joined back into a string and written back to the file.


