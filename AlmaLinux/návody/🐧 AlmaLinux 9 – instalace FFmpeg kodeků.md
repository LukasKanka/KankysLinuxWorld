# 🐧 AlmaLinux 9 – instalace FFmpeg kodeků

![](https://lukan.cz/wp-content/uploads/2024/09/AlmaLinuxlogo-3740426552-1536x864.png)

Po instalaci [AlmaLinux](https://almalinux.org/) možná narazíte na problém že nepřehrajete videa. Důvod je jednoduchý, protože vám nejspíš chybí [FFmpeg kodeky](https://ffmpeg.org/). V tomto článku si kodeky nainstalujeme, tento způsob by měl fungovat ve všech distribucích z rodiny RHEL.

 

   1. Do vašeho terminálu vložíme tento kód a zkontrolujeme aktualizace:
    sudo dnf update
   2. Pokud nemáte, je potřeba do systému přidat repozitaáře RPM Fusio:
   ```
    sudo dnf install https://download1.rpmfusion.org/free/el/rpmfusion-free-release-9.noarch.rpm
    sudo dnf install https://download1.rpmfusion.org/nonfree/el/rpmfusion-nonfree-release-9.noarch.rpm
    ```
    Více o repozitářých [RPM Fusion](https://lukan.cz/2024/09/almalinux-9-co-jsou-repozitare-fedora-fusion-a-jak-je-pridat-do-almalinux/).
  3.  A nainstalujeme kodek FFmpeg tímto příkazem:
  ```
    sudo dnf install ffmpeg ffmpeg-devel
    ```
   4. Tímto příkazem ověříme že instalace proběhla v pořádku:
   ```
    ffmpeg -version
    ```