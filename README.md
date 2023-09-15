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

