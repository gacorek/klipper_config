🔧 Instalacja Klippera na Vertex K8800 — JanuszShark™ Edition

🧱 1. Przygotowanie KIAUH
🔌 Podłącz Raspberry Pi do drukarki
Użyj kabla USB typu A–B (drukarkowego)

Podłącz Raspberry Pi do portu USB na płycie głównej Vertexa K8800

Upewnij się, że drukarka jest włączona

🔁 Uruchom KIAUH
bash
cd ~/kiauh
./kiauh.sh
W menu głównym wybierz:

text
4) [Advanced] → 1) [Build]
🔧 2. Konfiguracja firmware’u Klippera
W menu Klipper Firmware Configuration ustaw:

Kod
[*] Enable extra low-level configuration options
    Micro-controller Architecture (Atmega AVR)  --->
    Processor model (atmega2560)  --->
    Processor speed (16Mhz)  --->
    Communication interface (UART0)  --->
(500000) Baud rate for serial port
()  GPIO pins to set at micro-controller startup (NEW)
Nie wiem co to za ostatnia opcja, ale brzmi nieźle

Naciśnij Q, potem Y — KIAUH zapisze konfigurację i rozpocznie kompilację.

🛠️ 3. Kompilacja firmware’u
KIAUH wygeneruje:

bash
/home/gacorek/klipper/out/klipper.elf.hex
Na końcu wybierz y, aby zapisać konfigurację jako:

text
klippervertexk8800.config
🔥 4. Flashowanie firmware’u
Wybierz:

text
3) [Build + Flash] → 1) Regular flashing method → 1) make flash (default)
Typ połączenia:

text
1) USB
Wybierz wykryty MCU:

text
0) usb-1a86_USB2.0-Serial-if00-port0
Potwierdź:

text
Y) Start flash process
KIAUH zatrzyma klipper.service, wgra firmware przez avrdude, zweryfikuje i uruchomi usługę ponownie:

text
[OK] Flashing successful!
🧠 5. Po flashowaniu
Sprawdź port MCU:

bash
ls /dev/serial/by-id/
Dodaj do printer.cfg:

ini
[mcu]
serial: /dev/serial/by-id/usb-1a86_USB2.0-Serial-if00-port0
📟 6. Wyświetlacz i enkoder
Po wgraniu Klippera, wyświetlacz drukarki oraz pokrętło enkodera pełnią funkcję informacyjną — pokazują status połączenia, błędy, temperatury i inne komunikaty systemowe. Nie służą już do sterowania ruchem ani menu — cała kontrola odbywa się przez Fluidd/Moonraker.
