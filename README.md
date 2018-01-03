# LoRaWAN-Arduino-UNO---RN2483

### Účel projektu

Tento projekt byl vytvořen za účelem testování LoRaWAN sítě v oblasti Ostravy, kterou v rámci svých cvičení realizují studenti předmětu Radiokomunikační technika/Rádiové sítě vyučovaného na Katedře telekomunikační techniky, VŠB-TU Ostrava
 
V rámci tohoto projektu bylo vytvořeno 8 čidel založených na deskách LoRaWAN Arduino UNO s čipem RN2483 napájených stabilizovaným 3V3 napětím devíti voltové externí baterie a integrovaným MicroUSB konektorem. Každý takovýto modul vysílá prostřednictívm LoRaWAN sítě o frekvenci 433/868 MHz krátký textový řetězec obsahující svou identifikaci, která je zachytávána LoRa Gateway (TTN-GW-VSB) a vizualizována v prostředí The Things Network (TTN). Na základě takto přijatých zpráv je následně možné určit vysílající výkonovou úrověň daných senzoru a tím vytvořit realnou mapu pokrytí LoRaWAN sítě dané oblasti.

Pro účely testování bylo zapotřebí obejít Duty Cycle modulu RN2483, který nám omezoval zasílání zpráv v kratších intervalech. Každý takovýto modul RN2483 obsahuje vnitřní čítač zabraňující porušení vysílajících oprávnění přesahující 1% vysílající hodiny. Proto byl modul opakovaně resetován, čimž byl vymazán i jeho vnitřní čítač a možnost testování v kratších časových intervalech.

### Specifikace

LoRaWAN Arduino UNO je malý modulek, na jehož horní straně je transceiver RN2483 firmy Microchip, který je zkomunikovaný s procesorem ATmega328p ležícím na spodní straně desky. V procesoru je bootloader Arduino UNO (možno adaptovat na NANO). Modul je přímo přizpůsoben pro komunikaci v sítích LoRaWAN (více info na things.cz nebo na stránkách Českých Radiokomunikací a.s.). K dispozici jsou tato rozhraní:
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
-	vysílací špička cca 120mA                                                                                                              [1]

### Tutoriál

Kompletní tutoriál naleznete ve formátu .pdf [zde](https://www.google.com)
                                                                                        

### Obsah adresáře

- **LoRa_RN5.brd** - DPS LoRaWAN Arduino UNO (Eagle)
- **LoRa_RN5.sch** - schéma LoRaWAN Arduino UNO (Eagle)
- **RN2483-Arduino-Library-master.zip** - knihovna pro RN2483 dostupná [zde](https://github.com/jpmeijers/RN2483-Arduino-Library)
- code.ino - Kód pro Arduino IDE
- Tutorial.pdf - Návod na 

### Zdroje

- [1] [https://www.arduinotech.cz/produkt/lorawan-arduino-uno/](https://www.arduinotech.cz/produkt/lorawan-arduino-uno/) 
- [2] [https://www.arduinotech.cz/inpage/lorawan-arduino-uno-s-transceiverem-rhf76/](https://www.arduinotech.cz/inpage/lorawan-arduino-uno-s-transceiverem-rhf76/)
[1] []()
[1] []()
[1] []()
[1] []()
[1] []()
[1] []()
