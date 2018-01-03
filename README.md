# LoRaWAN-Arduino-UNO---RN2483

LoRaWAN Arduino UNO je malý modulek, na jehož horní straně je transceiver RN2483 firmy Microchip, který je zkomunikovaný s procesorem ATmega328p ležícím na spodní straně desky. V procesoru je bootloader Arduino UNO (možno adaptovat na NANO). Modul je přímo přizpůsoben pro komunikaci v sítích LoRaWAN (více info na things.cz nebo na stránkách Českých Radiokomunikací a.s.). K dispozici jsou tato rozhraní:
-	6 digitálních vstupů/výstupů
-	1 digitální vstup s přerušením pro low power režim
-	1 analogový vstup/výstup
-	vstup pro UART/USB převodník
-	anténní konektor SMA samice (na přání možno osadit U.FL IPX konektorem pro vyvedení antény pigtailem)
Napájení:
-	flash mód 5V
-	provozní mód 3,3V (bateriové napájení v rozmezí 2,4V až 4,1V)
Naměřená spotřeba:
-	power down mód cca 20uA
-	normální režim cca 25mA
-	vysílací špička cca 120mA
[1]
