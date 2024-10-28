## 🐧 AlmaLinux 9 – jak nainstalovat nejnovější verzi Neovim

![](https://lukan.cz/wp-content/uploads/2024/09/AlmaLinuxlogo-3740426552-1536x864.png)

Né každa Linuxová distribuce nabízí nejnovější verzi [Neovim](https://neovim.io/), kterou vyžadují některé rozšíření Neovim. Velmi jednoduše nainstalujeme nejnovější verzi Neovim kompilací z zdrojového kódu.

Mi si instalaci předvedeme na distribuci založené na RHEL v mém případě na [AlmaLinux 9](https://almalinux.org/). Na ostatních distribucích se bude pouze lišit krok 1, dle toho jestli používáte apt, yay a atd.

Kompilace ze zdrojového kódu

Instalace potřebných nástrojů a knihoven:
```
sudo dnf groupinstall "Development Tools"
sudo dnf install cmake gcc gcc-c++ make ninja-build unzip
```
Stažení zdrojového kódu Neovim:
```
git clone https://github.com/neovim/neovim.git
cd neovim
```
Kompilace Neovim:
```
make CMAKE_BUILD_TYPE=Release
```
Instalace Neovim:
```
sudo make install
```
Pokud některým krokům nerozumíte nebo nevíte co děláte, nechte si poradit od zkušenějších uživatelů na fóru nebo napište zde do diskuze.
