## Natas Level 6

- URL:      http://natas6.natas.labs.overthewire.org

- Open the website
![Webpage](images/level_06_01.png)

- We need to enter a secret message to access the password for the next level
- After clicking on the view source button, we see that there is some php code was somehow included
![Source Code](images/level_06_02.png)

- Navigate to the link in the php code ``` includes/secrets.inc ```
![Source Code](images/level_06_03.png)

- > $secret = "FOEIUWGHFEEUHOFUOIU";
![Sucess](images/level_06_04.png)