# Jak nainstalovat Firefox do Ubuntu bez Snapu

![](../img/liska-co-spi-ve-stylu-comix.jpg)

Ne každý chce využívat balíčkovací systém Snap v Ubuntu.

Teď si ukážeme jak nainstalovat Firefox do distribuce Ubuntu bez použití Snapu ale, jen přes terminál kam si přidáme repositář s Firefoxem.

První co uděláme přidáme si repositář s Firefoxem. Otevřeme terminál a zadáme do něj:
```
sudo add-apt-repository ppa:mozillateam/ppa 
```
Dále změňte prioritu balíčku Firefox tak, aby byla upřednostněna verze PPA/deb/apt Firefoxu. Vložením do terminálu:

(vložte tento celý text)

```
echo ‚ 
Package: * 
Pin: release o=LP-PPA-mozillateam 
Pin-Priority: 1001 
‚ | sudo tee /etc/apt/preferences.d/mozilla-firefox 
```

Pokud budete chtít, aby se budoucí aktualizace Firefoxu instalovaly automaticky vložte do terminálu:

```
echo ‚Unattended-Upgrade::Allowed-Origins:: „LP-PPA-mozillateam:${distro_codename}“;‘ | sudo tee /etc/apt/apt.conf.d/51unattended-upgrades-firefox 
```

A posledním příkazem nainstalujeme Firefox:

```
sudo apt install Firefox 
```