# 🐧 Jak v AlmaLinux 9 a dalších distribucích nainstalovat soubory tar.gz

![](https://lukan.cz/wp-content/uploads/2024/09/alma-linuxlinxdistribucion.png)

AlmaLinux 9, je velmi stabilní a bezpečný operační systém. To může mít nevýhodu v tom že balíčky v jeho repozitářích mohou být starší. Ale můžete si nainstalovat aktuální aplikaci bez použití Snap nebo Flatpack za pomocí souborů tar.gz.

My si tento způsob předvedeme na aplikaci [PhpStorm](https://www.jetbrains.com/phpstorm/) od [JetBrains](https://www.jetbrains.com/).

* Ze stránek JetBrains si stáhnete balíček [PhpStorm tar.gz](https://www.jetbrains.com/phpstorm/download/#section=linux) pro linux

* cd Downloads – v terminálu se přesuneme do složky kde máme stažený PHPStorm

* ls -lh – zkontrolujeme si název PhpStorm

* tar -xvf PhpStorm-2024.2.1.tar.gz – rozbalíme soubor s aplikací
    
* cd PhpStorm-221.5591.58/bin/ – přesuneme se do složky kde jsme rozbalily PHPStorm, číslo verze zjistíte v terminálu pod příkazem v prvním řádku kde jsme rozbalily soubor
    
* ./phpstorm.sh – spustíme PhpStorm

