# Deployment

To meet Moravia standard for quality of software development it is recommended that every project have automated deployment.

## General Guidelines
* **DO NOT install dev, test and production environments manually.** Use versioned scripts and package managers to install machine to desired state
* **DO NOT deploy application manually.** Always use independent deployment system like TeamCity.
* **Avoid to use passwords** in deployment scenarios. Use integrated security features like NTLM and Kerberos for authentication. At least do not store the passwords in plaintext. 
* **Do not store passwords and private keys** for deployment to production in VSC repository.

## Web Applications in IIS
* Do use msdeploy to deploy applications via Teamcity (http://www.iis.net/downloads/microsoft/web-deploy)
