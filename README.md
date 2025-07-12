# i2c-eeprom-overlay
Raspberry Pi DT-Overlay für verschiedene Atmel AT24 und kompatible i2c-EEPROMs

übersetzen mit: `dtc -@ -Hepapr -W no-unit_address_vs_reg -I dts -O dtb -o i2c-eeprom.dtbo i2c-eeprom-overlay.dts`
Und die `i2c-eeprom.dtbo` Datei nach $BOOTMOUNTPOINT/overlays/ kopieren bzw. verschieben. Details zur Konfiguration siehe [a relative link](i2c-eeprom.README)

Der EEPROM liegt dann als Datei unter `/sys/bus/i2c/devices/$BUS-00$ADDR/eeprom`
wobei BUS die i2c Busnummer und ADDR die i2c Adresse des EEPROM ist.
Beispiel für einen EEPROM am i2c1 Bus mit der Adresse 0x50:
`ls -l /sys/bus/i2c/devices/1-0050/eeprom`
