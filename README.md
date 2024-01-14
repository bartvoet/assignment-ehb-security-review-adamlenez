# Review on https://github.com/ehbstudentadam/aboutadamdocker.

This report concerns a review on an application build by my fellow student **Adam Lenez**.
The source code of this application is to be found at github in the public repo https://github.com/ehbstudentadam/aboutadamdocker.  
The application itself is publicly hosted and available at https://fissirostral-turbin.000webhostapp.com/.

## Applicative description

As preparation for this review I describe briefly the application from a functional and technical (+ operational) point of view.  
The goal of this is to be able to refer to these parts further in this document as we start with review.

### Functional setup

The application is a intro/bio on Adam (about, hobbies, studies, goals, ...) written in the context of the course "Backend Web".  

![](functional/homepage.png)

#### Dynamic part: Contact

The application is mostly static in nature but contains the possibility to the visitor in 
leaving behind some comments or messages towards Adam at contact-page (see https://fissirostral-turbin.000webhostapp.com/contact)

![](functional/contactpage.png)

### Technical setup

#### Frameworks

* The language used is **PHP**, version **8.3**
* The runtime container (and dependency injection) is **Laravel**-based
* **Eloguent** is being used as a persistence framework 

#### Middleware

* **MySQL** is used for **storing** contact information into a relational database
* **NGNIX** is used as a web server/proxy for the PHP/Laravel-application


#### Docker setup (and docker compose)

The application in github by Adam is docker-based.  
I created a small diagram as an overview of the setup described with the docker-compose.yaml to be found in the root of the source tree.

![](architecture/security_review.png)

4 containers are active:

The  PHP
  * Based on php:8.3.11-f
  * Specific Dockerfile to be found in the repo
* 

#### Cloud setup

https://fissirostral-turbin.000webhostapp.com/

https://www.youtube.com/watch?v=DYptNrZXIIo


## Approach

The application is for the largest part a static website.
The focus in this case however lies in the analysis of the operational and infrastructure part.

Beside that the performing dast with ZAP

What I can break in de local I will also use in the cloud

## Review

### Manual code inspection

#### Development mode

http://localhost:8080/api/user renders 500-error-code which exposes a debug-mode

#### Code-validation

2MB

Zeer grote request


### Privacy and GDPR

#### (PR01) Contact form need to align to GDPR regulations

A visitor is allowed to leave a message by filling out a form so that the owner (Adam in this case) can contact visitors of the site.

The data that the visitor provides is structured by:

* Name
* Email address
* Phone Number
* The actual message

In the context of GDPR the data - which is entered by the visitor - can be considered **personal information**.  
Depending on the nature of the message left behind, the data can also be considered  can also in some cases be considered sensitive data.

From the website it's not transparent:

* How the data is been processed
* For what purposes will it be used
* Retention period for this data?  Will this data being kept in a database forever or will it be removed after some time?
* ...

#### (PR01) Solution: Provide a privacy notice

#### (PR01) Solution: Provide a processing register



#### Suggestions
 


