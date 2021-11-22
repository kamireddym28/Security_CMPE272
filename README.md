CMPE_272 Sec#48 
Enterprise Software Platforms

HW#7_SECURITY

Problem Statement:  Design and build a PKI infrastructure that includes Root CA, Signing CA, and TLS Certificate. Use the TLS certificate to install a web server, e.g. tomcat.

Team: Akatsuki

Team members:
•	Archana Miyar Kamath
•	Simran Tanvir Memon
•	Mounica Kamireddy
•	Limeka Dabre

Implementation:

Step_1: To get started firstly, git clone  https://bitbucket.org/stefanholek/pki-example-1  and then follow the instructions as provided here: https://pki-tutorial.readthedocs.io/en/latest/simple/ for creating a simple pki infrastructure.

Step_2:  Creating root CA with the help of commands mentioned in above link: 
	 Creating directories and Create database
   - database files created:  root-ca.crl.srl  root-ca.crt.srl  root-ca.db  root-ca.db.attr
![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/database_files.png?raw=true)
	
 

	 Create CA request
![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/private_key_created.png?raw=true)
-	passphrase for private key for Root CA Request: "first"

 

	Create CA certificate
![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/CA_cert_self-signed.png?raw=true)
 

Step_3:  Create Signing CA
	       Create Directories
![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/create_signing_ca.png?raw=true)
 

	Create database
![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/create_db-signing_ca.png?raw=true)
 

	Create CA request
-	passphrase for private key for Signing CA Request: "second"
![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/create_signing_ca-private-key.png?raw=true)
 

	Create CA certificate
![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/ca_cert-signing-ca.png?raw=true)

 
Step_4:  Operate Signing CA
	Create email request
-	passphrase for private key for 'certs/fred.key' email request: "third"
![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/email_req-sign-ca.png?raw=true)
 

	Create email certificate
![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/email_certf-sign-ca.png?raw=true)
 

 Create TLS server request
![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/create_tls_server_req.png?raw=true)

 

Create TLS server certificate

![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/tls_server_cert_created.png?raw=true)

 

	Revoke certificate
  
![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/revoke-certf.png?raw=true)
 

Create CRL

![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/crl_created.png?raw=true)
 
Step_5:  Output Formats

Create DER certificates

![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/DER-cert-created.png?raw=true)
 

	Create DER CRL
  
![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/DER-crl-created.png?raw=true)
 

	Create PKCS#7 bundle
  
![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/create_PKCS%237_bundle.png?raw=true)
 

	Create PKCS#12 bundle
  
![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/create_PKCS%2312_bundle.png?raw=true)
 

Create PEM bundle

![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/PEM_bundles_created.png?raw=true)

Step_6:  View Results
	View Request
  
  ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/view_req_1.png?raw=true)
  
   ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/view_req_2.png?raw=true)
  
	View Certificate
  
 ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/view_certf_1.png?raw=true)
 
  ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/view_certf_2.png?raw=true)
   
	View CRL
  
 ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/view_crl.png?raw=true)
 

	View PKCS#7 bundle
  
 ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/view_pkcs%237_bundle_1.png?raw=true)
 
  ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/view_pkcs%237_bundle_2.png?raw=true)
  
   ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/view_pkcs%237_bundle_3.png?raw=true)
 

	View PKCS#12 bundle
  
 ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/view_pkcs%2312_bundle_1.png?raw=true)
 
  ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/view_pkcs%2312_bundle_2.png?raw=true)

 

Step_7:  Using the TLS certificate created, install the web server Tomcat. Refer link: https://tomcat.apache.org/tomcat-7.0-doc/ssl-howto.html for the commands to be executed.

	To create a new JKS store for Tomcat:
  
Command: Keytool -genkey -alias tomcat -keyalg RSA -keystore tomcat.jks

 ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/keytsore_tomcat_new.png?raw=true)
 
Generate a new csr for Tomcat:

 ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/tomcat_csr_new.png?raw=true)
 

	Sign the certificate for Tomcat using the root certificate:
  
 ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/tomcat_certf_new.png?raw=true)
 

Import Root certificate and Tomcat certificate: 

 ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/import_root_certf_new.png?raw=true)
 
 ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/import_tomcat_certf_new.png?raw=true)
 

The Tomcat server is running with TSL/SSL enabled on port 8443

 ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/tomcat_start_with_certf_new.png?raw=true)
 
 ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/localhost_8443.png?raw=true)
 
 ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/port_8443.png?raw=true)
 
 ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/certf_1.png?raw=true)
 
 ![alt text](https://github.com/simran-memon/Security_CMPE272/blob/main/assignment_screenshots/certf_2.png?raw=true)
 

References:

•	http://www.openssl.org/docs/apps/req.html

•	http://www.openssl.org/docs/apps/ca.html

•	https://deliciousbrains.com/ssl-certificate-authority-for-local-https-development/

•	https://serverfault.com/questions/483465/import-of-pem-certificate-chain-and-key-to-java-keystore

