# EndeavourOS jak opravit nefunkční WiFi po instalaci na MacBook Pro 2015

Někteří z vás uvažují na starším MacBooku přejít na Linux. Jedna ze skvělých distribucí je [EndeavourOS](https://endeavouros.com/) vycházející z [Arch Linuxu](https://archlinux.org/).

Bohužel se vám může stát, že po instalaci vám nepůjde WiFI, ale to se dá naštěstí velmi dobře opravit.

Tuto  distribuci je možné nainstalovat pomocí live image offline což je výhoda, že nefunkční WiFi se bude řešit až po instalaci.

Nejprve připojíme přes kabel k Macbooku mobilní telefon který je připojený k WiFi . Pokud máte neomezené data nemusíte být na WiFi.

Na telefonu po připojení potvrdíte, že důvěřujete tomuto zařízení a MacBook se připojí k internetu.

V aplikacích najdeme aplikaci Welcome a klikneme na Update Mirrors.

Pak dáme Update System.

Až se systém aktualizuje přejdeme na samotnou instalaci ovladačů.

Zapneme aplikaci Terminal (Console).

A do ní zadáme:
```
pacman -S linux-headers
pacman -S broadcom-wl-dkms
pacman -S dkms
```
Tím jsme stáhli ovladače.

Dále do terminálu zadáme:
```
pacman -S broadcom-wl
```
Pokračujeme dál a zadáme:
```
pacman -Qs broadcom
```
Tento příkaz by nám měl už zobrazit WiFi v MacBooku.

Pak restartujte MacBook a WiFi by měla jet.

 

 

Návod nezaručuje stoprocentní funkčnost, ale vždy pomohl.

Vše co děláte, děláte na vlastní nebezpečí.  V  případě problému lukan.cz neručí za vzniklé škody a nelze po něm vymáhat náhradu.

Vždy než něco potvrdíte přečtěte si co vám systém píše nebo log.
