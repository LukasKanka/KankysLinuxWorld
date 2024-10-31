# Docker Desktop, Docker s vlastním Gui na Ubuntu 22.04 instalace

Pokud se vám nelíbí rozhraní Dockeru v Terminálu nebo vás od Dockeru Terminál odrazuje řešení je Docker Desktop.

Docker Desktop je ideální k použití na pc nebo notebooku ke kterému máte fyzicky přístup. Na vzdáleném pc nebo serveru je lepší použít Terminál nebo přístup k Dockeru přes webové rozhraní.

Docker Desktop se může použít i přes Remote Desktop.

Tento návod je primárně určen pro Ubuntu 22.04, ale měl by fungovat i v jiných distribucích založených na Ubuntu. Já osobně nyní používám Ubuntu Budgie 22.04 kde jsem tímto postupem Docker rozjel bez problému.

**Prvně si nainstalujeme Engine Docker na Ubuntu**

Pokud nemáte nainstalován Gnome-Terminal tak si ho nainstalujte (na stránkách Docker Desktop to zmiňují jako podmínku).

**Gnome-Terminál nainstalujeme tímto způsobem:**
```
sudo apt install gnome-terminal
```
**Pokud máte nainstalovanou starou verzi Dockeru můžete ji odinstalovat tímto Příkazem v terminálu:**
```
sudo apt-get remove docker docker-engine docker.io containerd runc
```
**Dále si Aktualizujte index balíčků a nainstalujte balíčky tak, aby umožňovaly použití repositář přes HTTPS:aptapt:**

První příkaz vložte tento:
```
sudo apt-get update
```
A pak tento:
```
sudo apt-get install \
ca-certificates \
curl \
gnupg \
lsb-release
```
**Přidejte oficiální GPG klíč Dockeru těmito příkazy:**
```
sudo mkdir -p /etc/apt/keyrings

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```
K nastavení úložiště použijte následující příkaz:
```
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
$(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
**Aktualizujte index balíčku: apt tímto příkazem:**
```
sudo apt-get update
```
**Nainstalujeme modul Docker, kontejner a Docker Compose tímto příkazem:**
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```
**Spuštěním image ověřte, zda je instalace modulu Docker úspěšná:**
```
sudo docker run hello-world
```
Tento příkaz stáhne testovací image a spustí ji v kontejneru. Když indikátor kontejneru se spustí, zobrazí potvrzovací zprávu.

Tímto máme první část za sebou a doinstalujeme **Docker Desktop**:

Stáhněte si Docker Desktop pro ubuntu zde:

[Install on Ubuntu | Docker Documentation](https://docs.docker.com/desktop/install/ubuntu/)

**Pokud máte starou verzi dockeru můžete ji doinstalovat tímto příkazem:**
```
sudo apt remove docker-desktop
```
**Nainstalujte balíček pomocí apt následujícím způsobem:**

První uděláme update:
```
sudo apt-get update
```
**Pak v terminálu pomocí cd běžte do složky kam jste si stáhli Docker Desktop, nejspíše to bude:**
```
cd Downloads/
```
Nebo
```
cd Stažené/
```
**Tam si pomocí příkazu ověříme, jestli jsme ve správné složce a necháme si vypsat všechny soubory, měli byste tam vidět toto docker-desktop–.deb.**

Obsah složky zobrazíte příkazem:
```
Ls
```
Pokud tam soubor vidíte nainstalujeme Docker Desktop.

**Použijeme k tomu tento příkaz, místo slova verze dopněte číslo vaší verze:**
```
sudo apt-get install ./docker-desktop-verze.deb
```
Pokud proběhla instalace můžete se podívat do programů a uvidíte ikonu Docker Desktopo kterou aplikaci spustíte.

Návod je podle oficiálního webu docker a najdete ho pod těmito odkazy:

Instalace Docker:

https://docs.docker.com/engine/install/ubuntu/

Instalace Docker Desktop:

https://docs.docker.com/desktop/install/ubuntu/
