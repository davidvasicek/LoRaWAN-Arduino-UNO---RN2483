# LoRaWAN-Arduino-UNO---RN2483

### Cíl projektu

Tento projekt byl vytvořen za účelem testování LoRaWAN sítě v oblasti Ostravy, kterou v rámci svých cvičení realizují studenti předmětu Radiokomunikační technika/Rádiové sítě vyučovaného na Katedře telekomunikační techniky, VŠB-TU Ostrava.

V rámci tohoto projektu bylo vytvořeno 8 čidel založených na deskách LoRaWAN Arduino UNO s čipem RN2483 napájených stabilizovaným 3V3 napětím devíti voltové externí baterie a integrovaným MicroUSB konektorem. Každý takovýto modul vysílá prostřednictvím LoRaWAN sítě o frekvenci 433/868 MHz krátký textový řetězec obsahující svou identifikaci, která je zachytávána LoRa Gateway (TTN-GW-VSB) a vizualizována v prostředí The Things Network (TTN). Na základě této komunikace je následně možné určit vysílající výkonovou úrověň daných senzorů a tím vytvořit reálnou mapu pokrytí LoRaWAN sítě dané oblasti.

Pro účely testování bylo zapotřebí obejít Duty Cycle modulu RN2483, který nám omezoval zasílání zpráv v kratších intervalech. Každý takovýto modul RN2483 obsahuje vnitřní čítač zabraňující porušení vysílajících oprávnění přesahující 1% vysílající hodiny. Proto byl modul opakovaně resetován, čímž byl vymazán i jeho vnitřní čítač a možnost testování v kratších časových intervalech.

![alt text](https://github.com/davidvasicek/LoRaWAN-Arduino-UNO---RN2483/blob/master/IMG_LoRaWAN-Arduino-UNO.JPG)
![alt text](https://github.com/davidvasicek/LoRaWAN-Arduino-UNO---RN2483/blob/master/IMG_LoRaWAN-Arduino-UNO_1.JPG)
### Specifikace

LoRaWAN Arduino UNO je malý modulek, na jehož horní straně je transceiver RN2483 firmy Microchip, který je zkomunikovaný s procesorem ATmega328p ležícím na spodní straně desky. V procesoru je bootloader Arduino UNO (možno adaptovat na NANO). Modul je přímo přizpůsoben pro komunikaci v sítích LoRaWAN (více info na things.cz nebo na stránkách Českých Radiokomunikací a.s.). K dispozici jsou tato rozhraní: [1]
-	6 digitálních vstupů/výstupů
-	1 digitální vstup s přerušením pro low power režim
-	1 analogový vstup/výstup
-	vstup pro UART/USB převodník
-	anténní konektor SMA samice (na přání možno osadit U.FL IPX konektorem pro vyvedení antény pigtailem)

**Napájení:**
-	flash mód 5V
-	provozní mód 3,3V (bateriové napájení v rozmezí 2,4V až 4,1V)

**Naměřená spotřeba:**
-	power down mód cca 20uA
-	normální režim cca 25mA
-	vysílací špička cca 120mA

### Tutoriál

Výsledkem tohoto tutoriálu je čidlo založené na desce LoRaWAN Arduino UNO s vysílacím modulem RN2483 umožňující zasílaní krátkých zpráv prostřednictvím bezdrátové technologie LoRa. Tyto zprávy mohou obsahovat například informace o okolních teplotách získávány z externího teplotního senzoru, které je možné k desce LoRaWAN Arduino UNO připojit, nebo informace z mnoha jiných senzorů kompatibilních s touto deskou.

Kompletní tutoriál naleznete ve formátu .pdf [zde](https://github.com/davidvasicek/LoRaWAN-Arduino-UNO---RN2483/blob/master/LoRaWAN-Arduino-UNO---RN2483_tutorial.pdf)
                                                                                        
### Obsah adresáře

- **LoRa_RN5.brd** - DPS LoRaWAN Arduino UNO (Eagle)
- **LoRa_RN5.sch** - schéma LoRaWAN Arduino UNO (Eagle)
- **RN2483-Arduino-Library-master.zip** - knihovna pro RN2483 dostupná [zde](https://github.com/jpmeijers/RN2483-Arduino-Library)
- **LoRaWAN-Arduino-UNO---RN2483_code.ino** - kód pro Arduino IDE
- **LoRaWAN-Arduino-UNO---RN2483_tutorial.pdf** - tutoriál
- **LoRaDHT22** - ukázkový kód pro připojení teplotního čidla DHT22 k LoRaWAN Arduino UNO
- **IMG_LoRaWAN-Arduino-UNO.jpg** - foto vytvořených čidel
- **IMG_LoRaWAN-Arduino-UNO_1.jpg** - foto vytvořených čidel

### Užitečné odkazy

- Specifikace LoRaWAN Arduino UNO - RN2483 - e-shop [zde](https://www.arduinotech.cz/produkt/lorawan-arduino-uno/)
- Specifikace RN2483 [zde](http://ww1.microchip.com/downloads/en/DeviceDoc/50002346C.pdf)
- Popis technologie LoRa [zde](http://www.raycom.cz/data/article/filemanager/LoRa.pdf)
- Článek LPWAN - LoRaWAN, Sigfox - vítejte v IoT! [zde](https://www.arduinotech.cz/inpage/lpwan-lorawan-sigfox-vitejte-v-iot/)
- Článek LoRaWAN Arduino UNO s transceiverem RHF76 [zde](https://www.arduinotech.cz/inpage/lorawan-arduino-uno-s-transceiverem-rhf76/)

### Zdroje

- [1] [https://www.arduinotech.cz/produkt/lorawan-arduino-uno/](https://www.arduinotech.cz/produkt/lorawan-arduino-uno/) 
