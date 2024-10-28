# 🐧 AlmaLinux 9 – SELinux jak ho vypnu.

![](https://lukan.cz/wp-content/uploads/2024/09/AlmaLinuxlogo-3740426552-1536x864.png)

SELinux (Security-Enhanced Linux) je bezpečnostní modul pro jádro Linuxu, který poskytuje robustní řízení přístupu na úrovni jádra. Zapnutí SELinuxu může zvýšit bezpečnost systému tím, že omezuje, co mohou jednotlivé procesy dělat, a tím snižuje riziko útoků a šíření malwaru.

Pokud používáte Linux jen jako desktopový systém, rozhodnutí o zapnutí SELinuxu závisí na několika faktorech:

1. **Bezpečnost**: Pokud je pro vás prioritou bezpečnost, pak zapnutí SELinuxu může být dobrým krokem. SELinux může pomoci chránit vaše soubory a procesy před neoprávněným přístupem.
    
2. **Kompatibilita**: Některé aplikace mohou mít problémy s SELinuxem, zejména pokud nejsou správně nakonfigurovány. Pokud používáte software, který není kompatibilní s SELinuxem, můžete narazit na problémy.
    
3. **Správa**: SELinux může být náročný na správu, zejména pokud nejsou nastaveny správné politiky. Pokud nechcete nebo nemůžete věnovat čas správě SELinuxu, může být lepší ho vypnout.
    
4. **Výkon**: V některých případech může SELinux mírně ovlivnit výkon systému, ale většinou je tento vliv minimální.

Pokud se rozhodnete SELinux vypnout, můžete to udělat editací souboru /etc/selinux/config a nastavením SELINUX=disabled. Poté restartujte systém.
```
sudo nano /etc/selinux/config
```
Změňte řádek:
```
SELINUX=enforcing
```
na:
```
SELINUX=disabled
```

Pokud se rozhodnete SELinux ponechat zapnutý, doporučuji seznámit se s jeho konfigurací a správou, abyste mohli maximálně využít jeho bezpečnostních výhod.
