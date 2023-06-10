<h1>Update a file through a Python algorithm</h1>


<h2>Project Description</h2>
My organization is working to make their system more secure. It is my job to ensure the system is safe, investigate all potential security issues, and update employee computers as needed. The following steps provide examples of how I used SQL with filters to perform security-related tasks.
<br />

<h2>Retrieve after hours failed login attempts</h2>
There was a potential security incident that occurred after business hours (after 18:00). All after hours login attempts that failed need to be investigated.
The following code demonstrates how I created a SQL query to filter for failed login attempts that occurred after business hours.

![image](https://github.com/eleasel/PythonFileUpdate/assets/101367394/d210883c-a1a1-4906-a4c8-7bf3df5613df)

The first part of the screenshot is my query, and the second part is a portion of the output. This query filters for failed login attempts that occurred after 18:00. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an AND operator to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition is login_time > '18:00', which filters for the login attempts that occurred after 18:00. The second condition is success = FALSE, which filters for the failed login attempts. 

<h2>Retrieve login attempts on specific dates</h2>

A suspicious event occurred on 2022-05-09. Any login activity that happened on 2022-05-09 or on the day before needs to be investigated.
The following code demonstrates how I created a SQL query to filter for login attempts that occurred on specific dates.

![image](https://github.com/eleasel/PythonFileUpdate/assets/101367394/de575e1a-1b7d-4d3f-b779-d33fb509d6fc)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred on 2022-05-09 or 2022-05-08. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an OR operator to filter my results to output only login attempts that occurred on either 2022-05-09 or 2022-05-08. The first condition is login_date = '2022-05-09', which filters for logins on 2022-05-09. The second condition is login_date = '2022-05-08', which filters for logins on 2022-05-08.


<h2>Retrieve login attempts outside of Mexico</h2>
After investigating the organization’s data on login attempts, I believe there is an issue with the login attempts that occurred outside of Mexico. These login attempts should be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred outside of Mexico. 

![image](https://github.com/eleasel/PythonFileUpdate/assets/101367394/8e7a59af-2d2f-4cb8-beaa-55a1cfcfce74)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred in countries other than Mexico. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with NOT to filter for countries other than Mexico. I used LIKE with MEX% as the pattern to match because the dataset represents Mexico as MEX and MEXICO. The percentage sign (%) represents any number of unspecified characters when used with LIKE![image](https://github.com/eleasel/PythonFileUpdate/assets/101367394/a0085d95-862f-47b6-a859-dc8e50a517c2)

<h2>Retrieve employees in Marketing</h2>
My team wants to update the computers for certain employees in the Marketing department. To do this, I have to get information on which employee machines to update.
The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Marketing department in the East building.

![image](https://github.com/eleasel/PythonFileUpdate/assets/101367394/152c8222-ca4c-4eb4-845d-3b5d3785ed9d)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Marketing department in the East building. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with AND to filter for employees who work in the Marketing department and in the East building. I used LIKE with East% as the pattern to match because the data in the office column represents the East building with the specific office number. The first condition is the department = 'Marketing' portion, which filters for employees in the Marketing department. The second condition is the office LIKE 'East%' portion, which filters for employees in the East building.

<h2>Retrieve employees in Finance or Sales</h2>

The machines for employees in the Finance and Sales departments also need to be updated. Since a different security update is needed, I have to get information on employees only from these two departments.
The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Finance or Sales departments.

![image](https://github.com/eleasel/PythonFileUpdate/assets/101367394/8e82ed99-da76-4f3f-8c21-e799a629803b)



The .split() function is called by appending it to a string variable. It works by converting the contents of a string to a list. The purpose of splitting ip_addresses into a list is to make it easier to remove IP addresses from the allow list. By default, the .split() function splits the text by whitespace into list elements. In this algorithm, the .split() function takes the data stored in the variable ip_addresses, which is a string of IP addresses that are each separated by a whitespace, and it converts this string into a list of IP addresses. To store this list, I reassigned it back to the variable ip_addresses. 

<h2>Iterate through the remove list</h2>
A key part of my algorithm involves iterating through the IP addresses that are elements in the remove_list. To do this, I incorporated a for loop:

![image](https://github.com/eleasel/PythonFileUpdate/assets/101367394/9a5b25d5-b612-4370-9e68-232a31b9684f)


The for loop in Python repeats code for a specified sequence. The overall purpose of the for loop in a Python algorithm like this is to apply specific code statements to all elements in a sequence. The for keyword starts the for loop. It is followed by the loop variable element and the keyword in. The keyword in indicates to iterate through the sequence ip_addresses and assign each value to the loop variable element. 

<h2>Remove IP addresses that are on the remove list</h2>
My algorithm requires removing any IP address from the allow list, ip_addresses, that is also contained in remove_list. Because all of the elements in remove_list are also in the ip_addresses list, and because the ip_addresses list does not contain duplicates, I was able to incorporate the .remove() method into the body of my for loop in the following way:

![image](https://github.com/eleasel/PythonFileUpdate/assets/101367394/1dfc3f37-6cac-4856-b00d-b60763d74fdd)

 

Because the IP addresses in the remove_list must be deleted from the ip_addresses list, I applied .remove() to ip_addresses. I passed in the loop variable element as the argument so that each IP address that was in the remove_list would be removed from ip_addresses. 

<H2>Update the file with the revised list of IP addresses</H2>
As a final step in my algorithm, I needed to update the allow list file with the revised list of IP addresses. To do so, I first needed to convert the list back into a string. I used the .join() method for this:

![image](https://github.com/eleasel/PythonFileUpdate/assets/101367394/a99296e5-8a34-43f3-8665-4a54d43eb4a1)

The .join() method combines all items in an iterable into a string. The .join() method is applied to a string containing characters that will separate the elements in the iterable once joined into a string. In this algorithm, I used the .join() method to create a string from the list ip_addresses so that I could pass it in as an argument to the .write() method when writing to the file "allow_list.txt". I used a single space (" ") as the separator. 

Then, I used another with statement and the .write() method to update the file:

![image](https://github.com/eleasel/PythonFileUpdate/assets/101367394/0880dd52-0081-45da-9349-bb106126f3d4)

This time, I used a second argument of "w" with the open() function in my with statement. This argument indicates that I want to open a file to write over its contents. When using this argument "w", I can call the .write() function in the body of the with statement. The .write() function writes string data to a specified file and replaces any existing file content. 
In this case I wanted to write the updated allow list as a string to the file "allow_list.txt". This way, the restricted content will no longer be accessible to any IP addresses that were removed from the allow list. To rewrite the file, I appended the .write() function to the file object file that I identified in the with statement. I passed in the ip_addresses variable as the argument to specify that the contents of the file specified in the with statement should be replaced with the data in this variable.

<H2>Summary</H2>
I created an algorithm that removes IP addresses identified in a remove_list variable from the "allow_list.txt" file of approved IP addresses. This algorithm involved opening the file, converting it to a string to be read, and then converting this string to a list stored in the variable ip_addresses. I then iterated through the IP addresses in remove_list and removed each of those IP addresses from the ip_addresses list with the .remove() method. After this, I used the .join() method to convert the ip_addresses back into a string so that I could write over the contents of the "allow_list.txt" file with the revised list of IP addresses.

</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
