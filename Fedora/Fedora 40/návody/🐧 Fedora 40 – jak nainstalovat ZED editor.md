## 🐧 Fedora 40 – jak nainstalovat ZED editor

![](https://lukan.cz/wp-content/uploads/2024/10/zedkiller.jpg)


[Zed](https://zed.dev/) je vysoce výkonný, „multiplayer“, bezplatný a open source kódový editor napsaný v [Rust](https://www.rust-lang.org/) a vyvinutý na GitHub. Byl vytvořen stejnými autory jako textový editor Atom, a přestože má funkce IDE, je velmi responzivní. V tomto tutoriálu se dozvídáme, jak nainstalovat Zed na Fedoru a ostatní distribuce z rodiny [RHEL](https://cs.wikipedia.org/wiki/Red_Hat_Enterprise_Linux).

Všechny distribuce nemají k dispozici balíček Zed. V některých případech však může být editor instalován z úložiště softwaru třetích stran. Vždy bychom si měli být vědomi toho, že balíčky hostované v těchto relacích nejsou oficiální. Balíček třetí strany Zed, instalovatelný na **Fedoru** například najdete v repozitáři **„Terra“**. Chcete-li přidat jako zdroj softwaru do našeho systému, můžeme použít následující příkaz:
```
$ sudo dnf install --repofrompath 'terra,https://repos.fyralabs.com/terra$releasever' --setopt='terra.gpgkey=https://repos.fyralabs.com/terra$releasever/key.asc' terra-release
```
Budeme vyzváni k instalaci terra-release balíčků a potvrdíme důvěřuj klíči GPG úložiště. Jakmile je úložiště k dispozici, můžeme nainstalovat Zed spuštěním:
```
$ sudo dnf install zed
```
