Using Swestore iRODS
=====================

Download and upload data
-------------------------

From the command line
^^^^^^^^^^^^^^^^^^^^^^
There are several command line tools capable of using the protocols provided by Swestore iRODS. For interactive usage on SNIC clusters we recommend using the iCommands which should be installed on all SNIC resources. There are too many commands to document fully here. 

 - Please check full and updated documentation at `iRODS official Documentation <https://docs.irods.org/master/icommands/user/>`_.
 - The command line client may be downloaded from `iRODS Download page <http://irods.org/download/>`_. 
 - Configuration of the icommands requires a file called **irods_environment.json** to be placed in a subdirectory **.irods/** of your home directory (e.g. ~/.irods/irods_environment.json).
 - A template of this file is available: **download irods_environment.json**. 

You must edit this with a text editor (not MS word, but notepad for Windows, textEdit for Mac or any Unix editor) and put your SNIC username in the place for <YOUR_SNIC_USER_NAME>.::

 {
    "irods_host": "irods-login.swestore.se",
    "irods_port": 2432,
    "irods_default_resource": "SNICDisk",
    "irods_home": "/snic.se/home/<YOUR_SNIC_USER_NAME>",
    "irods_cwd": "/snic.se/home/<YOUR_SNIC_USER_NAME>",
    "irods_user_name": "<YOUR_SNIC_USER_NAME>",
    "irods_zone_name": "snic.se",
    "irods_client_server_negotiation": "request_server_negotiation",
    "irods_client_server_policy": "CS_NEG_REFUSE",
    "irods_encryption_key_size": 32,
    "irods_encryption_salt_size": 8,
    "irods_encryption_num_hash_rounds": 16,
    "irods_encryption_algorithm": "AES-256-CBC",
    "irods_default_hash_scheme": "SHA256",
    "irods_match_hash_policy": "compatible",
    "irods_authentication_scheme": "PAM"
 }


From GUI client
^^^^^^^^^^^^^^^^^
Graphical User Interface (GUI) clients are known to work on some operating systems.

 Cyberduck
   Is a graphical client for Windows and OS X.
   
   #. Download and install Cyberduck from https://cyberduck.io.
   #. Download and open the **Swestore iRODS cyberduck profile** (right click and select 'save link as' to download). Then click on the profile, cyberduck should then open the connection as a cyberduck book mark.
   #. Edit the profile as below changing the path to /snic.se/home/<YOUR_SNIC_USER_NAME> 
   #. Close the profile and double click on the bookmark in cyberduck - if the bookmark is not visible, then you can bring it up by going to the menu Bookmark->toggle bookmarks. This should bring up the login prompt. Enter your SNIC username and password. A peculiarity of cyberduck with iRODS is that you must put the text PAM: before your username as is shown below.
   #. Once you have successfully authenticated you should get a view of your home directory.
   
 Access using WebDAV (map a network drive)
  - WebDAV on Windows 10
    https://snic-irods-webdav.pdc.kth.se:8443/snic.se/home/
  - WebDAv on OS X
    https://snic-irods-webdav.pdc.kth.se:8443/snic.se/home/
  - WebDAV on Linux
    https://snic-irods-webdav.pdc.kth.se:8443/snic.se/home/
    
From a web browser
^^^^^^^^^^^^^^^^^^^
 Davrods
  Swestore iRODS is accessible in your web browser as a simple directory index interface at https://irods-webdav.swestore.se:8003/. 
  To browse private data you need to authenticate with your username and password.  

 * **Projects** are organized under the /projects directory as https://irods-webdav.swestore.se:8003/projects/YOUR_PROJECT_NAME/.
 * **Home** can be accessed at https://irods-webdav.swestore.se:8003/home/YOUR_USER_NAME/. 
 * **Public** can be accessed at https://irods-webdav.swestore.se:8003/home/public/. 

 EMC Metalnx
  The EMC Metalnx is an administrative and metadata management user interface (UI) for iRODS. You can access it at https://irods-web.swestore.se

