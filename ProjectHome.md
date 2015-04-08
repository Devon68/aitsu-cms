## aitsu - Das Open Source CMS-Framework für KMUs. ##

aitsu CMS Framework basiert auf Contenido, PHP, MySQL und Zend Framework. Mit aitsu steigern Anwender, Entwickler und Agenturen ihr Online-Potential, erweitern ihr Know-how und kommen einfach schneller zu sichtbaren Ergebnissen.

aitsu kommt mit **Zend Framework**, **jQuery**, **jQuery.UI** und **YAML-Support**.

Das aitsu Community Forum, das Wiki und die Webseite sind zur Zeit nur in Deutsch verfügbar. Wir arbeiten hart daran, die Inhalte schnell zu übersetzen. Wenn Du ein Englisch-Muttersprachler bist und aitsu gerne unterstützen möchtest, zögere nicht, Dich direkt mit uns in Verbindung zu setzen. Du bist stets willkommen.

Installationanleitung: http://www.aitsu.org/dokumentation/tutorials/installationsanleitung-aitsuce-final-release.html


---


## aitsu - The Open Source CMS-Framework System for SME. ##

aitsu CMS Framework is based on Contenido, PHP, MySQL and Zend Framework. With aitsu users, developers and agencies increase their online capabilities, extend their know-how and will easily come to viewable results fast.

aitsu comes with **Zend Framework**, **jQuery**, **jQuery.UI** and **YAML-support**.

The aitsu community board and wiki and even the web site is yet German only. We are working hard to get the translation done quickly. If you are english native speaking and would like to support aitsu, please don't hesitate to contact us directly. You are always welcome.

Visit www.aitsu.org from time to time to check if your language is available.

## Installation: ##

For the installation of aitsuCE you need to meet the following requirments:

  * Linux-/ Unix-System
  * Apache-Webserver
  * PHP from Version 5
  * MySQL from Version 5

The download includes the following file:

  * aitsuCE\_0.9.1\_final\_20100311.zip

### 1 Unzip ###

Switch to the root directory of the Web server and unzip the file. Note: Server root and web root are two different things. If the file is unpacked into the top level (server root), the domain must point into the directory aitsu/ (web root).

Following directories will be created.

  * ~
  * ..aitsu
  * ....admin
  * ....application
  * ....clienttemplate
  * ....cms
  * ....conlib
  * ....contenido
  * ....doc
  * ....library
  * ....pear

### 2 Configuration ###

Switch to the directory

`cd aitsu/application/configs/`

Open the configuration file.

`nano config.ini`

Complement your server path and database settings

```
[backend] 
; IMPORTANT: set this value to false after installation is complete 
admin.allowdiagnosewithoutlogin = true 

; Contenido Backend Server Path 
rootPath = /root/webseiten/aitsu 

; Contenido Backend Web Path 
rootUrl = http://www.domain.tld/contenido/ 

; Admin Web Path 
adminRoot = http://www.domain.tld/ 
contenido.client = 1 
contenido.language = 1 

; Database configuration 
database.adapter = pdo_mysql 
database.params.host = localhost 
database.params.username = dbuser 
database.params.password = "dbpass" 
database.params.dbname = dbname 
database.params.tblprefix = con_ 

sys.errorpage = 12 
sys.dbdumppath = /root/webseiten/aitsu/application/dbdumps 
sys.doLog = false 
sys.logPath = /root/webseiten/aitsu/application/logs 

; Buffering and Handler 
output.gzhandler = false 
output.stripwhitespace = false 

; Rewriting rewrite.controller = Aitsu_Core_Rewrite_Standard 
rewrite.uselang = true 
rewrite.omitfirst = true 
rewrite.modrewrite = true 

[client1 : backend] 
contenido.client = 1 
contenido.language = 1 
contenido.serverpath = /root/webseiten/aitsu/cms/ 
contenido.webpath = http://www.domain.tld/ 

sys.errorpage = 12 

; Buffering and Handler 
output.gzhandler = false 
output.stripwhitespace = true 

; Rewriting 
rewrite.controller = Aitsu_Core_Rewrite_Standard 
rewrite.uselang = true 
rewrite.omitfirst = true 
rewrite.modrewrite = true
```

### 3 Set file permissions ###

Switch to aitsu directory

`cd ../../`

Set file permissions:
Attention: The correct setting varies from provider to provider. Select the permissions as restrictive as possible.
Start with little file permissions (0744). If you notice any problems, increase the file permissions steop by step (0754), (0755). 0777 file permission is no protection at all. Find out more about this at your provider.

  * chmod -R 0755 contenido/logs/
  * chmod -R 0755 contenido/cache/
  * chmod -R 0755 contenido/cronjobs/
  * chmod -R 0755 contenido/temp/
  * chmod -R 0755 cms/cache/
  * chmod -R 0755 cms/css/
  * chmod -R 0755 cms/js/
  * chmod -R 0755 cms/logs/
  * chmod -R 0755 cms/templates/
  * chmod -R 0755 cms/upload/
  * chmod -R 0755 cms/version/

### 4 aitsu Diagnose ###

Start your web browser and switch to aitsu Diagnose

`http://www.domain.tld/admin/index.php/diagnose`

Click Installation & Configuration and follow the steps with mouse click one after the other.

### 5 Customize aitsuCE ###

Start the aitsu Backend within your web browser and switch to your desired language.

`http://www.domain.tld/contenido/ `

  * User: sysadmin
  * Password: sysadmin

Change the password of your systems administrator.

`Administration » User » sysadmin`

Important! Open the config.ini and make sure to set admin.allowdiagnosewithoutlogin from true to false to prevent unauthorized access to the system.

`admin.allowdiagnosewithoutlogin = false`

### Ready! ###

Start the aitsu Frontend within your web browser

`http://www.domain.tld/cms/`

Congratulations. You have successfully installed aitsuCE.