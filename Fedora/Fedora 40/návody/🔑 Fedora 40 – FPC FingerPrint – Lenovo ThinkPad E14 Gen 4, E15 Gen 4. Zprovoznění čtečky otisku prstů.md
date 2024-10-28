## 🔑 Fedora 40 – FPC FingerPrint – Lenovo ThinkPad E14 Gen 4, E15 Gen 4. Zprovoznění čtečky otisku prstů. ## 

Čtečka otisků prstů je skvělá věc, pomůže vám s přihlášením do systému v terminálu za každým sudo nemusíte vypisovat heslo. Pokud vlastníte **Lenovo ThinkPad / Thinkbook E14 Gen 4 nebo E15 Gen 4** možná jste podle této [tabulky](https://fprint.freedesktop.org/supported-devices.html) zjistili, že čtečka otisku prstů **Fingerprint reader FPC 10a5:9800** není v linuxu podporována a tím další vaše pokusy o zprovoznění skončily.

Ale na stránce [Lenovo](https://pcsupport.lenovo.com/us/en/products/laptops-and-netbooks/thinkpad-edge-laptops/thinkpad-e14-gen-4-type-21eb-and-21ec/downloads/ds563477-fpc-fingerprint-driver-for-ubuntu-2004-ubuntu-2204-thinkpad-e14-gen-4-e15-gen-4?category=Fingerprint%20Reader) existuje ovladač, který bohužel nefunguje. Nicméně po menší úpravě čtečku otisků prstů rozjedeme.

Celý tento proces jsem dělal na [Fedora 40 Workstation](https://fedoraproject.org/workstation/download) s Gnome 46.6. Tento postup by měl jít na všech distribucích rodiny RHEL a i na ostatních desktopových prostředích než jen gnome. Po úpravě skriptu by měl fungovat také v Ubuntu. Zaručit to ovšem nemohu, protože to nemám jinde než nanFedoře 40 s Gnome 40.6. A teď k samotné instalaci a úpravě scriptu.

Při instalaci postupuj opatrně, vše si zkontroluj, případně si pročti dokumentaci i scriptu nebo na stránce Lenovo ať si nezpůsobíš potíže. V žádném případě neručím za vzniklé škody.

1. Ověříme si, že vážně máte **Fingerprint reader FPC 10a5:9800**  tímto příkazem:
```
lsubs
```
Pokud to sedí, pokračujeme dále.

příkaz lsusb

![](https://lukan.cz/wp-content/uploads/2024/10/Snimek-obrazovky-z-2024-10-22-21-11-38.png)

2. Pokud nemáte nainstalujte balíček **fprintd**:
```
sudo dnf install fprintd
```
3. Stáhneme si ovladač z webu Lenovo a to **FPC FingerPrint Driver r1slm02w.zip** a uložíme si ho třeba do složky **/home/"user"/Stažené/**.

4. Soubor zip rozbalíme a začneme upravovat scripty.

5. První půjdeme do složky: **/home/"user"/Stažené/r1slm02w/FPC_driver_linux_27.26.23.39/install_fpc**  a tam v jakémkoliv textovém editoru otevřeme
install.sh  přepíšeme vložením původního kódu a uložíme do něj tento kód:
```
if grep -qE 'ID=fedora' /etc/os-release; then
  sudo cp ./libfpcbep.so /usr/lib64/
  sudo chmod +x /usr/lib64/libfpcbep.so
else
  sudo cp ./libfpcbep.so /usr/lib/x86_64-linux-gnu/
fi;
```
6. Půjdeme do složky: **/home/“user“/Stažené/r1slm02w/** otevřeme v ní terminál a do něj zadáme:
```
cd FPC_driver_linux_27.26.23.39/install_fpc
chmod +x install.sh
sudo ./install.sh
```
7. Teď půjdeme do této složky: **/home/"user"/Stažené/r1slm02w/FPC_driver_linux_libfprint/install_libfprint** a tam v jakémkoliv textovém editoru otevřeme
install.sh  přepíšeme vložením původního kódu a uložíme do něj tento kód:
```
if grep -qE 'ID=fedora' /etc/os-release; then
  sudo dnf -y install libfprint fprintd fprintd-pam 'dnf-command(versionlock)'
  sudo dnf versionlock libfprint
  sudo cp -r lib/* /usr/lib/
  sudo cp usr/lib/x86_64-linux-gnu/* /usr/lib64/
  sudo chmod +x /usr/lib64/libfprint-2*
else
  sudo cp -r lib/* /lib/
  sudo cp -r usr/* /usr/
  sudo mkdir -p /var/log/fpc
  #avoid libfprint being modified under apt upgrading
  echo "libfprint-2-2 hold" | sudo dpkg --set-selections
  sudo chmod 755 /usr/lib/x86_64-linux-gnu/libfprint-2.so.2.0.0
fi
echo "Installation completed successfully. You must reboot your system."
```
8. Půjdeme do složky: **/home/“user“/Stažené/r1slm02w/** otevřeme v ní terminál a do něj zadáme:
```
cd FPC_driver_linux_libfprint/install_libfprint
chmod +x install.sh
sudo ./install.sh
```
Měli byste restartovat systém, ale u mně to nebylo potřeba. Vše prošlo i bez restartu.

9. Teď v Gnome půjdeme do  **Nastavení -> Uživatelé -> Přihlášení otiskem prstů** dáme Zapnout a postupujeme dle návodu skenováním prstů.

Snímaní prstů v Gnome

![](https://lukan.cz/wp-content/uploads/2024/10/Snimek-obrazovky-z-2024-10-22-21-53-39.png)

V ostatních prostředích bude postup velmi podobný nebo by měl jít tento příkaz:
```
sudo authselect enable-feature with-fingerprint
```
,ale nemám ho odzkoušený.