# 🐧 AlmaLinux 9 – instalace Postmana + vytvoření ikony pro spuštění

![](../img/AlmaLinuxlogo.png)

Pokud si chcete do AlmaLinux 9 nainstalovat Postman a vytvořit spouštěcí ikonu postup je následovný. Jen připomýnám tento postup by měl být vhodný ve všech distribucích založených na RHEL.

1. Nejprve je třeba aktualizovat index místních balíčků s následujícím příkazem:
```
sudo dnf update -y
```
2. Stáhněte si ze serveru Postmana:
```
sudo wget https://dl.pstmn.io/download/latest/linux64
```
3. Ex traktujte  stažený soubor:
```
sudo tar -xvf linux64 -C /usr/bin
```
4. Zde musíte tento soubor přidat do systémové cesty. Chcete-li to provést, spusťte následující příkaz:
```
echo 'export PATH="$PATH:/usr/bin/Postman"' >> ~/.bashrc
```
5. Spusťte Postmana:
```
postman
```
Pokud chcete Postman přidat do nabídky aplikací či si vytvořit ikonu na plochu, uděláte to tímto způsobem. Tento způsob jsem ozkoušel na Gnome 40.10.

Pomocí nano vytvořte soubor, který později naplníme. Zatím v terminálu zadejte tento príkaz:
```
sudo nano /usr/share/applications/Postman.desktop
```
Do souboru vložte, zapište a uložte tento text:
```
[Desktop Entry]
Name=Postman API Tool
GenericName=Postman
Comment=Testing API
Exec=/usr/bin/Postman/Postman
Terminal=false
X-MultipleArgs=false
Type=Application
Icon=/usr/bin/Postman/app/resources/app/assets/icon.png
StartupWMClass=Postman
StartupNotify=true
```
Tímto způsobem jsme si vytvořily spouštěcí ikonu do nabídky aplikací.

Pokud chcete ikonu na plochu vykopírujte si ji na plochu z této pozice:
```
cp /usr/share/applications/Postman.desktop ~/Desktop/
```
Pokud budete chtít postman odinstalujete tímto způsobem:
```
sudo rm -r /usr/bin/Postman
sudo rm -r /usr/share/applications/Postman.desktop
sudo rm -r ~/Desktop/Postman.desktop 
```