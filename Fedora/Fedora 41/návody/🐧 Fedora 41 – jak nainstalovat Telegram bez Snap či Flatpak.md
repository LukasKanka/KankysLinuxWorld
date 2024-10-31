# 🐧 Fedora 41 – jak nainstalovat Telegram bez Snap či Flatpak

![](../img/telegram-app.jpg)

Telegram je rychlá, bezpečná a všestranná platforma pro zasílání zpráv, která nabízí řadu funkcí včetně šifrovaných zpráv, sdílení velkých souborů a cloudového úložiště. Díky podpoře skupin, kanálů, robotů a přizpůsobitelných témat není Telegram jen aplikací pro zasílání zpráv, ale komplexním komunikačním nástrojem vhodným pro osobní i profesionální použití. Díky dostupnosti napříč platformami je přístupný na různých zařízeních a zajišťuje bezproblémovou komunikaci napříč desktopy, mobilními a webovými platformami.

## Nainstalujte telegram přes RPM Fusion 

### Aktualizujte Fedoru před instalací telegramu 
```
sudo dnf upgrade --refresh
```

### Importujte RPM Fusion 
```
sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm
```
```
sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```
#### Více o importu RPM Fusion se dozvíte v článku [🐧 AlmaLinux 9 – co jsou repozitáře Fedora Fusion a jak je přidat do AlmaLinux](https://lukan.cz/2024/09/almalinux-9-co-jsou-repozitare-fedora-fusion-a-jak-je-pridat-do-almalinux/)

### Instalujte Telegram přes příkaz DNF
```
sudo dnf install telegram
```

### Odinstalace Telegramu
```
sudo dnf remove telegram
```

#### Případně můžeme odstranit i zdroje RPM Fusion
```
sudo dnf config-manager --set-disabled rpmfusion-free
```
```
sudo dnf config-manager --set-disabled rpmfusion-nonfree
```
Seznam naších repozitářů i instalaci balíčku zobrazíme 
```
dnf repolist
```