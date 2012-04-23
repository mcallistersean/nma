Technical Reference for database administrators
===============================================

This section is meant for whoever is responsible for administrating the NMA's
database. It will be a small collection of HOW-TOs explaining the usage of
certain aspects of the system in front of you.

Backing up your database
------------------------
The most important parts of the system are located in the follwong directory:
    
    /home/nma/NMA_DATA
    
This directory holds the actual database files (in the "db" folder) and the images
(in the "images" folder). Another folder holds the automatically generated thumbnails.

In order to backup the system it should be sufficient to copy the "db" and "images" folder 
to the designated backup medium (CD, DVD, external HDD).



Updating the system
-------------------
Since I am trying to find some time in Austria to improve the system you will get updates 
from me via the internet. Again, if there are problems or, please don't hesitate to write 
me an email.

That said, here are some basic guidelines to update to the latest source code:

1. Open up a Terminal (Appications -> Accessoires -> Terminal)

2. Type the following commands, each in one line:
    
   workon nma
   
   cd /home/nma/env/nma/nma
   
   hg pull
   
   hg update
   
3. Now you should have the latest source code for the nma system, but there are still 
   some things to get done:
       
        - first, update the documentation:
           
           cd docs
           
           make html
           
           cd ..
           
        - update the language files
        
          ./update_languages.sh
          
        - and finally restart the webserver (this will ask for your password)
           
           sudo /etc/init.d/apache2 restart
           
If you have any problems please contact me.