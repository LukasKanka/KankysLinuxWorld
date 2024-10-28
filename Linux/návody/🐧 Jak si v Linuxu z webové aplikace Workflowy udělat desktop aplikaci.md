## 🐧 Jak si v Linuxu z webové aplikace Workflowy udělat desktop aplikaci ##

![](https://lukan.cz/wp-content/uploads/2024/10/workflowy.png)


[Workflowy](https://workflowy.com/) je webová aplikace pro správu úkolů a poznámek, která je přístupná přes prohlížeč. Proto není nutné ji instalovat jako samostatnou aplikaci na Linux distrech. Můžete ji používat přímo přes webový prohlížeč, jako je [Firefox](https://www.mozilla.org/cs/firefox/new/) nebo [Chrome](https://www.google.com/intl/cs/chrome/).

Pokud byste však chtěli mít Workflowy jako samostatnou aplikaci na svém ploše, můžete použít nástroj jako **[Nativefier](https://github.com/nativefier/nativefier)**, který umožňuje vytvořit samostatnou aplikaci z webových stránek.

Následující kroky popisují, jak to udělat pomocí Nativefier:

1. **Nainstalujte Node.js a npm**: Pokud ještě nemáte nainstalovaný [Node.js](http://node.js/) a npm, můžete je nainstalovat pomocí následujících příkazů:
```
sudo dnf install nodejs npm
```
2. **Nainstalujte Nativefier**: Nativefier je nástroj pro vytváření samostatných aplikací z webových stránek. Nainstalujte ho pomocí npm:
```
sudo npm install -g nativefier
```
3. **Vytvořte samostatnou aplikaci pro Workflowy:** Použijte Nativefier k vytvoření samostatné aplikace pro Workflowy:
```
nativefier --name "Workflowy" "https://workflowy.com/"
```

## Bonus:

Pokud chcete vytvořit zástupce (špouštěc) pro aplikaci Workflowy, kterou jste vytvořili pomocí Nativefier, můžete to udělat následujícím způsobem:

1. **Přesuňte aplikaci do složky /opt**: Nejprve přesuňte aplikaci, kterou jste vytvořili pomocí Nativefier, do složky /opt. Tato složka je obvykle používána pro dodatečné aplikace.
```
sudo mv Workflowy-linux-x64 /opt/Workflowy
```
2. **Vytvořte zástupce v domácím adresáři**: Vytvořte soubor workflowy.desktop v adresáři ~/.local/share/applications:
```
nano ~/.local/share/applications/workflowy.desktop
```
3. **Upravte soubor zástupce**: Do souboru workflowy.desktop vložte následující obsah:
```
[Desktop Entry]
Name=Workflowy
Comment=Workflowy Web App
Exec=/opt/Workflowy/Workflowy
Icon=/opt/Workflowy/resources/app/icons/icon.png
Terminal=false
Type=Application
Categories=Utility;Application;
```
Ujistěte se, že cesta k ikoně (Icon) je správná. Pokud aplikace neobsahuje ikonu, můžete použít libovolnou jinou ikonu nebo cestu k ikoně neuvádět.

4. **Nastavte oprávnění**: Ujistěte se, že soubor zástupce je spustitelný:
```
chmod +x ~/.local/share/applications/workflowy.desktop
```
5. **Spusťte aplikaci**: Nyní byste měli vidět Workflowy v nabídce aplikací. Můžete ji spustit stejně jako jakoukoli jinou aplikaci.
