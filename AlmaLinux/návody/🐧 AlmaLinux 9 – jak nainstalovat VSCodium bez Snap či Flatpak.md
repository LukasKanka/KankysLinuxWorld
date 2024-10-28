# 🐧 AlmaLinux 9 – jak nainstalovat VSCodium bez Snap či Flatpak

![](../img/AlmaLinuxlogo.png)

Na instalovat [VSCodium](https://vscodium.com/) do [AlmaLinux 9](https://almalinux.org/) bez použití [Snap](https://snapcraft.io/) nebo [Flatpak](https://flathub.org/) je velmi jednoduché, tento návod platí jak na AlmaLinux 9 tak by měl fungovat na distribucích založených na RHEL.

VSCodium vyniká jako pozoruhodná alternativa k populárnímu editoru [Visual Studio Code](https://code.visualstudio.com/). Nabízí podobný zážitek bez telemetrie a sledovacích funkcí přítomných v posledně uvedené. Je přizpůsoben vývojářům, kteří upřednostňují soukromí a chtějí open-source řešení, které neochrání funkčnost.

Zde je přehled toho, co dělá VSCodium vynikající volbou pro vývojáře:

* Otevřená povaha, zajištění transparentnosti a komunitně řízených vylepšení.
* Absence telemetrie poskytuje vývojové prostředí zaměřené na soukromí.
* Kompatibilita s množstvím programovacích jazyků a rámců.
* Rozsáhlá knihovna rozšíření pro přizpůsobení a zlepšení vývojového zážitku.
* Intuitivní uživatelské rozhraní, které se stará o začínající i zkušené vývojáře.
* Efektivní výkon, optimalizace času vývoje a využití zdrojů.
* Silná podpora komunity a pravidelné aktualizace pro lepší funkčnost.
* Kompatibilita napříč platformami, která umožňuje konzistentní zkušenosti napříč různými operačními systémy.

Samostatná instalace je velmi jednoduchá:

1. Otevřeme terminál do něj vložíme tento příkaz čím zkontrolujeme aktualizace a repozitáře:
```
sudo dnf upgrade --refresh
```
2. Naimportujeme si  repozitář s VSCodium:
```
sudo rpmkeys --import https://gitlab.com/paulcarroty/vscodium-deb-rpm-repo/-/raw/master/pub.gpg
```
3. Dále importujte úložiště provedením následujícího příkazu:
```
printf "[gitlab.com_paulcarroty_vscodium_repo]\nname=download.vscodium.com\nbaseurl=https://download.vscodium.com/rpms/\nenabled=1\ngpgcheck=1\nrepo_gpgcheck=1\ngpgkey=https://gitlab.com/paulcarroty/vscodium-deb-rpm-repo/-/raw/master/pub.gpg\nmetadata_expire=1h" | sudo tee -a /etc/yum.repos.d/vscodium.repo
```
Měl by se nám zobrazit tento výstup:
```
[gitlab.com_paulcarroty_vscodium_repo]
name=download.vscodium.com
baseurl=https://download.vscodium.com/rpms/
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://gitlab.com/paulcarroty/vscodium-deb-rpm-repo/-/raw/master/pub.gpg
metadata_expire=1h
```
4. S importovaným úložištěm můžete nyní pokračovat v instalaci VSCodium. Spusťte ve svém terminálu následující příkaz:
```
sudo dnf install codium
```
Pro uživatele, kteří se zajímají o sestavení insider založené na sestavení Visual Studio Code, spusťte následující příkaz:
```
sudo dnf install codium-insiders
```
**Poznámka**: Stabilní i insider sestavení lze nainstalovat současně, protože sdílejí samostatné instalace.

### VSCodium odstraníte:
```
sudo dnf remove codium
```
Insider verzi:
```
sudo dnf remove codium-insiders
```
Pokud se rozhodnete VSCodium v ​​budoucnu nepoužívat a chcete odstranit úložiště ze systému, spusťte následující příkaz:
````
sudo rm /etc/yum.repos.d/vscodium*
````