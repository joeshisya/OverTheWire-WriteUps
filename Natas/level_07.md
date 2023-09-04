## Natas Level 7

- URL:      http://natas7.natas.labs.overthewire.org

- Open the website
![Webpage](images/level_07_01.png)

- Clicking on the home and about page leads us to the links
    - > http://natas7.natas.labs.overthewire.org/index.php?page=home
    - > http://natas7.natas.labs.overthewire.org/index.php?page=about 

- We get a hint in the source code
![Source Code](images/level_07_02.png)

- Replace the page parameter with the file above
- > http://natas7.natas.labs.overthewire.org/index.php?page=/etc/natas_webpass/natas8

![Success](images/level_07_03.png)
