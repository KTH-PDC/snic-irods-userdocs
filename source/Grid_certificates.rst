Grid certificates
==================

Short introduction to certificates
----------------------------------

In order to get access to Swestore or any other grid compute or storage resources you must have a valid (eScience) client certificate. This certificate is used instead of a username and password when accessing the resource. The resource itself has a server certificate that ensures you have connected to the right resource. This is exactly the same mechanism used when you use a web browser to contact your bank.

A certificate is the similar to a passport in real-life. In the same way you have to prove who you are when you acquire a passport the same is true for a certificate. A third party, the Certificate Authority (CA), issues a certificate (passport) that both you and the resource trust. They vouch for your identity and has signed your certificate.

A certificate consist of a public key, some user information and the signature of the CA. In addition to the certificate you have a corresponding private key. The private key is secret and should be kept as secure as possible.

The grid certificate and private key is stored in your web browser and/or in your home directory on the host where you will be accessing the resource. Standard file names are:

 ``~/.globus/usercert.pem``

 ``~/.globus/userkey.pem``

The certificate contains your public key, your name and organization and a signature by the CA. It is does not contain any username.
The certificate is valid for 13 month and should be renewed yearly.
The private key should be handled with great care. It should only be readable by you and not by the group or others (i.e. "chmod 400 userkey.pem"). Store the key on trusted computers and transfer the key between computers using encryption (using for example scp).
On shared file systems make sure that ~/.globus is not readable by everybody:

 ``chmod 700 ~/.globus``

 and on AFS:

 ``fs sa ~/.globus system:anyuser none``

The private key should be encrypted using a passphrase. Anyone that can decrypt the private key will be able to authenticate as you to grid resources. This is similar to the private key in SSH. You must choose a strong passphrase for the private key. This passphrase must not be used anywhere else. You must never ever give away or share the certificate, passphrase or the unencrypted key to someone else.

For more information regarding certificates and public key cryptography:

* http://en.wikipedia.org/wiki/Public-key_cryptography
* http://en.wikipedia.org/wiki/Public_key_certificate
* http://www.nordugrid.org/documents/certificate_howto.html

Requesting a certificate
-------------------------

Certificates are issued by a Certificate Authority or CA. The certificate needed for accessing the Swestore or other grid resources should have the eScience Personal or Grid Premium type, not all CA:s are certified by `The International Grid Trust Federation <https://www.igtf.net/>`_ to issue these.
For users residing in the Nordics there are two relevant CA:s that can issue grid/eScience/e-Science certificates: Digicert and Nordugrid. The Digicert CA is preferred if it is available for your university or research group, but some institutions has not enabled this service yet. The Nordugrid CA can also be used but requires more manual labor by all parties.

NOTE: The Terena CA portal has been replaced with the DIGICERT portal, instructions below might need updating

Recommended procedure for each university:

======================================== ============== ===============================================================================================================
University                               Recommended CA Specific instructions
======================================== ============== ===============================================================================================================
Chalmers University of Technology (CTH)  Digicert	`CTH C3SE Documentation <http://www.c3se.chalmers.se/index.php/Personal_certificates>`_
University of Gothenburg (GU)	         NorduGrid	`SNIC for GU Documentation <http://docs.snic.se/wiki/GU_Certificate_Instructions>`_
Karolinska Institutet (KI)	         Digicert	`KI Documentation <https://internwebben.ki.se/sv/personliga-certifikat>`_
KTH Royal Institute of Technology (KTH)	 Digicert	`SNIC for KTH Documentation <http://docs.snic.se/wiki/KTH_Certificate_Information>`_
Linköping University (LiU)	         Digicert	`LiU Documentation <http://liu.se/insidan/it/irt/personliga-certifikat>`_
Luleå University of Technology (LTU)	 NorduGrid	`Nordugrid CA Documentaion  <http://docs.snic.se/wiki/Requesting_a_grid_certificate_from_the_Nordugrid_CA>`_
Lund University (LU)	                 Digicert	`LU Documentation <http://www.ldc.lu.se/tjanster/it-sakerhet/certifikat>`_
Sveriges Lantbruksuniversitet (SLU)	 Digicert	`SNIC for SLU Documentation <http://docs.snic.se/wiki/Requesting_a_grid_certificate_using_the_Digicert_SSO_Portal>`_
Stockholm University (SU)	         Digicert	`SNIC for SU Documentation <http://docs.snic.se/wiki/SU_Certificate_Information>`_
Umeå University (UmU)	                 Digicert	`SNIC for UmU Documentation <http://docs.snic.se/wiki/UmU_Certificate_Information>`_
University of Borås (UB)	         Digicert	`SNIC for UB Documentation <http://docs.snic.se/wiki/Requesting_a_grid_certificate_using_the_Digicert_SSO_Portal>`_
Uppsala University (UU)	                 Digicert       `SNIC for UU Documentation <http://docs.snic.se/wiki/UU_Certificate_Instructions>`_
======================================== ============== ===============================================================================================================       

`Instructions for the Digicert CA <http://docs.snic.se/wiki/Requesting_a_grid_certificate_using_the_Digicert_SSO_Portal>`_

`Instructions for the NorduGrid CA (use this only if Digicert isn't available at your site) <http://docs.snic.se/wiki/Requesting_a_grid_certificate_from_the_Nordugrid_CA>`_







