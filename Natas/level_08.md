# Natas Level 8 Walkthrough

**URL:** [http://natas8.natas.labs.overthewire.org](http://natas8.natas.labs.overthewire.org)

## Introduction
- Natas Level 8 is a web security challenge.
- The objective is to find the password for the next level, natas9.

## Initial Exploration
1. Open the website using the provided URL.
   ![Webpage](images/level_08_01.png)

2. Investigate the source code for hints and vulnerabilities.
   ![SourceCode](images/level_08_02.png)

## Decoding the Password
3. You'll notice that the PHP source code contains an encoded password.
   - To go from the secret to encoded secret the following steps are performed
     - The secret is encoded to base64
     - The resulting string is reversed
     - The reversed string is converted to hex
   - In order to get the original secret, we need to perform the same steps but in reverse

4. To decode the password, follow these steps:
   - Copy the encoded password.
   - Open a tool like CyberChef or use a similar method of your choice.
   - Perform the following operations in reverse order:
     - Convert the string from hex 
     - Reverse the resuting string to get a base64 string
     - Convert from base64 to obtain athe original secret
   ![CyberChef](images/level_08_03.png)

## Success
5. After decoding the password, you'll obtain the password for natas9.
   ![Success](images/level_08_04.png)

