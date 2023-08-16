# Instructions to execute Bootloader for SmartGrip

- Turn ON SmartGrip in Bootloader Mode
- Keep the code (.bin extension) file in stm32bootloader directory
- Launch CMD in stm32loader directory
- Run the desired commands below

## Python Command to ERASE memory using bootloader
python -m stm32loader -p COM3 -b 115200 -P none -V -f G0 -e

**Command Syntax :** 

python -m stm32loader -p "COM PORT" -b 115200 -P none -V -f G0 -e

## Python Command to Write & VERIFY memory using bootloader
python -m stm32loader -p COM3 -b 115200 -P none -V -f G0 -a 134258688 -w -v Code.bin

**Command Syntax :** 

python -m stm32loader -p "COM PORT" -b 115200 -P none -V -f G0 -a "TARGET ADDRESS (DECIMAL)" -w -v "YOUR BIN FILE"

## Python Command to JUMP TO ADDRESS using bootloader
python -m stm32loader -p COM3 -b 115200 -P none -V -f G0 -g 134258688

**Command Stntax :**

python -m stm32loader -p "COM PORT" -b "BUAD RATE" -P none -V -f G0 -g "TARGET ADDRESS (DECIMAL)"

## Python Command to ERASE, WRITE, VERIFY & JUMP TO ADDRESS using bootloader
python -m stm32loader -p COM3 -b 115200 -P none -V -f G0 -e && timeout /t 5 && python -m stm32loader -p COM3 -b 115200 -P none -V -f G0 -a 134258688 -w -v Code.bin && timeout /t 5 && python -m stm32loader -p COM3 -b 115200 -P none -V -f G0 -g 134258688

**Command Syntax :** 

python -m stm32loader -p "COM PORT" -b "BUAD RATE" -P none -V -f G0 -e && timeout /t "DELAY TIME (second)" && python -m stm32loader -p "COM PORT" -b "BUAD RATE" -P none -V -f G0 -a "TARGET ADDRESS (DECIMAL)" -w -v "YOUR BIN FILE" && timeout /t "DELAY TIME (seconds)" && python -m stm32loader -p "COM PORT" -b "BUAD RATE" -P none -V -f G0 -g "TARGET ADDRESS (DECIMAL)"
