FLY BY NIGHT README FILE
TABLE OF CONTENTS
=========================================
1. JDK verstion and plataform
2. Execution Instructions
3. Location of data file
4. Design choices document
5. File listing

1. JDK Version and Plataform
The JDK version used for this project was 1.4.0. For detailed information on the exact version,
refer to the following output from the "java -version" command:
  java version "1.4.0"
  Java (TM) 2 Rutitime Environment, Standard Edition ( build 1.4.0-b92)
  Java HotSpot(TM) Client VM ( build 1.4.0-b92, mixed mode )

This project was developed and tested in a computer to following architecture:
Authentic AMD, AMD Duron(tm) processor, 112,0MB RAM using Windows Milennum. 
The following information details the exact operating system information: 
Microsoft Windows Me 4.90.3000 

2. Execution instructions

Initially,
Create a new directory(folder) where will be extracted the contents of scjda-sp2867618 to.
Copy the attached file into the directory you created and extract the content of the attached one.
Make sure you have a java environment in which run the files.

All commands must be executed on a command prompt from the folder you extracted the contents
of scjda-sp2867618 to (the one containing the FBNMain.jar, FBNServer.jar and db.db files, aka, 
installation directory). Please, also, see the user documentation
located in the folders userdocs\gui and userdocs\server for  additional details.

There are two ways to run the Fly By Night application: non-network mode and networked mode.

2.1 Non-network mode 
    In non-newtowork mode, you only need to start one JVM to run the client application. 
    To do this, go to the installation directory and run the following command from 
    a command window ( make sure that db.db is in the installation directory ).
                                   java -jar FBNMain.jar

    After doing that, it will be displayed a dialog box containing the following message of alert:
    "Problem to read config parameter. Loading default values". This occurs because all 
    configuration parameters will be persistent between run of the program being stored
    in a file called suncertify.properties which will be located in the installation directory.
    Click on OK button. Next time, that dialog box won't be displayed to you.

    Following, will be displayed a dialog box asking you about the execution mode. 
    Choose the option non-network mode, and then click on non-network button. After this,
    it will be displayed other dialog box, asking you about the configuration parameter
    for execute the application in the non-network mode. Input into the location of 
    data file (It is displayed a default file will be $Install_Dir/db.db, where $Install_Dir
    is the installation directory). Click on Start button.
  

2.2 Networked mode
    In networked mode, you need to start the server application in one JVM, and the
    client within another JVM.

    To start the server, go to the installation directory ( make sure that db.db is
    in the installation directory ) and run the following command:
                                  java -jar FBNServer.jar

    If you want to specify the  data file and port number used by server, use the following command:
                java -jar [-Dport=<number_port>] [-Ddbfile=<path_and_file>] FBNServer.jar
    1. Example for the port 1099 
       java -jar -Dport=1099 FBNServer.jar
    2. Example for the port 3021 and the datafile db.db located in directory c:\test
       java -jar -Dport-3021 -Ddbfile=c:\test\db.db FBNServer.jar

    NOTE: If the the port 1099 or 3021 is already used on your computer, 
          please select a free port ( 1024-65535) 

    To start the client, run the following command:
                                java -jar FBNMain.jar

    After doing that, it will be displayed a dialog box containing the following message of alert:
    "Problem to read config parameter. Loading default values". This occurrs because all 
    configuration parameters will be persistent between run of the program being stored
    in a file called suncertify.properties which will be located in the installation directory.
    Click on OK button. Next time, that dialog box won be displayed to you.

    Following, it will be displayed a dialog box, asking you about the execution mode.
    Choose the option network mode, and click on network button. After that, will be
    displayed other dialog box, asking you about the configuration parameter for running
    the application in the network mode. Make sure that the corresponding paramaters provided
    in the dialog box containing information about the DNS name and port number are respectively
    used by server-side application. Click on start button.

  
3. Location of data file
   The data file db.db used for this assignment is located under of the main directory
   that you unjarred the main jar file.
          For example: if you unjarred the file into a directory called c:\FBN 
                       you would find the db.db at c:\FBN\db.db
       
4. Design Choices Document
   The design choices document is located in the located under of the main directory
   that you unjarred the main jar file under the name DESIGN_CHOICES.txt

5. File listing
   The following list outlines the contents of the Fly By Night application directory,
   as well as the purpose of each directoty or file.

   Install_DIR            
     + classes             DIRECTORY containing all the class files
     + src                 DIRECTORY containing all of the .java source files written during
                                     the course of the project  
     + userdocs            DIRECTORY containing all the javadoc and user documentation 
       +- javadoc          DIRECTORY containing all the java documentation
          +- index.html      This is the main starting point for viewing the FBN javadoc
       +- gui              DIRECTORY containing all the user documentation for the gui
          +- index.html      This is the main starting point for viewing the documentation of gui
       +- server           DIRECTORY containing all the user documentation for the data server
          +- index.html      This is the main starting point for viewing the documentation of server

     + db.db               Original database file ( given for the assignment )
     + Devassnmt2.jar      The original jar file received from Sun´s site for the assignment
     + FBNMain.jar         The client application ( executable jar file )
     + FBNServer.jar      The server application ( executable jar file )
     + DESIGN_CHOICES.txt  Document describing design choices made
     + README.txt          This file

