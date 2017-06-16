# Linux_Server_Configuration
for Udacity Fullstack Web Development Project

This project is my Item-Catalog project, Virtual Vending Machine, loaded onto a 
Ubuntu 16.04 Linux Apache2 server through Amazon Web Service's Lightsail. The project
is meant to mimic a vending machine with various items available to read (or create, 
edit and delete after login with either Google or Facebook).

1. The static IP address is 34.195.231.101 with ssh access on port 2200
2. The url to the website is http://virtualvendingmachine.xyz
3. I used Python 2.7.12 for the programming language, Postgresql for the database, Sqlalchemy for ORM,
   and a Flask framework. These are the packages I installed (some globally and some with a
   virtual environment):

  a. python-pip<br>
  b. virtualenv<br>
  c. virtualenvwrapper (didn't use)<br>
  d. postgresql python-psycopg2<br>
  e. python-sqlalchemy<br>
  f. werkzeug==0.8.3<br>
  g. flask==0.9<br>
  h. Flask-Login==0.1.3<br>
  i. oauth2client<br>
  j. requests<br>
  k. httplib2<br>
  l. git<br>
  m. libapache2-mod-wsgi<br>
  
  I made the following configuration changes to the Apache2 server:
  
  a. changed the ssh port from 22 to 2200<br>
  b. configured the firewall to only accept incoming on ports: 80, 123, 2200 and enabled<br>
  c. created USER: grader WITH PASSWORD: 'grader'<br>
  d. gave user: grader sudo access<br>
  e. created RSA ssh key pair for user: grader. Loaded public key onto server.<br>
  f. configured time zone to UTC<br>
  g. create database USER(ROLE): catalog WITH PASSWORD: 'planet8'. permission to 
  	  create database only.<br>
  h. checked that no remote connections were allowed to database which is
     installation default<br>
  i. configured application handler mod_wsgi with a WSGIScriptAlias(made vvmapp.wsgi file)<br>
     and a WSGIDaemonProcess to use a virtual environment.<br>
  j. set ServerName and DocumentRoot<br>
  k. disabled Root Login<br>
  
  4. As far as third-party resources, I predominantly relied upon the Udacity Fullstack forums for help
     on several occasions.  I also went to Stack Overflow a good deal as well as a few READTHEDOCS.
     I didn't keep a complete record of which worked and which didn't (the large majority didn't). If this is
     imperative I shall attempt to retrace my steps and document all sources I can identify. I did
     use one very-cropped version of a circuit board graphic in the front end by Szasz Andreea which was offered as
     free wallpaper http://www.desktopwallpaper4.me/abstract/circuit-board-775/. I enquired about a policy 
     for using the graphic for this project, but to date I have received no response. I left it in for aesthetic,
     but it's not essential. I would comply with the author's policy if I had it.
  
