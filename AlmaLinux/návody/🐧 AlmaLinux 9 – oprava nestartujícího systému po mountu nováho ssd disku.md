## 🐧 AlmaLinux 9 – oprava nestartujícího systému po mountu nováho ssd disku

![](https://lukan.cz/wp-content/uploads/2024/09/AlmaLinuxlogo-3740426552-1536x864.png)

Pokud jste si připojily do AlmaLinux 9 nový disk a systém po restartu nenajel, oprava existuje.

Nejspíš jste použily nebo podobný způsob při přidání ssd do Vašeho systému:

```
sudo blkid
sudo mkdir /media/
sudo mkdir /media/data
sudo nano /etc/fstab
sudo mount -a
```
A po restartu pc se Vám zobrazila tato chyba:
```
    You are in emergency mode. After logging in, type journalctl -xb to view system logs, systemctl reboot to reboot, systemctl default or exit

    Přístup ke konzole nelze získat, účet roota je uzamčen.

    Podrobnosti naleznete v manuálové stránce sulogin(8).
```
![](https://lukan.cz/wp-content/uploads/2024/09/20240920_161834360_iOS-150x150.jpg)

## Oprava:

Použijeme live usb, například [EndeavourOS](https://endeavouros.com/).

 Najdi v prohlížeči souboru, v root AlmaLinux složku etc a v ní soubor **fstab – etc/fstab**

Ve složce etc otevři terminál – klikem pravím tlačítek a otevřít v terminálu.

Do terminálu vlož: **sudo nano fstab**

Zakomentuj řádek pomocí # nebo smaž kde jsi přidal nový ssd disk

Vlož do terminálu: **sudo umount /mnt/root**

Restartuj systém: **reboot**

A nezapomeň vytáhnout usb z pc.

Nyní by Váš systém měl najet.

Jak připojit nový ssd v AlmaLinux najdeš v tomto [článku](https://lukan.cz/2024/09/almalinux-pripojeni-noveho-ssd-v-gnome-bez-padu-systemu-po-restartu-systemu/).
