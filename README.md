# Modul 346
## KN00
### Cloud-init
Eine Cloud init Datei ist die Generelle bezeichnung für ein File das für die Konfiguration und steuerung einer Cloud umgebung Verantwortlich ist. In dieser Cloud init Datei sind anweisungen enthalten die beim start einer VM oder des Containers zum Beispiel ausgeführt werden. kSo ein Cloud init File kann auch in verschiedenen Dateitypen sein zum Beispiel YAML JSON oder Bash. In diesem File sind Netzwerkkonfigurationen enthalten, Benutzerrechte, Softwareinstallationen und Konfigurationen.
#### Eine virtuelle instanz mit Cloud Init installieren
1. Erstellen einer VM in einer Cloud Umgebung
2. Danach sollte man die Konfigurations und Meta Dateien angeben die wärend dem erstellen dann verwendet werden.
3. Sobald die VM erstellt ist ruft die cloud init Datei die Konfigurationsdatein ab und führt diese Aufgaben aus.
#### Was ist Infrastructure as Code
IaC ist ein Konzept mit dem man mit hilfe von Code Herausfindet welche Infrastruktur anforderung mein System hat. Das bedeutet das die gesamte Infrastruktur mit allem nötigen per code beschrieben und behandelt wird.
##### Welche Produkte bieten Infrastructure As  Code an
1. Terraform
2. AWS CloudFormation
2. Azure Resource Manager Templates
3. Google Cloud Deployment Manager
4. Ansible
5. Viele weitere
### Virtualisierung
Ein Hypervisor ist für die bereitstellung und verwaltung von VMs zuständig.
1. Typ1 wird direkt auf der Hardware installiert.
2. Typ2 wird auf einem bereits vorhanden Betryíebsystem installiert.

Was ist ein hyperscaler
Das ist ein cloud anbieter der eine sehr grosse Infrastruktur hat das heisst grosse skalierbarkeit für den Kunden. 

### Betriebsmodelle
#### On Premise
Die ganze hard und software wird

### Unterschied Public und Private cloud
In der Public Cloud werden Resourcen von einem Anbieter bereitgestellt und dann von mehreren Benutzern benutzt die Sicherheit häng sehr stark von dem Anbieter ab und ist auch in seiner Verantwortung. Bei der Private cloud ist das anders dort hat die Organistation die komlette kontrolle. Jedoch hat man in der Orivat cloud auch höhere kosten für hardware.



## Servicemodelle

#### 1.Infrastructure as a Service
Bei diesem Modell werden grundlegende Komponenten bereitgestellt wie Maschienen Speicher Netzwerke etc. Dort kann man dann seine eigenen Betriebsysteme und anwendungen installieren.
#### Platform as a service
Hier kann man sich voll auf die entwicklung des Services oder der Anwendung. Das heisst Aspekte wie betriebsystem oder Netzwerkinfrastruktur wird vom Anbieter übernomen.
#### Software as Service
Bei diesem Modell muss sich um nichts gekümmert werden es wird netzwerk Hardware infrastruktur einfach alles bereitgestellt und man kann einfach die anwendungen verwenden.
#### Function as a Service
Dies ist eine Option die es einem ermöglicht einzele codeabschnitte auf einer serverlosen einheit laufen zu lassen. Ohne sich um die verwaltung zu kümmern.
### Beispiel Infrastructure as a Service
AWS
### Beispiel Platform as a service
MS Azure
### Beispiel Software as Service
MS Office 365

# AWS
## KN02
### EC2
![Bild1](./1.png)
![Bild1](./2.png)
### S3
![Bild1](./3.png)
![Bild1](./4.png)

### SSH-Key
![Bild1](./5.png)
![Bild1](./6.png)
### Web- und Datenbankserver
![Bild1](./7.png)
![Bild1](./8.png)
## KN03
### Cloud-init Datei Verstehen
#cloud-config
users: #Anfang User Konfiguration
  - name: ubuntu #user ubuntu wird erstellt
    sudo: ALL=(ALL) NOPASSWD:ALL #user ubuntu kann alles mit sudo machen ohne passwort
    groups: users, admin # ubuntu wird der gruppe users und admin hinzugefügt
    home: /home/ubuntu #Das heimverzeichnis des users Ubuntu wird festgelegt
    shell: /bin/bash #standart shell des users ubuntu wird festgelegt
    ssh_authorized_keys: #Konfiguration für zugelassene ssh schlüssel
      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC0WGP1EZykEtv5YGC9nMiPFW3U3DmZNzKFO5nEu6uozEHh4jLZzPNHSrfFTuQ2GnRDSt+XbOtTLdcj26+iPNiFoFha42aCIzYjt6V8Z+SQ9pzF4jPPzxwXfDdkEWylgoNnZ+4MG1lNFqa8aO7F62tX0Yj5khjC0Bs7Mb2cHLx1XZaxJV6qSaulDuBbLYe8QUZXkMc7wmob3PM0kflfolR3LE7LResIHWa4j4FL6r5cQmFlDU2BDPpKMFMGUfRSFiUtaWBNXFOWHQBC2+uKmuMPYP4vJC9sBgqMvPN/X2KyemqdMvdKXnCfrzadHuSSJYEzD64Cve5Zl9yVvY4AqyBD aws-key       # öffentlicher ssh schlüssel für den user ubuntu
ssh_pwauth: false #passwort wird deaktiviert damit sich der user nur per ssh einloggen kann
disable_root: false #root user wird nicht gelöscht
package_update: true # System wird bei der erstellung geupdated
packages:
  - curl # Befehlszeilentool das zum übertragen von Daten zuständig ist.
  - wget # Befehlszeilentool das zum Herunterladen von daten aus dem Internet zuständig ist.
### SSH-Key und Cloud-init
#### Angepasstes cloud init
#cloud-config
users:
  - name: ubuntu
    sudo: ALL=(ALL) NOPASSWD:ALL
    groups: users, admin
    home: /home/ubuntu
    shell: /bin/bash
    ssh_authorized_keys:
      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQClMuN4c8pSm7QH4RDE2Mx3uEWWihkZ36qAondBO+sGkJtMeX+W5BwTHCSFNqyniqKuMHcKcYhfzcMHMtFB3+k3oIHx2hle7KY9ZAzoefAa/WBQOdpwwwEVMhIGQmqH1IA2xbseQbOYBdu8q4U5fEvHWyrDZyjqYRcmoIH8iOoKCZZ5NfaAPixvdxd4aOYpIsDa/Xujk7vyYl0Wto8SYni91Cb5iygvS95tJyPfTtrNjGuOdVnCRKRRmX4AQefpHmnKJmsT41VLYjJI8OhtLD2KJ6MImJBcPqIsiw8mYMDwJTvKFUrwrR7JM7c2gVNA6Ypv88pBtFMfZpEJ8BhTTM9z aws-key       
ssh_pwauth: false
disable_root: false 
package_update: true
packages:
  - curl 
  - wget 

#### Schlüsselpaar beim Start zugewiesen
![Bild1](./9.png)
#### Zugriff per SSH durch den ersten schlüssel
![Bild1](./10.png)
#### Zugriffsversuch per SSH durch den zweiten Schlüssel
![Bild1](./11.png)
#### Cloud init log
![Bild1](./11.png)
#### cloud-init-output log
![Bild1](./12.png)
#### MariaDB
![Bild1](./13.png)
#### telnet
![Bild1](./14.png)
#### telnet
![Bild1](./15.png)
#### Cloud init
#cloud-config
users:
  - name: ubuntu
    sudo: ALL=(ALL) NOPASSWD:ALL
    groups: users, admin
    home: /home/ubuntu
    shell: /bin/bash
    ssh_authorized_keys:
      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCJcKHgH4tZN1XjGda61Bwxgq+kqrsblBy/H+n6/h107YRRYRpOi3UeG6u5ibS1+dAZKPr2lF9JWUAn/zqbFDfTUR7p05b+XwJ0LkB+AafL1vM6Spp8NTqU6QqXpXm8309lP3IlD6T5w+sJlmm5ixpOnv711y1zVnUBvA492O/dqG/gt7xNEMMxVzB/5Lw0bxQz1AEWPAIol0WeLQKfN8sSd/jerOVcHKabt9pk3BdqwJWx0YRDDfICPFKw43mcfzFhytGtkH87nMnT61jA4/ZFSzPiFJYueabkBIC9tEzuCm0fJWaXe+vL0oaIurohtwdIb5nU5diQuNYzjeD2PXIH aws-key       
ssh_pwauth: false
disable_root: false 
package_update: true
packages:
  - curl 
  - wget
  - mariadb-server
runcmd:
  - sudo mysql -sfu root -e "GRANT ALL ON *.* TO 'admin'@'%' IDENTIFIED BY 'password' WITH GRANT OPTION;"
  - sudo sed -i 's/127.0.0.1/0.0.0.0/g' /etc/mysql/mariadb.conf.d/50-server.cnf
  - sudo systemctl restart mariadb.service
  #### index.html
  ![Bild1](./16.png)
  #### info.php
  ![Bild1](./17.png)
  #### db.php
  ![Bild1](./18.png)
  #### adminer
   ![Bild1](./19.png)

 ## KN04

![Bild1](./20.png)
![Bild1](./21.png)
![Bild1](./22.png)
![Bild1](./23.png)
![Bild1](./24.png)



  #cloud-config
users:
  - name: ubuntu
    sudo: ALL=(ALL) NOPASSWD:ALL
    groups: users, admin
    home: /home/ubuntu
    shell: /bin/bash
    ssh_authorized_keys:
      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCJcKHgH4tZN1XjGda61Bwxgq+kqrsblBy/H+n6/h107YRRYRpOi3UeG6u5ibS1+dAZKPr2lF9JWUAn/zqbFDfTUR7p05b+XwJ0LkB+AafL1vM6Spp8NTqU6QqXpXm8309lP3IlD6T5w+sJlmm5ixpOnv711y1zVnUBvA492O/dqG/gt7xNEMMxVzB/5Lw0bxQz1AEWPAIol0WeLQKfN8sSd/jerOVcHKabt9pk3BdqwJWx0YRDDfICPFKw43mcfzFhytGtkH87nMnT61jA4/ZFSzPiFJYueabkBIC9tEzuCm0fJWaXe+vL0oaIurohtwdIb5nU5diQuNYzjeD2PXIH ssh_pwauth: false
disable_root: false
package_update: true  
packages:
  - apache2
  - adminer
  - curl
  - wget
  - php
  - libapache2-mod-php
  - php-mysqli
write_files:
  - content: |
      <?php phpinfo(); ?>
    path: /var/www/html/info.php
    permissions: '0644'
write_files:
- content: |
    <?php
    $ihrname = "Mael";
    ?>
      <html>
      <head>
      <title><?php echo $ihrname; ?></title>
      </head>
      <body>
      <h1>Merjungfrau.</h1>
      <br/>
      <img src="https://malskn04bucketv1.s3.amazonaws.com/neom-0vpBglNUp_s-unsplash.jpg" />
      </body>
      </html>
    ?>
  path: /var/www/html/image.php
  permissions: '0644'
runcmd:
  - sudo systemctl restart apache2




Hot Speicher der sofort verfügbar ist
Warm Wird nicht so heufig wie hot verwendet muss trozdem schnell verfügbar sein
Cold wird selten oder nie benötigt zugriffszeit keine priorität

![Bild1](./25.png)

172.31.48.230/16
172.31.48.231/16
## KN05

![Bild1](./KN051.png)
![Bild1](./KN052.png)
![Bild1](./KN053.png)
![Bild1](./KN054.png)
![Bild1](./KN055.png)
![Bild1](./KN056.png)
![Bild1](./KN057.png)
![Bild1](./KN058.png)
![Bild1](./KN059.png)

Cloud init habe ich nicht mehr da ich diese KN auf meinem PC gemacht habe jedoch habe ich ja alle beweis Screenshots.

## KN06

### Was ist ein reverse Proxy

Ein reverse Proxy ist ein Server der vor Webservern installiert ist.Er leitet Anfragen von Clients an Webserver weiter. Reverse Proxys werden meist implementiert um die Sicherheit Pervormance und Zuverlässigkeit zu verbessern.

Das erweitern der Disk geht bei laufendem Betrieb
Den instance Typ zu ändern geht nicht bei laufendem Betrieb
![Bild1](./KN061.png)
![Bild1](./KN062.png)
![Bild1](./KN063.png)
![Bild1](./KN064.png)
![Bild1](./KN065.png)
![Bild1](./KN066.png)

### C
![Bild1](./KN067.png)


![Bild1](./KN068.png)

## KN07
![Bild1](./KN071.png)
![Bild1](./KN072.png)

Ich habe immer das gewählt das zu den Anforderungen passt und dort wo keine forgaben waren haben ich Annahmen getroffen um das beste für den Kunden zu erhalten

![Bild1](./KN073.png)

Wie auch oben schon gesagt habe ich alles so gut wie möglich gemacht das es am besten den Anforderungen des Kunden ensprechen wird.
![Bild1](./KN074.png)
![Bild1](./KN075.png)

SalesForce ist teurer als Zoho. Wen man bei SalesForce alles Zusammenrechnet Zahlt man im Monat 2´640 euro im Monat. 

###
SaaS, IaaS oder Paas

Vorteile SaaS
Sofort einsetzbarkeit
Skalierbar
Kostenersparnis

Nachteile
Begrenzte Anpassung
Datensicherheit

Vorteile IaaS

Flexibilität
Kontrolle
Skalierbarkeit

Nachteile
Anpassungsprobleme
Erfordert Schulungen

Vorteile PaaS
Entwicklungsplatform
Zeitersparnis

Nachteile
Eingeschränkte Individualisierung
Abhängikeit vom Anbieter



Die verschiedenen angebote unterscheiden sich sehr vom Preis jedoch auch bon der Dienstleistung

Welches ist das Billigste

Wenn man die Betriebskosten anschaut ist AWS das günstigste mit 874.32 USD pro Jahr


Heroku ist das Teuerste der Cloud lösungen. jedoch bietet es mehr möglichkeiten als die anderen. heroku ist sehr einfach hat einen schnellen start. Es bietet Automatisierungs möglichkeiten.

## KN08

![Bild1](./KN081.png)
![Bild1](./KN082.png)
![Bild1](./KN083.png)
![Bild1](./KN084.png)
![Bild1](./KN085.png)

