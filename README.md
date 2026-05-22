# sqlinjection
Exploiting SQL Injection vulnerability

# AIM:
To exploit SQL Injection vulnerability using Multidae web application in Metasploitable2

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode


### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

SQL Injection is a sort of infusion assault that makes it conceivable to execute malicious SQL statements. These statements control a database server behind a web application. Assailants can utilize SQL Injection vulnerabilities to sidestep application safety efforts. They can circumvent authentication and authorization of a page or web application and recover the content of the whole SQL database. 

Identify IP address using ifconfig in Metasploitable2

## OUTPUT

<img width="698" height="399" alt="image" src="https://github.com/user-attachments/assets/0070d6f8-cb21-46fe-89cf-6b77b1bf63e6" />

<img width="955" height="611" alt="image" src="https://github.com/user-attachments/assets/dbda43ee-e3ff-4401-b7d4-e9c00ee6ab9c" />



Use the above ip address to access the apache webserver of Metasploitable2 from kali/parrot linux. In Kali Linux use the ip address in a web browser.
##  OUTPUT

<img width="724" height="260" alt="image" src="https://github.com/user-attachments/assets/d31053d6-51dd-45ed-b20d-b60b16ad1611" />



Select Multidae from the menu listed as shown above. The page is displayed as below:
##  OUTPUT

<img width="944" height="1081" alt="image" src="https://github.com/user-attachments/assets/33955a68-22b7-4c92-83a9-e6a1ab6a59c4" />


Click on the menu Login/Register and register for an account
##  OUTPUT

<img width="950" height="1097" alt="image" src="https://github.com/user-attachments/assets/dfc1a404-0508-45a4-86b6-07e60c250aba" />


Click on the link “Please register here”
##  OUTPUT

<img width="956" height="939" alt="image" src="https://github.com/user-attachments/assets/e2e348e4-7af2-4271-9e7f-aed223735441" />


Click on “Create Account” to display the following page:
##  OUTPUT

<img width="655" height="468" alt="image" src="https://github.com/user-attachments/assets/13943530-1764-449f-a6fa-065263d76a66" />


<img width="942" height="1094" alt="image" src="https://github.com/user-attachments/assets/dc4a7567-9805-49aa-8028-5764c15c2b91" />

The login structure we will use in our examples is straightforward. It contains two input fields (username and password), which are both vulnerable. The back-end content creates a query to approve the username and secret key given by the client. Here is an outline of the page rationale:


($query = “SELECT * FROM users WHERE username=’$_POST[username]’ AND password=’$_POST[password]’“;).
 For the username put “ganesh” or “anything” and for the password put (anything’ or ‘1’=’1) or (admin’ or ‘1’=’1) then try to log in, and you’ll be presented with an admin login page.
##  OUTPUT

<img width="940" height="1000" alt="image" src="https://github.com/user-attachments/assets/f1c14553-da7f-4b93-86f8-f43063ac4f25" />



Click “Login”. The logged in page will show as below:
##  OUTPUT

<img width="972" height="975" alt="image" src="https://github.com/user-attachments/assets/7155ebd7-4a48-482b-b1e5-a055a1ee1701" />




If error faced in registration follow the following steps in metasploitable 2:


This issue is caused by a misconfiguration in the config.inc located in the /var/www/mutillidae folder on Metasploitable 2 VM.

Edit config.inc
Edit config.inc file located in /var/www/mutillidae folder on Metasploitable 2 by typing the following commands [one at the time]:
cd /
sudo nano /var/www/mutillidae/config.inc
Type msfadmin when prompted for the root password. 
Once nano opens config.inc file, look for the line $dbname = ‘metasploit’ as shown in Figure  below:
##  OUTPUT

<img width="785" height="503" alt="image" src="https://github.com/user-attachments/assets/e673daba-c708-4110-a347-08ff31dcc884" />



Replace ‘metasploit’ with ‘owasp10’ and make sure the lines end with semicolon ; as shown in Figure
##  OUTPUT

<img width="785" height="503" alt="image" src="https://github.com/user-attachments/assets/afb8c8f2-6937-4179-8c9f-b1b3fc14b1f1" />



Save and exit the config.inc
Save than exit the config.inc file by typing CTRL+X keys on your keyboard and the Y [Enter] when prompted to save the file
Restart the Apache server
To restart Apache, type the following command in the terminal. Alternatively, you can just reboot Metasploitalbe 2 VM.
sudo /etc/init.d/apache2 reload
##  OUTPUT


<img width="788" height="114" alt="image" src="https://github.com/user-attachments/assets/56b1b9e6-47ee-429f-92fd-f401a18c8653" />


# Reset Mutillidae database
Refresh the page then clicking on the Reset DB menu option to reset the Mutillidae database [Figure ]. Click OK when prompted.
##  OUTPUT

<img width="788" height="114" alt="image" src="https://github.com/user-attachments/assets/b4388501-dfd1-43f9-9ee9-71ebdec9a8a6" />




# Test the new configuration
Alright. Now is time to test if we managed to fix the database issue. Go ahead and register a new account on the Mutillidae webpage.

The Mutillidae database error no longer appears 
 
## OUTPUT

<img width="929" height="907" alt="image" src="https://github.com/user-attachments/assets/1eb9661a-2da5-453c-b44d-668f627f6ecf" />


Now after logging out you will see the login page. In the login page give ganesh’ # (myusername). You can see the page now enters into the administrator page as before when giving the password.

## OUTPUT

<img width="959" height="1074" alt="image" src="https://github.com/user-attachments/assets/11f6794e-6929-431e-8861-996822d6cd29" />



Click the login button and you will see it enter into the administrator page.
## OUTPUT

<img width="963" height="1052" alt="image" src="https://github.com/user-attachments/assets/a4f41b66-3331-44fc-93c1-3291bf8b02d3" />


## Union-based SQL injection

UNION-based SQL injection assaults enable the analyzer to extract data from the database effectively. Since the “UNION” operator must be utilized if the two inquiries have precisely the same structure, the attacker must craft a “SELECT” statement like the first inquiry. 
we will be using the “User Info” page from Mutillidae to perform a Union-Based SQL injection attack. Go to “OWASP Top 10/A1 — Injection/SQLi — Extract-Data/User Info” 

After logging out, Now choose the menu as shown below:
##  OUTPUT

<img width="947" height="1103" alt="image" src="https://github.com/user-attachments/assets/59e6f98f-e428-4f3c-a230-bfc49172cef3" />




From this point, all our attack vectors will be performed in the URL section of the page using the Union-Based technique.There are two different ways to discover how many columns are selected by the original query. The first is to infuse an “ORDER BY” statement indicating a column number. Given the column number specified is higher than the number of columns in the “SELECT” statement, an error will be returned.

##  OUTPUT

<img width="941" height="1065" alt="image" src="https://github.com/user-attachments/assets/9060c36a-24ca-4afb-90c3-6f6da7296885" />


Since we do not know the number of columns, we start at 1. To find the exact amount of columns, the number is incremented until an error related to the “ORDER BY” clause is returned. In this example, we incremented it to 6 and received an error message, so it means that the number of columns is lower than 6.

The browser url of this info page need to be modified with the url as below:
##  OUTPUT

<img width="949" height="1062" alt="image" src="https://github.com/user-attachments/assets/6846f7b3-feb1-48b8-95c8-551aedffe72f" />



After adding the order by 6 into the existing url , the following error statement will be obtained:
##  OUTPUT

<img width="945" height="1155" alt="image" src="https://github.com/user-attachments/assets/6060ae1a-10b8-4022-8af2-3fdf80119cdd" />




When we ordered by 5, it worked and displayed some information. It means there are five columns that we can work with. Following screenshot shows that the url modified to have statement added with ordered by 5 replacing 6.

## OUTPUT

<img width="949" height="1163" alt="image" src="https://github.com/user-attachments/assets/71dba1df-d127-4b25-a4de-9675a5ad1718" />



 As it is having 5 columns the query worked fine and it provides the correct result
##  OUTPUT

<img width="949" height="1163" alt="image" src="https://github.com/user-attachments/assets/d24b8c52-cc24-4a73-86a0-735f81b98825" />



Instead of using the "order by" option, let’s use the "union select" option and provide all five columns. Ex: (union select 1,2,3,4,5).
##  OUTPUT

<img width="949" height="1163" alt="image" src="https://github.com/user-attachments/assets/1b681c1e-f8b1-4cfe-9b2c-28b70852fe41" />


As given in the screenshot below columns 2,3,4 are usable in which we can substitute any sql commands to extract necessary information.
##  OUTPUT


<img width="703" height="337" alt="image" src="https://github.com/user-attachments/assets/e25cc755-7ecf-4ef0-9fad-9b33992da6d0" />


Now we will substitute some few commands like database(), user(), version() to obtain the information regarding the database name, username and version of the database.
##  OUTPUT

<img width="958" height="1048" alt="image" src="https://github.com/user-attachments/assets/262a6f1e-4a75-4c38-b5a6-64f4f8ff72ee" />

<img width="954" height="1087" alt="image" src="https://github.com/user-attachments/assets/facee538-743a-429b-b8e0-438b555f22c6" />

<img width="950" height="1076" alt="image" src="https://github.com/user-attachments/assets/4be3c7e8-38f5-484f-a63a-638566008530" />


The url when executed, we obtain the necessary information about the database name owasp10, username as root@localhost and version as 5.0.51a-3ubuntu5.
In MySQL, the table “information_schema.tables” contains all the metadata identified with table items. Below is listed the most useful information on this table.

Replace the query in the url with the following one:
union select 1,table_name,null,null,5 from information_schema.tables where table_schema = ‘owasp10’
##  OUTPUT'

<img width="951" height="1067" alt="image" src="https://github.com/user-attachments/assets/cf2526fc-b332-480d-bd15-281748db6137" />


The url once executed will  retrieve table names from the “owasp 10” database.
##Extracting sensitive data such as passwords 

When the attacker knows table names, he needs to discover what the column names are to extract data.

In MySQL, the table “information_schema.columns” gives data about columns in tables. One of the most useful columns to extract is called “column_name.”

Ex: (union select 1,colunm_name,null,null,5 from information_schema.columns where table_name = ‘accounts’).

Here we are trying to extract column names from the “accounts” table.
##  OUTPUT

<img width="958" height="1040" alt="image" src="https://github.com/user-attachments/assets/a78c2fd4-8885-4bf8-acd9-e64242fae095" />


The column names of the accounts is displayed below for the following url:


Once we discovered all available column names, we can extract information from them by just adding those column names in our query sentence.

Ex: (union select 1,username,password,is_admin,5 from accounts).
##  OUTPUT

<img width="945" height="1068" alt="image" src="https://github.com/user-attachments/assets/e2912f29-b425-4a7e-8e4b-15eab693be72" />



## Reading and writing files on the web-server
We can use the “LOAD_FILE()” operator to peruse the contents of any file contained within the web-server. We will typically check for the “/etc/password” file to see if we get lucky and scoop usernames and passwords to possible use in brute force attacks later.

Ex: (union select null,load_file(‘/etc/passwd’),null,null,null).


##  OUTPUT

<img width="950" height="1111" alt="image" src="https://github.com/user-attachments/assets/afbf86c8-68e1-4c5c-accb-c948981488f6" />


## RESULT:
The SQL Injection vulnerability is successfully exploited using the Multidae web application in Metasploitable2.
