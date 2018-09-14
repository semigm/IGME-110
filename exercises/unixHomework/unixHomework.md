# Unix Prep Homework

Next week, you’ll be publishing web pages to RIT’s web server. This exercise will help you to determine if your RIT web account was properly configured. Make sure to do this exercise before next week, so that if there are problems you have time to correct them!


## Part 1: Logging Into the RIT Web Server

* **Windows**:  Launch the MobaXterm program (installed on all IGM computers, and downloadable from https://mobaxterm.mobatek.net/), and select the SSH icon in the top left corner. Enter banjo.rit.edu as the remote host, and your RIT username (eg abc1234). If you are asked a question about the security key on the server, say yes (this will only happen the first time you log in). Type in your password when prompted.

* **Mac**:  Launch the Terminal application (available on all Mac computers), and at the prompt type in the following (replacing yourUserName with your RIT User ID).
`ssh yourUsername@banjo.rit.edu`


Note: When you type in your password, you will not see any characters on the screen. It will be accepting your input, but you will not see any characters on the screen as you type.)

If you see the something resembling the following text, it means you’ve successfully connected:

```
login: Thu May 18 11:57:55 2017 from [your host name]

RIT information technology resources are for the use of the RIT community only. 
By using RIT information technology resources you acknowledge that you have read 
and comply with RIT's Code of Conduct for Computer and Network Use and RIT's 
Information Security Policy and Standards. Use of RIT information technology 
resources may be monitored and unauthorized use is strictly prohibited.
```

If you get an error message, or have difficulty connecting, ask for help in an IGM lab, or contact the [ITS help desk](https://www.rit.edu/its/help-support/hours-contact) for assistance--you’ll need to be able to log in to your account in order to do the week 5 in-class exercises.

Once you've successfully logged in, continue to Part 2.


## Part 2: Checking Your Configuration

After connecting to the server, type in the command ls (LS in lowercase) to show a list of your home directory contents. At a minimum, you should see php_data and www in the display.

![sample view of ls results](banjo-prompt.png)

If you do not see php_data and www listed when you typed in the ls command, please let me know ASAP--it means RIT did not configure your account properly, and we need to get that fixed that before class next week.

That’s it! You’re done. To close your session, you can type either `logout` or `exit`, and then quit the MobaXterm or Terminal program.