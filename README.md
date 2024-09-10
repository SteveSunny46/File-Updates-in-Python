# IP-based File Access using Python

## Project description
I've developed an algorithm to automate the management of access to restricted content at our organization. This algorithm uses an "allow_list.txt" file to specify which IP addresses are granted access, and a separate list to identify IP addresses that should no longer have this privilege. It ensures that those IP addresses are removed from the "allow_list.txt" file, effectively revoking their access to the content.


## Open the file that contains the allow list
To begin with the algorithm, I initiated by opening the "allow_list.txt" file. Firstly, I assigned the file name as a string to the variable named "import_file." Secondly, I used the “with” statement to open the file. 

![AD_4nXfzogW2zTav_nvH3xn8RP6IzqIjTrcVT9qrLaERpjvkje2pnL0UNzljWhdhtOCS6KSpo8DpEIuTFtoAInpBrvCyT-_jluGeaIJS1Qaw1pB05ZsRS5B70UuN](https://github.com/SteveSunny46/File-Updates-in-Python/assets/171859383/f063b171-7b85-49d8-84af-85de2b008c3f)

In my algorithm, I use the “with” statement and the “.open()” function to read the allow list file. This allows me to access the stored IP addresses. The with statement helps manage the file resource by automatically closing it when I'm done.

I used  “open(import_file, "r") as file”. The .open() function has two parts: the first specifies the file I'm opening, and the second says I'm reading it. I use the “as” keyword to store the file's contents in a variable named "file" while I work with it in the “with” statement.


## Read the file contents

Next, I used the “.read()” function to read the file
![AD_4nXdSr7RkSmRhOLH9UIMbdJwyYJEU_3vRjYKtJaE86Kq07MHNv5EshOwfuqYWRCBSsvh2lUX9Q9UlA7CpWFb6lpox3QhDaxu0Fu_PhtWxQMt8ciGEm0JYmvIY](https://github.com/SteveSunny46/File-Updates-in-Python/assets/171859383/fd61f3bb-6622-47e2-bc6d-a6496fc09c0d)

With the "r" argument in the “.open()” function, I can use the “.read()” method within the “with”  statement. This method converts the file content into a string that I can read. I used it with the "file" variable from the “with” statement and saved the result as "ip_addresses."


## Convert the string into a list

Using the “.string()” function, I can convert the string to a list. I perform this on the ip_addresses.

![AD_4nXfKcUk7NQ4xwlv3zZwH8CS1_DueOK_-pOieJDfXPZustz_7Y4J-RcqAZjH5mP_T256ButorfDFnUyfpNyNt_tvYDhQq0K2SbjkWTGVJJivG5_1mYFUYEy2p](https://github.com/SteveSunny46/File-Updates-in-Python/assets/171859383/b84558a5-9c01-4a82-bce0-53f93af27cb6)

The “.split()” function is used with a string variable. It takes the contents of the string and turns them into a list. The reason for splitting "ip_addresses" into a list is to make it easier to remove IP addresses from the allow list. By default, “.split()” divides the text into list elements using spaces. In this algorithm, I applied “.split()”  to the "ip_addresses" variable, which holds a string of IP addresses separated by spaces. It then converts this string into a list of IP addresses, which I stored back in the "ip_addresses" variable.

## Iterate through the remove list
Using a "for" loop I can iterate through the IP addresses in the “remove_list”.

![AD_4nXeo1dCmGIYobysU-C-hp5wDySOhMC71lRh2NlqoqpjLhE2J79m47bHL4MSAX-7efx8PZpYgRvyKrZjPDc4pn04KW2SNuN9JxjA9-lqTvFBscaI_Sls94Yry](https://github.com/SteveSunny46/File-Updates-in-Python/assets/171859383/3f5fc41a-77e0-487c-85ac-b3c8fb0984bc)


The “for” loop in Python is used to repeat a specific set of actions for each item in a sequence. It starts with the "for" keyword and involves a loop variable (like "element") that takes on each value in the sequence (in this case, "ip_addresses").


## Remove IP addresses that are on the remove list
Inside the for loop, I added a condition to check if the loop variable "element" is present in the "ip_addresses" list. This check is important because trying to remove an element that is not in the "ip_addresses" list would lead to an error.

If "element" is indeed found in "ip_addresses," I used the .remove() method to eliminate it from the list. This way, each IP address from the "remove_list" gets removed from the "ip_addresses" list.

## Update the file with the revised list of IP addresses 
![AD_4nXdM-T-SFe6idGoWHWI-qQxRcTxtat_52-gudyBjmuB4sFA8EncuTrgKTM5DRQM8UWRhY38T248bQ58UbQaJu5HNz1zWasQUJdDsxwE3zpTfI2fp7ERsiH00](https://github.com/SteveSunny46/File-Updates-in-Python/assets/171859383/46893000-5ddf-4f7e-bb1e-4a16554cc48c)

The “.join()” method combines items in a list into a single string with a specified separator. I used it to create a string from the "ip_addresses" list, making each element appear on a new line by using (" ") as the separator.

In a new “with”  statement, I opened the file with the "w" argument to overwrite its content. I used the “.write()” method to replace the file's content with the modified "ip_addresses" list. This ensures that restricted content is no longer accessible to removed IP addresses.
## Summary 

I designed an algorithm to eliminate IP addresses listed in a "remove_list" from the "allow_list.txt" file, which contains approved IP addresses. Here's how it works:

1. I opened the file and converted it into a string to read its contents.

2. Then, I transformed this string into a list, which I stored in the variable "ip_addresses."

3. I proceeded to go through the IP addresses in the "remove_list." For each address, I checked if it existed in the "ip_addresses" list.

4. If it was found, I used the .remove() method to remove it from "ip_addresses."

5. Finally, I used the .join() method to turn "ip_addresses" back into a string. This allowed me to replace the contents of the "allow_list.txt" file with the updated list of IP addresses.
