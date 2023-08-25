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

#### 1.Infrastructure as a Service
Bei diesem Modell werden grundlegende Komponenten bereitgestellt wie Maschienen Speicher Netzwerke etc. Dort kann man dann seine eigenen Betriebsysteme und anwendungen installieren.
#### Platform as a service
Hier kann man sich voll auf die entwicklung des Services oder der Anwendung. Das heisst Aspekte wie betriebsystem oder Netzwerkinfrastruktur wird vom Anbieter übernomen.
#### Software as Service
Bei diesem Modell muss sich um nichts gekümmert werden es wird netzwerk Hardware infrastruktur einfach alles bereitgestellt und man kann einfach die anwendungen verwenden.