# Connect to Princeton OIT Server

1. You need to get your PUID as a user on the server. Talk to Forrest or Kian Wee.
2. Enable unix access for your PUID [here](https://fed.princeton.edu/cas/login;jsessionid=3F1F014CD7E5D83F65CA9E2495AD1EB5?locale=en&service=https%3a%2f%2feisess200l.Princeton.EDU%2fcgi-bin%2fShell%2fnview.pl).
3. Once enabled, you will be able to log into the server with ssh. One must be in the Princeton campus or vpn to the Princeton network to log into the server.
    ```
    ssh your_puid@andlchaos300l.princeton.edu
    ```
4. To get root access, get a software/hardware token (USD 60/ 132) from [here](https://princeton.service-now.com/service/?id=sc_cat_item&sys_id=a8f092884f569e00f56c0ad14210c791).
5. Once you get your RSA token setup remember your pin when you setup your token. Use the command
    ```
    sudo su - root
    ```

    a. Then enter your pin (the pin you use when setting up your RSA token) plus the passcode on your token. For e.g. if your pin is 123456 and the RSA passcode is 654321, your passcode is 123456654321
