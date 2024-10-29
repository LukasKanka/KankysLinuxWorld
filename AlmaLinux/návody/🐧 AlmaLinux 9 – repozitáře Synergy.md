# 🐧 AlmaLinux 9 – repozitáře Synergy

![](../img/AlmaLinuxlogo.png)


Úložiště Synergy obsahuje balíčky, které ještě nejsou přítomny v RHEL nebo EPEL, ale byly pro Společenství vyžádány Společenstvím. Toto úložiště lze považovat za repozitář před EPEL, protože AlmaLinux OS Foundation jako člen komunity EL vynaloží veškeré úsilí, aby balíčky dostaly do EPEL tak, aby byly široce dostupné na všech distribucích kompatibilních s RHEL. Balíček vydání úložiště Synergy vám také umožňuje používat jej nejen s AlmaLinuxem, ale s jakoukoli distribucí kompatibilní s RHEL

Úložiště Synergy lze povolit pro OS AlmaLinux a pro další distribuce v ekosystému EL, jako je RHEL, CentOS, Rocky Linux atd.

Chcete-li povolit úložiště Synergy na počítačích AlmaLinux, spusťte následující příkaz:
```
dnf install -y almalinux-release-synergy
```
Chcete-li povolit úložiště Synergy v jakékoli distribuci kompatibilní s RHEL, spusťte následující příkaz:
```
dnf install -y https://repo.almalinux.org/almalinux/almalinux-release-synergy-latest-$(rpm -E %rhel).noarch.rpm
```
Povolení úložiště PowerTools/CRB

Vezměte prosím na vědomí, že povolení úložiště Synergy automaticky povolí také úložiště EPEL a PowerTools/CRB, pokud je vydání epel poskytnuté vaší distribucí dostatečně aktuální. Pokud stále nemáte povoleno PowerTools/CRB, měli byste spustit následující:
```
dnf update -y epel-release
crb enable
```
Distribuce bez epel-release balíčku

Pokud vaše distribuce neposkytuje epel-release během balíčku se zobrazí chyba závislosti almalinux-release-synergy instalace balíčku. V tomto případě použijte k povolení úložiště Synergy následující příkaz:
```
dnf install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-$(rpm -E %rhel).noarch.rpm \
               https://repo.almalinux.org/almalinux/almalinux-release-synergy-latest-$(rpm -E %rhel).noarch.rpm
```
## Bonus : vyžádejte si balíček

O balíček lze požádat prostřednictvím [chatovacího kanálu Packaging](https://chat.almalinux.org/almalinux/channels/engineeringpackaging)

[(otevře se nové okno)](https://chat.almalinux.org/almalinux/channels/engineeringpackaging) v Mattermost. Aby byl balíček zahrnut do úložiště Synergy, musí splňovat následující kritéria:

* Balíček nesmí být v úložištích RHEL (včetně dalších úložišť jako RT, NFV, SAP atd.)
* Balíček nesmí být v úložišti EPEL
* Balíček nesmí aktualizovat, nahrazovat nebo být v konfliktu s balíčky od RHEL a EPEL
* Vývojář balíčků neudržuje úložiště YUM/DNF pro distribuce kompatibilní s RHEL

