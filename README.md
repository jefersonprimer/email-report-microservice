# Micro-service with Spring + Oracle Cloud
The objective of this project was to exemplify how to create a complete microservice using Spring Boot, integrating with Oracle Cloud's free mode services for storing objects, files and sending emails. The idea is to simulate a microservice capable of generating and sending reports by email, using Object Storage and Mail Delivery services.

## Oracle Cloud Free Mode

If you want to create a free account on Oracle Cloud, access the link [Oracle Cloud Free Tier](https://social.ora.cl/60049HoAk) e siga as instruções. 

The free account offers services with unlimited use such as Virtual Machine Instances, Object Storage, Email Delivery, NoSQl Database and SQL Database.

## Prerequisites for execution
* [Have an Oracle Cloud account](https://social.ora.cl/60049HoAk)
* Java Version 21
* Maven 3.9.7

## Settings

### Application.properties

The configuration file`application.properties` must be configured with your Oracle Cloud account information. To do this, you must fill in the file `application.properties` in the folder `src/main/resources` with the following information:

```properties
# Oracle Cloud  
spring.application.name=mailservice
spring.mail.username=YOUR_STMP_USERNAME
spring.mail.password=YOUR_SMTP_PASSWORD
spring.mail.from=YOUR_REGISTERED_EMAIL
spring.mail.properties.mail.smtp.auth=true
spring.mail.properties.mail.smtp.starttls.enable=true
spring.mail.properties.mail.smtp.starttls.required=true
spring.mail.properties.mail.smtp.ssl.trust=smtp.email.sa-saopaulo-1.oci.oraclecloud.com
spring.mail.host=smtp.email.sa-saopaulo-1.oci.oraclecloud.com
spring.mail.port=587
spring.mail.protocol=smtp
```

### SDK Credentials Configuration

In the archive `.oci/config` you must configure Oracle Cloud access credentials. To do this, you must fill in the file`.oci/config` in the project root folder with the configs generated in your account.

**Step by step**

1. Log in to your Oracle Cloud account.
2. Go to your profile details page in the OCI console. Go to the “API Keys” tab. Click on the “Add API Key” button. This will open the following pop-up window.
3. Enter a name for the API key and click the “Add” button. This will download the API key file.
4. Copy the contents of the file and paste it into the ~/.oci/config file on your local machine.

```properties
[DEFAULT]
user=YOUR_USER_ID
fingerprint=FINGERPRINT
tenancy=TENANCY_ID
region=sa-saopaulo-1
key_file=private-key.pem
```
