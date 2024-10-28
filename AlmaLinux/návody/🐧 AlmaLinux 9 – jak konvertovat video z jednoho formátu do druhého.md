# 🐧 AlmaLinux 9 – jak konvertovat video z jednoho formátu do druhého

![](../img/FFmpeg.jpeg)

V posledním článku jsme si ukázaly jak nainstalovat [FFmpeg](https://ffmpeg.org/). V tomto článku si ukážeme jak v Linuxu jednoduše převedeme video z jednoho do druhého formátu a čeká nás malí bonus.

Abychom mohli převod provést potřebujeme nainstalovat FFmpeg čemu jsme se věnovali v [minulém článku](https://lukan.cz/2024/10/almalinux-9-instalace-ffmpeg-kodeku/). Tento návod by měl fungovat na distribucích rodiny RHEL a i všech ostatních linuxových distribucích.

 

 

Postup převodu je následující: v konzoli se přesuňte kde máte uložený video soubor. Příkazem níže provedete převod do jiného formátu, input a output nahraďte názvem souboru.
```
ffmpeg -i input.mp4 output.avi
```
Bonus: z videa můžete extrahovat pouze zvuk, to uděláte tímto příkazem:
```
ffmpeg -i input.mp4 -vn output.mp3
```
-vn nám disabluje video a převede se samotný zvuk.
