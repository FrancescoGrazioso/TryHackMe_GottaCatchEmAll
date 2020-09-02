# Title: Gotta Catch'Em All!

## Description

This room is based on the original Pokemon series. Can you obtain all the Pokemon in this room?


## Question 1

Run Nmap to search open ports

```
nmap -sC -sV -Pn {Machine-IP}
```


After running a Nmap scan, we'll see that there is an ssh & HTTP port open. We will utilize both of these ports for this room.

Open the IP in your browser of choice, click 'open page source' or the equivalent in your browser.

Scrolling to the bottom shows a weird combination of username and password.

```
ssh username@{Machine-IP}
```

After logging into ssh with the provided credentials, traverse to the user's directory.

You should see a compressed folder that needs to be unzipped? Let's unzip it!

```
unzip <file_name.zip>
```

This will have our first pokemon's text file!

Wait, it still requires a hexadecimal decoder to find the answer. After doing so, you'll have your first answer!

Hexadecimal Decoder: https://cryptii.com/pipes/hex-decoder


## Question 2

First things first, let's see if our webpage from earlier has any pages.

Run the following command:

```
find / -name '*type.txt' 2> /dev/null
```

You'll find a bunch of file location we can visit.

Check the first one, the water type, it is encoded , but looks a lot weirder. That's because it's a Caesar Cipher!

After decoding, you'll have your answer!

Caesar Cipher Decoder: https://cryptii.com/pipes/caesar-cipher


## Question 3

After locating the first two Pokemon, you'll move over to the '/etc/' directory, and there will be a weird directory located there titled 'Why_am_i_here?'

After changing into the correct directory, you'll see the file we need for our third question!

This one needs to be decoded using base64.

Base64: https://www.base64decode.org/


## Question 4 - LAST ONE!

Let's see if we can find any login credentials for a root user to gain access to our last root flag!

Definitely a weird directory in '/Videos/' on the Pokemon user's system.

**Absolute path: 'Gotta/Catch/Them/ALL!'**

Hmm, this looks like a fake C++ file, maybe it has something in it?

```
cat Could_this_be_what_Im_looking_for?.cplusplus
```

There are the login credentials for a user. But does it give root access?

It does!

Time to become **Ash Ketchum** and gain root access and the final flag.

After changing into the home directory of the root user, we'll see a file title **roots-pokemon.txt**.

There it is! The final flag!

The best thing about this flag? No cipher or coded message!

# Congratulations!
