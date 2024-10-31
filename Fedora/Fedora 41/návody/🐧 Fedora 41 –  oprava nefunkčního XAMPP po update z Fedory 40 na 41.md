# 🐧 Fedora 41 – oprava nefunkčního XAMPP po update z Fedory 40 na Fedoru 41

Pokud jste přešli z Fedory 40 na [Fedoru 41](https://fedoraproject.org/) pomocí update bez čisté instalace, možná vám přestal pomocí příkazu **sudo /opt/lampp/lampp start** se spouštět [XAMPP](https://www.apachefriends.org/download.html).

Náprava je poměrně jednoduchá, do terminálu stačí dát tyto dva příkazy:
```
sudo dnf -y update && sudo dnf -y install libnsl
```
```
sudo dnf install -y libxcrypt-compat
```
a už by vám měl zas fungovat příkaz:
```
sudo /opt/lampp/lampp start
```
