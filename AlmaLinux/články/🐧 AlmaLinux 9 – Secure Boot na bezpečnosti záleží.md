# 🐧 AlmaLinux 9 – Secure Boot na bezpečnosti záleží

![](https://lukan.cz/wp-content/uploads/2024/09/AlmaLinuxlogo-3740426552-1536x864.png)

Na bezpečnosti záleží a vývojáři AlmaLinux 9 jsou si toho vědomi. Pokud Váš computer podporuje Secure Boot, AlmaLinux 9 bude skvělá volba jak pro Váš Desktop taky Vaši firmu či Server.

Proč používat Secure Boot se dozvíte v přepisu článku z blogu [AlmaLinux](https://almalinux.org/blog/).

## O zabezpečeném spouštění

V případě, že ještě nejste obeznámeni, [Secure Boot](https://en.wikipedia.org/wiki/UEFI#Secure_Boot) je to bezpečnostní funkce vytvořená tak, aby zajistila, že během procesu spouštění může běžet pouze důvěryhodný software. Tato funkce pomáhá zabránit načtení škodlivého softwaru nebo neoprávněného kódu při spouštění. Secure Boot ověřuje podpis operačního systému během spouštění a poskytuje další ochranu proti malwaru a neoprávněnému přístupu.

AlmaLinux používá shim bootloader k podpoře Secure Boot – open-source bootloader, který vytváří důvěru mezi firmwarem UEFI a operačním systémem během procesu spouštění. Shim zajišťuje, že proces spouštění zůstane bezpečný, a to ověřením podpisu zavaděče před načtením operačního systému.

AlmaLinux shim je oficiálně podepsán společností Microsoft a aktuálně důvěřuje 2 certifikátům. Další podrobnosti o důvěryhodných certifikátech a spoustě dalších funkcí zabezpečení AlmaLinuxu najdete na [stránce Zabezpečení](https://almalinux.org/security/).

## Kontrola stavu zabezpečeného spouštění

Důrazně doporučujeme povolit Secure Boot na vašem systému AlmaLinux.

Poznámka: Před provedením níže uvedených kroků se ujistěte, že váš počítač podporuje UEFI Secure Boot.

Pomocí nástroje mokutil můžete zkontrolovat, zda je ve vašem systému již povoleno Secure Boot. Spusťte v terminálu následující příkaz:
```
mokutil --sb-state
```
Výstup zobrazí, zda je zabezpečené spouštění povoleno nebo zakázáno.

Chcete-li na svém počítači povolit zabezpečené spouštění, zadejte během spouštění nastavení systému BIOS/UEFI (obvykle se to provádí stisknutím klávesy jako F2, F10, F12 nebo Delete během spouštění). Poté vyhledejte možnost Secure Boot a povolte ji. Uložte změny a restartujte systém, aby bylo zabezpečené spouštění aktivní.

Pokud používáte AlmaLinux na virtuálním počítači, doporučujeme povolit Secure Boot v nastavení při vytváření. Kroky k tomu jsou popsány v několika různých průvodcích, jako je [průvodce Fedora](https://docs.fedoraproject.org/en-US/quick-docs/uefi-with-qemu/) a průvodce [Virtuzzo](https://docs.virtuozzo.com/virtuozzo_hybrid_server_7_users_guide/managing-virtual-machines-and-containers/performing-virtual-machine-specific-operations.html#enabling-secure-boot-for-virtual-machines).

## Další funkce zabezpečení

Jak jsem již zmínil dříve, pevně věříme v zabezpečení a pracovali jsme na poskytování funkcí i průvodců, které můžete potřebovat k vytvoření bezpečného prostředí. Podívejte se na náš obsáhlý seznam [bezpečnostních opatření](https://almalinux.org/security/), která ještě více zvýší zabezpečení vašeho systému AlmaLinux.
