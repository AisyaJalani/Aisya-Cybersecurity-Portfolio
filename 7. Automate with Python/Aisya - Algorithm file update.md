# Algorithm for file updates in Python


## Scenario

You are a security professional working at a health care company. As part of your job, you're required to regularly update a file that identifies the employees who can access restricted content. The contents of the file are based on who is working with personal patient records. Employees are restricted access based on their IP address. There is an allow list for IP addresses permitted to sign into the restricted subnetwork. There's also a remove list that identifies which employees you must remove from this allow list.

The task is to create an algorithm that uses Python code to check whether the allow list contains any IP addresses identified on the remove list. It should remove those IP addresses from the file containing the allow list.

## Description

At my organization, access to restricted content is controlled with an allow list of IP addresses.
The "allow_list.txt" file identifies these IP addresses. A separate remove list identifies IP
addresses that should no longer have access to this content. I created an algorithm to
automate updating the `allow_list.txt` file and remove these IP addresses that should no longer have access.
<br/>

**1. Open the file that contains the allow list**

* First part of the algorithm, I opened the `allow_list.txt` file. I assigned this file name as a string to the `import_file` variable:

<img width="475" alt="print (renove_list)" src="https://github.com/user-attachments/assets/96cb0f62-faff-4c7a-87a0-e2976cdb282a" /> <br/>

<img width="614" alt="AD_4nXeTx8VXu3_f6vVH4u2VTMzN8NEtlYQtdkLbxcNTaloXe89_8QHoUoc9DE3kB879pSeaLrd54wNXDiQXzgRs7L5Betym6nbnI1im7-KG62WcNcxDthO2bRJL" src="https://github.com/user-attachments/assets/eda04107-aab4-43f0-b807-4febfff79e32" /> <br/>

* Then, I used a `with` statement to open the file.
* In the algorithm, the `with open(import_file, "r") as file:` statement is used to read the specified allow list file. This allows access to the stored IP addresses. The `with` statement ensures proper resource management by automatically closing the file upon exit. Here, `open()` `"r"` parameter denotes read mode, and `file` is assigned as a variable to hold the opened file object.

**2. Read the file contents**

<img width="783" alt="AD_4nXdOm-AfmOIEg16mhWCs1FtiCLyoMqFxgPB9o7Czlx_PcEDdZcl0LSiZML-dgFtALJARQ_8pWDOf5mlRUhBHkIq2oweYJ2POdeOXVpv8CLOmJAhM8Dr_PPjw" src="https://github.com/user-attachments/assets/fe013149-828c-4fdc-9be6-590553473fa1" /> <br/>

* To read the file contents, I used the `.read()` method to convert it into the string.
* Using the `.open()` function with mode `"r"` (read), I applied the `.read()` method inside the `with` statement to convert the contents of `allow_list.txt` into a string. This string was assigned to the variable `ip_addresses` for later data processing in the program.

**3. Convert the string into a list**

<img width="617" alt="AD_4nXcSQOnS-8JH4g8q5w-Wm2QEhwyhMAwBVIV1k5tfV5vbRVRRxTQg_zrfQoXDLpWoIs0VjGRg8HYa8TA0K7VTAWbwieKMre8pzFILI2au8QXbckkpc1oyTl3g" src="https://github.com/user-attachments/assets/ac7fd6d6-dc49-45b7-a810-d03b0bba08e2" /> <br/>

* To remove individual IP addresses from the allow list, I used the `.split()` method to convert the `ip_addresses` string into a list to remove individual IP addresses from the allow list.
* The `.split()` function, when appended to a string variable like `ip_addresses`, converts its contents into a list. By default, it splits the string into list elements wherever whitespace is found. This process makes it easier to manipulate, such as removing IP addresses from the `ip_addresses` list. To store this list, I reassigned it back to the variable `ip_addresses`.

**4. Iterate through the remove list**

<img width="527" alt="AD_4nXfwNVaSi0jbfD3SuRAbP26uUbBGQuSzK4tjBqdp740lDGFcZDH7T-Giu7_KvUkHJQf9gJoiOxoEg4-mX4b_Xtm--nLSBgisM9dd3V6qYAiVo_l7yXyvbjYC" src="https://github.com/user-attachments/assets/d4ee0aff-9c6a-491c-8967-94b65fce3a1b" />
<br/>

* A `for` loop, initiated by the `for` keyword, iterates through a sequence (e.g., `ip_addresses`), applying specific code statements to each `element` within it. This effectively processes all items in the sequence.

**5. Remove IP addresses that are on the remove list**

<img width="570" alt="AD_4nXfG_ay6fiFbNfGGFf2vHgK85hojTFECqcw92gavKxzJf0nmcfsLjI8HE-ojgmVOKZHyuldK4TudzbuPsYLIrsE3oj5YDOs_J7xjvqxWC64dgSqzX5mG20J8" src="https://github.com/user-attachments/assets/6accd403-40fb-4e38-8f55-f4fbd3a90b78" /> <br/>

* To remove IP addresses from `ip_addresses` that are also present in `remove_list`, I implemented a `for` loop. Inside, a conditional check ensures the `element` exists in `ip_addresses` before applying `.remove(element)` to prevent errors, effectively removed unwanted IPs.

**6. Update the file with the revised list of IP addresses**

<img width="793" alt="AD_4nXcHFJyycMeovPN8ubo1vO0rxksiUhTYm9wYiFCMq9dQDs49X7xz7PjXqjclsCpPV3505CAt8npsVYruVvo0O1X9cct76b3aelRBtxo66g97sGylrzmowhnW" src="https://github.com/user-attachments/assets/7079ff20-de51-484b-ad80-5ea8c9f6ccf8" /> <br/>

* Final step in the algorithm, I need to update the allow list file with the revised list of IP addresses. To do so, first convert the list back into a string. I used the `.join()` method for this.
* The `.join()` method converts an iterable (e.g., the `ip_addresses` list) into a single string. It's applied to a separator string, in this case `("\n")`, which places each joined element on a new line. This resulting string is then passed to the `.write()` method for file output.

<img width="603" alt="AD_4nXepPoJ38lJP7RgWyls5oYLmAy6Ha1iVHAMe0U9gwNAR_7LacWGCQqPQMX0nXt-2oFsHXYfj39vnwQhA91pwk598DDmnIdNA9UfOpMcZ2p3Ar1v7zKVBYLJw" src="https://github.com/user-attachments/assets/8ba0002f-05df-4b67-97fb-c296fd578cfd" /> <br/>

* Next, I used `with` statement and the `.write()` method to update the file.
* The `with open(import_file, "w") as file:` statement opens the specified file for writing, effectively overwriting its existing content. The `.write()` function is then called on the `file` object, passing the `ip_addresses` string as an argument. This rewrites "allow_list.txt" with the updated content, ensuring restricted access for removed IP addresses.

## Summary

To summarize, I wrote an algorithm that removes IPs from a `remove_list` out of the `allow_list.txt` file. It reads the file into a string, splits it into a list `ip_addresses`, then iterates through `remove_list`, removing any matching IPs from `ip_addresses`. The updated list is joined back into a string and written back to the file.


