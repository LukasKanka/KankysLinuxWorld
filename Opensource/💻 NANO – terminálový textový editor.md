# 💻 NANO – terminálový textový editor

![](https://lukan.cz/wp-content/uploads/2024/10/nano-wall.jpg)



Textový editor [nano](https://www.nano-editor.org/) je jedním z nejpopulárnějších editorů pro příkazový řádek v Unixových systémech. Byl vytvořen jako alternativa k editoru [pico](https://en.wikipedia.org/wiki/Pico_(text_editor)), který byl součástí balíku Pine, populárního e-mailového klienta.

## Historie NANO

   1. **Vznik a první verze**:
        Nano byl původně vytvořen Chrisem Allegrettou v roce 1999.
        Byl navržen jako svobodný software, který by nahradil pico, protože pico byl součástí proprietárního balíku Pine.
        První verze nano byla vydána v roce 1999 pod názvem TIP (TIP Isn’t Pico).
   2. **Změna názvu**:
        V roce 2000 byl TIP přejmenován na nano, aby se vyhnul možným právním problémům s názvem TIP.
        Název „nano“ byl vybrán jako odkaz na jednotku „nano“, což je miliardtina (10^-9) něčeho, co symbolizuje, že nano je „malý“ editor.
   3. **Vývoj a rozšíření**:
        Od svého vzniku prošel nano mnoha vylepšeními a rozšířeními.
        Byly přidány nové funkce, jako je podpora pro barvení syntaxe, podpora pro vícejazyčné prostředí, a mnoho dalších vylepšení uživatelského rozhraní.
        Nano se stal součástí mnoha Linuxových distribucí a je často používán jako výchozí textový editor pro uživatele, kteří preferují jednoduchost a uživatelskou přívětivost.
   4. **Současnost**:
        Nano je stále aktivně vyvíjen a udržován.
        Poslední verze obsahují mnoho pokročilých funkcí, které ho dělají konkurenceschopným i pro pokročilé uživatele.
        Nano je stále populární díky své jednoduchosti a snadnému ovládání, což ho dělá vhodným pro začátečníky i pro rychlé úpravy textových souborů.

 ## Hlavní rysy nano

   **Jednoduchost**: Nano je známý svou snadnou použitelností a intuitivním rozhraním.

   **Podpora pro barvení syntaxe**: Podporuje barvení syntaxe pro mnoho programovacích jazyků, což usnadňuje čtení a úpravu kódu.

   **Vícejazyčná podpora**: Podporuje mnoho jazyků, což ho dělá přístupným pro širokou škálu uživatelů.

   **Klávesové zkratky**: Nano používá klávesové zkratky, které jsou zobrazeny v dolní části obrazovky, což usnadňuje jejich použití.

Nano je tedy významným nástrojem v arzenálu mnoha uživatelů Unixových systémů a jeho historie svědčí o jeho trvalé popularitě a užitečnosti.

Praxe

Nano je výchozí terminálový textový editor v mnoha  distribucích Linuxu. Ačkoli je použití méně komplikované než u [Vim](https://www.vim.org/) a [Emacs](https://www.gnu.org/software/emacs/) , neznamená to, že použití Nano nemůže být ohromující.

## Základní nano klávesové zkratky

**Zkratka** 	**Popis**
```
nano název souboru (vlož do terminálu) 	Otevřete soubor pro úpravy v Nano
Klávesy se šipkami 	Pohyb kurzoru nahoru, dolů, doleva a doprava
Ctrl+A, Ctrl+E 	Přesuňte kurzor na začátek a konec řádku
Ctrl+Y/Ctrl+V 	Posouvat stránku nahoru a dolů
Ctrl+_ 	Přesuňte kurzor na určité místo
Alt+A a poté použijte šipku 	Nastavte značku a vyberte text
Alt+6 	Zkopírujte vybraný text
Ctrl+K 	Vystřihněte vybraný text
Ctrl+U 	Vložte vybraný text
Ctrl+6 	Zrušte výběr
Ctrl+K 	Vyjmout/smazat celý řádek
Alt+U 	Vrátit zpět poslední akci
Alt+E 	Opakujte poslední akci
Ctrl+W, Alt+W 	Vyhledejte text, přejděte na další shodu
Ctrl+\ 	Hledat a nahradit
Ctrl+O 	Uložte úpravu
Ctrl+X 	Ukončete editor
```
## Jak používat textový editor Nano

Předpokládám, že Nano editor již máte na svém systému nainstalovaný. Pokud ne, doinstalujte si do své distribuce balíček NANO.

## Seznámení s rozhraním editoru Nano

Pokud jste někdy používali Vim nebo Emacs, všimnete si, že používání Nano je mnohem jednodušší. Okamžitě můžete začít psát nebo upravovat text.

Nano editor také zobrazuje důležité klávesové zkratky, které musíte použít pro úpravy ve spodní části editoru. Tímto způsobem se nezaseknete při ukončení editoru jako Vim.

![](https://lukan.cz/wp-content/uploads/2024/10/Snimek-z-2024-10-05-09-14-19-e1728112542322.png)

Když se zobrazí „^X Ukončit“, znamená to, že k ukončení editoru použijete klávesy Ctrl+X. Když se zobrazí „M-U Zrušit“, znamená to, že poslední akci vrátíte zpět pomocí klávesy Alt+U.

## Otevřete nebo vytvořte soubor pro úpravy v Nano

V Nano můžete otevřít soubor pro úpravy takto:
```
nano my_file
```
Pokud soubor neexistuje, stále se otevře editor a po ukončení budete mít možnost uložit text do my_file.

Můžete také otevřít nový soubor bez jakéhokoli jména (jako nový dokument) s Nano takto:
```
nano
```
## Základní úprava

V Nano můžete rovnou začít psát nebo upravovat text. Neexistují žádné speciální režimy vkládání ani nic podobného. Je to skoro jako používat běžný textový editor, alespoň pro psaní a úpravy.

Jakmile cokoli v souboru upravíte, všimnete si, že tyto informace odráží v editoru.

Změny se do souboru automaticky neuloží okamžitě, pokud to výslovně neuděláte. Když editor ukončíte pomocí klávesové zkratky Ctrl+X, budete dotázáni, zda chcete upravený text uložit do souboru či nikoli.

## Pohyb v editoru

Kliknutí myší zde nefunguje. Pomocí kláves se šipkami se můžete pohybovat nahoru a dolů, doleva a doprava.

Pomocí klávesy Home nebo Ctrl+A se můžete přesunout na začátek řádku a pomocí klávesy End nebo Ctrl+E se přesunout na konec řádku. K rolování po stránkách lze použít klávesy Ctrl+Y/Page Up a Ctrl+V/Page Down.

![](https://lukan.cz/wp-content/uploads/2024/10/Snimek-z-2024-10-05-09-23-49-e1728113147117.png)

Pokud chcete přejít na konkrétní místo, jako je poslední řádek, první řádek, na určitý text, použijte kombinaci kláves Ctrl+_. Zobrazí se vám některé možnosti, které můžete použít ve spodní části editoru.

## Vyjmout, zkopírovat a vložit v editoru Nano

Pokud nechcete trávit příliš mnoho času zapamatováním si zkratek, použijte myš.

Vyberte text myší a poté pomocí nabídky pravého tlačítka zkopírujte text. Můžete také použít klávesovou zkratku Ctrl+Shift+C v terminálu. Podobně můžete použít pravé kliknutí a vybrat vložit z nabídky nebo použít kombinaci kláves Ctrl+Shift+V.

**Nano specifické zkratky pro kopírování a vkládání**

Nano také poskytuje své vlastní zkratky pro vyjmutí a vložení textu, ale to by mohlo být pro začátečníky matoucí.

Přesuňte kurzor na začátek textu, který chcete zkopírovat. Stisknutím Alt+A nastavte značku. Nyní pomocí kláves se šipkami zvýrazněte výběr. Jakmile vyberete požadovaný text, můžete pomocí kláves Alt+6 zkopírovat vybraný text nebo použít Ctrl+K k vyjmutí vybraného textu. Pro zrušení výběru použijte Ctrl+6.

Jakmile zkopírujete nebo vyjmete vybraný text, můžete jej vložit pomocí Ctrl+U.
Odstraňte text nebo řádky v Nano

V Nano neexistuje žádná vyhrazená možnost pro smazání. K vymazání jednoho znaku můžete použít klávesu Backspace nebo Delete. Opakovaným stisknutím nebo přidržením odstraníte více znaků.

Můžete také použít klávesy Ctrl+K, které oříznou celý řádek. Pokud to nikam nevložíte, je to stejně dobré jako smazání řádku.

Pokud chcete smazat více řádků, můžete použít Ctrl+K na všechny postupně.

Další možností je použít značku (Ctrl+a). Nastavte značku a pohybem šipky vyberte část textu. Pomocí Ctrl+K ořízněte text. Není třeba jej vkládat a vybraný text se (svým způsobem) smaže.

## Vraťte zpět nebo opakujte svou poslední akci

Přestřihnout špatnou čáru? Vložili jste nesprávný výběr textu? Je snadné dělat takové hloupé chyby a je snadné tyto hloupé chyby napravit.

Poslední akce můžete vrátit zpět a znovu provést pomocí:
```
    Alt+U: Zpět
    Alt + E: Znovu
```    
Tyto kombinace kláves můžete opakovat a vrátit je zpět nebo opakovat vícekrát.

## Hledat a nahradit

Pokud chcete vyhledat určitý text, použijte Ctrl+W, zadejte výraz, který chcete hledat, a stiskněte enter. Kurzor se přesune na první shodu. Chcete-li přejít na další shodu, použijte klávesy Alt+W.

Ve výchozím nastavení se při vyhledávání nerozlišuje malá a velká písmena. Pro hledané výrazy můžete také použít regulární výraz.

Pokud chcete nahradit hledaný výraz, použijte klávesy Ctr+\ a poté zadejte hledaný výraz a stiskněte klávesu enter. Dále se vás zeptá na výraz, kterým chcete hledané položky nahradit.

Kurzor se přesune na první shodu a Nano se zeptá na vaši konformaci pro nahrazení shodného textu. Použijte Y nebo N pro potvrzení nebo zamítnutí. Pomocí Y nebo N se přesunete na další shodu. Můžete také použít A k nahrazení.

## Uložte soubor během úprav (bez ukončení)

V grafickém editoru jste pravděpodobně zvyklí své změny čas od času ukládat. V Nano můžete použít Ctrl+O k uložení změn, které jste v souboru provedli. Funguje to i s novým, nepojmenovaným souborem.

Nano zobrazuje tuto klávesovou zkratku ve spodní části, ale není patrná. Říká „^O Write Out“, což znamená použít Ctrl+O (je to písmeno O, nikoli číslo nula) k uložení vaší aktuální práce. Ne každý na to může přijít.

V grafickém textovém editoru pravděpodobně používáte k uložení změn Ctrl+S. Staré zvyky umírají těžce, ale mohou způsobit potíže. Pokud ze zvyku omylem stisknete Ctrl+S pro uložení souboru, všimnete si, že terminál zamrzne a nemůžete nic dělat.

Pokud omylem stisknete Ctrl+S, stisknete Ctrl+Q, nic nemůže být děsivější než zamrzlý terminál a ztráta práce.
Uložte a ukončete Nano editor

Editor ukončíte stisknutím kláves Ctrl+X. Když to uděláte, dá vám možnost uložit soubor nebo soubor zahodit nebo zrušit proces ukončení.

Můžete to také udělat, pokud chcete uložit upravený soubor jako nový soubor (funkce uložit jako v běžných editorech). Když stisknete Ctrl+X pro ukončení a poté Y pro uložení změn, zobrazí se možnost, do kterého souboru se mají uložit. V tomto okamžiku můžete změnit název souboru.

Chcete-li uložit úpravy do souboru, musíte mít ‚oprávnění k zápisu‘ do souboru, který upravujete.

## Zapomněli jste klávesovou zkratku? Použijte nápovědu

Jako každý jiný textový editor založený na terminálu se Nano silně spoléhá na klávesové zkratky. Přestože ve spodní části editoru zobrazuje několik užitečných zkratek, nemůžete je vidět všechny.

Je nemožné si zapamatovat všechny zkratky, zvláště na začátku. Co můžete udělat, je použít klávesy Ctrl+G k vyvolání nabídky podrobné nápovědy. Nabídka nápovědy obsahuje všechny klávesové zkratky.

## Vždy se podívejte na spodní část editoru Nano

Pokud používáte Nano, všimnete si, že ve spodní části zobrazuje důležité informace. To zahrnuje klávesové zkratky, které budou použity ve scénáři. Zobrazuje také poslední akci, kterou jste provedli.

Pokud se s Nano příliš necítíte, můžete získat více obrazovky pro úpravy textu vypnutím zkratek zobrazených ve spodní části. K tomu můžete použít klávesy Alt+X. Nedoporučuji to dělat, abych byl upřímný. Stisknutím Alt+X se zobrazení zkratky vrátí zpět.
