# 🐧 AlmaLinux 9 – co jsou EPEL repozitáře a jak je doinstalovat

![](.././img/AlmaLinuxlogo.png)

EPEL (Extra Packages for Enterprise Linux) jsou repozitáře, které poskytují dodatečné balíčky pro distribuce založené na Red Hat Enterprise Linux (RHEL), jako je AlmaLinux, CentOS, Rocky Linux a další. Tyto repozitáře jsou spravovány komunitou Fedora a jejich cílem je poskytnout uživatelům přístup k širšímu spektru software, který není zahrnut v základních repozitářích těchto distribucí.

EPEL repozitáře obsahují balíčky, které jsou obvykle dostupné v Fedora, ale nejsou zahrnuty v RHEL kvůli různým důvodům, jako jsou licenční omezení nebo politiky RHEL. Mezi software, který může být zahrnut v EPEL repozitářích, patří:

1. **Dodatečné aplikace**: Různé aplikace, které nejsou zahrnuty v základních repozitářích RHEL, ale které mohou být užitečné pro uživatele.
2. **Nástroje pro vývoj**: Dodatečné nástroje a knihovny pro vývojáře.
3. **Síťové služby**: Různé síťové služby a aplikace, které mohou být užitečné pro správce systémů.
4. **Multimediální aplikace**: Aplikace pro práci s multimediálními soubory.

Použití EPEL repozitářů může pomoci uživatelům AlmaLinux a dalších distribucí založených na RHEL získat přístup k širšímu spektru software, který by jinak nemohli snadno instalovat. Tyto repozitáře jsou spravovány a udržovány komunitou Fedora a jsou k dispozici pro všechny uživatele, kteří chtějí rozšířit funkčnost svého systému.

## Jak povolit EPEL repozitáře v AlmaLinux

Pokud chcete povolit EPEL repozitáře v AlmaLinux, můžete použít následující příkazy:

1. Nainstalujte balíček epel-release:
```
    sudo dnf install epel-release
```    
2. Aktualizujte seznam repozitářů:
```
    sudo dnf makecache
```
Po provedení těchto kroků budou EPEL repozitáře povoleny a budete moci instalovat balíčky z těchto repozitářů pomocí dnf nebo yum.

## Bonus:

Většina balíčků EPEL vyžaduje balíčky z úložiště PowerTools/CRB jako závislosti. Spusťte vhodný příkaz pro povolení úložiště PowerTools/CRB:

**AlmaLinux OS 8**
```
dnf config-manager --set-enabled powertools
```
**AlmaLinux OS 9**
```
dnf config-manager --set-enabled crb
```