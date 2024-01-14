# Review on https://github.com/ehbstudentadam/aboutadamdocker.

This report concerns a review on an application build by my fellow student **Adam Lenez**.
The source code of this application is to be found at github in the public repo https://github.com/ehbstudentadam/aboutadamdocker.  
The application itself is publicly hosted and available at https://fissirostral-turbin.000webhostapp.com/.

## Description on the application

As preparation for this review some 

### Functional

The application is a intro/bio on Adam (about, hobbies, studies, goals, ...) written in the context of the course "Backend Web".  

![](functional/homepage.png)

#### Dynamic part: Contact

The application is mostly static in nature but contains the possibility to the visitor in 
leaving behind some comments or messages towards Adam at contact-page (see https://fissirostral-turbin.000webhostapp.com/contact)

![](functional/contactpage.png)

### Technical

![](architecture/security_review.png)


## Nog te wijzigen

* password root invullen in .env
* permissies probleem sudo chmod -R a+rwx ./src/
* docker compose exec php artisan key:generate

## Approach

The application is for the largest part a static website.
The focus in this case however lies in the analysis of the operational and infrastructure part.

Beside that the performing dast with ZAP

What I can break in de local I will also use in the cloud

### Minimizing

### Preparation: what needs to be checked

## Things to abuse

http://localhost:8080/api/user renders 500-error-code which exposes a debug-mode

### SNYk

1 critical 3 hight

### Docker libraries and utilties

not minimized, waarom git??? waarom dev

### htaccess

.htaccess
website lijkt te beschermen hiertegen

### Embedded .env-file

code naar container bougeren...
.env file kan 

docker compose exec app cat .env

https://docs.docker.com/compose/use-secrets/

### Potential DDOS

Large bodies

## Type of application

PHP, Laravel-based, Eloquent
Docker compose

Voornamelijke statische applicatie met uitzondering van het formulier.
Focus ligt dus meer op configuratie en systeem

## Hoe de applicatie deployen

~~~
$ git clone git@github.com:ehbstudentadam/aboutadamdocker.git
$ docker compose up --build
$ docker compose exec app composer install
$ docker compose exec app php artisan migrate
$ docker compose exec "php artisan key:generate"
~~~

https://www.youtube.com/watch?v=DYptNrZXIIo

### Access the database

http://localhost:3400/index.php?route=/sql&db=aboutadamproject&table=messages&pos=0

https://logmeonce.com/resources/default-phpmyadmin-password/#:~:text=Usually%2C%20the%20default%20username%20and,'%E2%81%A2%20and%20'password'.&text=If%20the%20default%20username%20and,%E2%80%8Cthat%20the%20configuration%20file%20(config.

https://cheatsheetseries.owasp.org/cheatsheets/Laravel_Cheat_Sheet.html

## Where to look for with Laravel-apps

Checklist opbouwen en aflopen

https://stephenreescarter.net/talks/hacking-laravel/

https://www.google.com/search?channel=fs&client=ubuntu-sn&q=attacking+a+laravel+application

https://medium.com/@prevailexcellent/protect-your-laravel-app-5-expert-strategies-to-foil-hackers-d44b419d549d

https://www.linkedin.com/pulse/securing-laravel-applications-best-practices-web-security-tuhin/


https://cheatsheetseries.owasp.org/cheatsheets/Laravel_Cheat_Sheet.html

https://stillat.com/blog/2016/11/16/laravel-security-helper-function-e-for-html-entities

https://security.snyk.io/package/composer/laravel%2Fframework

https://book.hacktricks.xyz/network-services-pentesting/pentesting-web/laravel

https://infosecwriteups.com/the-big-danger-with-laravel-env-file-403ca60aaf14

## DDOS-attach

Zeer grote request

## Aanpak

* Static Analysis Security Testing (SAST)
    * Semgrep
    * SonarQube
    * phpstan
* Software Composition Analysis (SCA)
    * Dependabot
    * SNYK
* Dynamic Analysis Security Testing (DAST)
    * ZAP

Architectuur van de applicatie

Wat zijn de bais regels
Review op basis van deze regels

Tools -> Analyzeren

Uitsluiten maar toch toei, Mitigeren, Patchen

Analyzeren 

##

http://fissirostral-turbin.000webhostapp.com/ is mogelijk je kan naar poort 80

http://fissirostral-turbin.000webhostapp.com:3400/

http://localhost:3400/

## Docker

* Usage of unecessary libraries
* Usage of dev

## Sonarqube

Problems with java17+ for sonarqube

~~~
export SONAR_JAVA_PATH=/usr/lib/jvm/java-1.17.0-openjdk-amd64/bin/java
~~~

https://docs.sonarsource.com/sonarqube/10.3/analyzing-source-code/scanners/sonarscanner/

~~~
sqp_e09f738c318eb958e0c6799afce96d6195e32f91

/home/bart/Downloads/sonar-scanner-cli-5.0.1.3006-linux/sonar-scanner-5.0.1.3006-linux/bin/sonar-scanner \
  -Dsonar.projectKey=adam-review \
  -Dsonar.sources=. \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.token=sqp_e09f738c318eb958e0c6799afce96d6195e32f91
~~~

http://localhost:9000/projects

## Semgrep

https://semgrep.dev/docs/getting-started/quickstart/

~~~
$ python3 -m pip install semgrep
$ semgrep login
$ semgrep scan
$ semgrep ci
~~~

## ZAP

/home/bart/2024-01-12-ZAP-Report-.html

### SNYK

https://docs.snyk.io/snyk-cli/install-or-update-the-snyk-cli#install-the-snyk-cli-with-npm-or-yarn


https://app.snyk.io/org/bartvoet/project/fde697c5-92be-4957-912b-4a7712b69f29

### Pint

https://laravel.com/docs/10.x/pint

### PHPStan 

https://github.com/larastan/larastan
https://phpstan.org/user-guide/getting-started

## PHPInsights

~~~
sudo apt install php-mbstring
composer require nunomaduro/phpinsights --dev
php artisan vendor:publish --provider="NunoMaduro\PhpInsights\Application\Adapters\Laravel\InsightsServiceProvider"

• [Code] Disallow empty:
  app/Http/Middleware/RedirectIfAuthenticated.php:22: Use of empty() is disallowed.

• [Code] Disallow short ternary operator:
  app/Providers/RouteServiceProvider.php:49: Use of short ternary operator is disallowed.

• [Code] Useless constant type hint:
  app/Providers/RouteServiceProvider.php:18: Useless @var annotation.

• [Code] No empty comment:
  app/Providers/AppServiceProvider.php: 
@@ -15,3 +15,3 @@
     {
-        //
+        
     }
@@ -25,3 +25,3 @@
     {
-        //
+        
     }
  app/Providers/AuthServiceProvider.php: 
@@ -27,3 +27,3 @@
 
-        //
+        
     }
  app/Providers/EventServiceProvider.php: 
@@ -29,3 +29,3 @@
     {
-        //
+        
     }
  +5 issues omitted

• [Code] Unused parameter:
  app/Http/Controllers/AboutAdamController.php:90: Unused parameter $id.
  app/Http/Controllers/AboutAdamController.php:90: Unused parameter $request.
  app/Http/Controllers/AboutAdamController.php:101: Unused parameter $id.
  +3 issues omitted
...
~~~

### Rector

...

### Dependabot

https://github.com/bartvoet/adamlenez-review/security/dependabot/1

## System

##

## GDPR

As a visitor of the site I can leave comment but there is no indication on what to do with it.

## htacess

https://www.sitelock.com/blog/common-htaccess-file-hacks/

