## 🐧 Fedora 40 – jak nainstalovat WebStorm bez Snap či Flapak ##

![](https://lukan.cz/wp-content/uploads/2024/10/jetbrains_featured.webp)



[JetBrains](https://www.jetbrains.com/) uvolnilo zdarma pro nekomerční použití IDE [WebStorm](https://www.jetbrains.com/webstorm/) a [Rider](https://www.jetbrains.com/rider/). Bohužel je nenajdete v repozitářích Fedory 40. Pokud nechcete používat [Flatpaky](https://flathub.org/) nebo [Snapy](https://snapcraft.io/) tak možnost jak aplikace nainstalovat z balíčku tar.gz.

Provedeme instalaci WebStorma.

Stáhneme si WebStorm aktuální verzi ze stránek [JetBrain s příponou tar.gz.](https://www.jetbrains.com/webstorm/download/#section=linux) Já si na to udělal složku APP.

Otevřeme terminál ve složce kde máme WebStorm a zkontrolujeme verzi WebStormu:
```
ls -lh 
```
Zadáme do terminálu tar -xvf puls název alikace a aplikaci rozbalíme:
```
tar -xvf WebStorm-2024.2.4.tar.gz
```
Vytvořte soubor s příponou .desktop v ~/.local/share/applications/ (pro uživatelské aplikace). Například, soubor může mít název myapp.desktop, ale my použijeme název webstorm.desktop. Také soubor rovnou upravíme v editoru nano a uložíme soubor.

   -> Jak procovat s nano zjistíte v článku [Nano – terminálový textový editor](https://lukan.cz/2024/10/%f0%9f%92%bb-nano-terminalovy-textovy-editor/)
```
[Desktop Entry]
Name=WebStorm
Comment=Description of Webstorm
Exec=/home/váš user name/APP/WebStorm-242.23726.96/bin/webstorm
Icon=/home/váš user name/APP/WebStorm-242.23726.96/bin/webstorm.png
Terminal=false
Type=Application
Categories=Utility;Application;
```
**Name**: Název aplikace, který se zobrazí v nabídce.

**Comment**: Popis aplikace.

**Exec**: Cesta k spustitelnému souboru aplikace.

**Icon**: Cesta k ikoně aplikace (můžete použít absolutní cestu nebo umístit ikonu do standardního adresáře ikon).

**Terminal**: true, pokud aplikace potřebuje běžet v terminálu, jinak false.

**Type**: Typ souboru, obvykle Application.

**Categories**: Kategorie, do kterých aplikace patří (můžete přidat více kategorií oddělených středníkem).

Udělte souboru spustitelné práva: Zajistěte, aby soubor .desktop měl spustitelné práva.
```
chmod +x ~/.local/share/applications/webstorm.desktop
```
A to je vše aplikaci uvidíme v nabídce aplikací a můžeme si ji třeba přidat do lišty.

Tento návod by měl fungovat i v jiných Linuxových Distribucích.
