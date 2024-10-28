# 🐧 AlmaLinux 9 – co jsou repozitáře Fedora Fusion a jak je přidat do AlmaLinux

![](https://lukan.cz/wp-content/uploads/2024/09/AlmaLinuxlogo-3740426552-1536x864.png)



Fedora Fusion je projekt, který rozšiřuje ekosystém Fedora Linuxu tím, že poskytuje dodatečné repozitáře s balíčky, které nejsou zahrnuty v hlavních repozitářích Fedora. Tyto repozitáře obsahují software, který může být užitečný pro uživatele Fedora, ale který nemůže být zahrnut do hlavních repozitářů z různých důvodů, jako jsou licenční omezení nebo politiky Fedora.

Repozitáře Fedora Fusion jsou navrženy tak, aby byly snadno přístupné a použitelné pro uživatele Fedora. Mezi software, který může být zahrnut v těchto repozitářích, patří například:

1.   **Proprietární ovladače**: Ovladače pro hardwarové komponenty, které nejsou open source.
2.  **Multimediální kodeky**: Kodeky pro přehrávání multimediálních souborů, které mohou být z licenčních důvodů problematické.
3.  **Další aplikace**: Různé aplikace, které nejsou zahrnuty v hlavních repozitářích Fedora, ale které mohou být užitečné pro uživatele.

Použití repozitářů Fedora Fusion může pomoci uživatelům Fedora získat přístup k širšímu spektru software, který by jinak nemohli snadno instalovat. Tyto repozitáře jsou spravovány a udržovány komunitou Fedora a jsou k dispozici pro všechny uživatele Fedora, kteří chtějí rozšířit funkčnost svého systému.

## Instalace EPEL a RPM Fusion

Tato příručka popisuje, jak nainstalovat Extra balíčky pro Enterprise Linux (EPEL) a RPM Fusion , dvě softwarová úložiště, která obsahují software, který není součástí AlmaLinuxu (jako kodeky).

**VAROVÁNÍ**

Tato softwarová úložiště třetích stran nemusí být podporována [projektem Elevate](https://wiki.almalinux.org/elevate/) společnosti AlmaLinux .

## Instalace Fusion Repozitářů:

 
### Krok 1: Nainstalujte EPEL.

Instalace EPEL je vyžadována pro RPM Fusion.

Postupujte podle zde popsaných [zde pro instalaci EPEL](https://lukan.cz/2024/09/almalinux-9-co-jsou-epel-repozitare-a-jak-je-doinstalovat/)

### Krok 2: Nainstalujte (a ověřte) klíče RPM Fusion GPG

Stažení a ověření klíčů GPG RPM Fusion zajistí, že balíčky, které nainstalujete, pocházejí z RPM Fusion a nebyly změněny (náhodou nebo se zlým úmyslem).

1. Stáhněte si balíček distribution-gpg-keys .
```
$ sudo dnf install distribution-gpg-keys
```
Pokud se zobrazí výzva k importu klíče GPG, porovnejte klíč, který jste obdrželi, s [podpisovými klíči balíků Fedory](https://fedoraproject.org/security/)

[otevře nové okno](https://fedoraproject.org/security/) . Ujistěte se, že klíč na webové stránce je ve správné verzi EPEL, jak je popsána v uživatelském ID, a ujistěte se, že se otisky shodují.

2. Importujte klíče RPM Fusion pomocí rpmkeys
```
# RPM Fusion (free packages)
$ sudo rpmkeys --import /usr/share/distribution-gpg-keys/rpmfusion/RPM-GPG-KEY-rpmfusion-free-el-$(rpm -E %rhel)
# RPM Fusion (nonfree packages)
$ sudo rpmkeys --import /usr/share/distribution-gpg-keys/rpmfusion/RPM-GPG-KEY-rpmfusion-nonfree-el-$(rpm -E %rhel)
```

3. (Volitelné) Zkontrolujte, zda se GPG klíče shodují s klíči na stránce [RPM Fusion keys](https://rpmfusion.org/keys)

[(otevře nové okno)](https://rpmfusion.org/keys) . (Je v sekci označené „Aktuálně používané klíče“.) Pomocí níže uvedených příkazů zobrazte importované klíče a porovnejte je s klíčem v RPM Fusion.
```
# RPM Fusion (free packages)
$ gpg --show-keys --with-fingerprint /usr/share/distribution-gpg-keys/rpmfusion/RPM-GPG-KEY-rpmfusion-free-el-$(rpm -E %rhel)
# RPM Fusion (nonfree packages)
$ gpg --show-keys --with-fingerprint /usr/share/distribution-gpg-keys/rpmfusion/RPM-GPG-KEY-rpmfusion-nonfree-el-$(rpm -E %rhel)
```
### Krok 3: Nainstalujte RPM Fusion

Zadejte příkaz níže.
```
$ sudo dnf --setopt=localpkg_gpgcheck=1 install  https://mirrors.rpmfusion.org/free/el/rpmfusion-free-release-$(rpm -E %rhel).noarch.rpm https://mirrors.rpmfusion.org/nonfree/el/rpmfusion-nonfree-release-$(rpm -E %rhel).noarch.rpm
```

Pokud se instalace nezdaří, může to znamenat, že dříve importované klíče GPG neodpovídají podpisu repozitářů RPM Fusion. Pokud k tomu dojde, opakujte krok 2.3, abyste zjistili, zda máte správné klíče GPG.
