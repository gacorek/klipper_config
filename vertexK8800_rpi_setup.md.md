# 🖨️ Klipper Vertex Delta K8800 — Instalacja na Raspberry Pi

Splashowy przewodnik krok po kroku: od wyboru sprzętu po pełną konfigurację Klippera, Moonrakera i Fluidd z użyciem KIAUH. System zoptymalizowany pod kontrolę, branding i webhook-ready konfigurację.

---

## 🧱 1. Sprzęt — Raspberry Pi, ale splashowo

| Model         | Status       | Uwagi                                |
|---------------|--------------|--------------------------------------|
| RPi 4B (2–8GB)| ✅ Polecany   | Szybki, stabilny, dobry pod kamerę   |
| RPi 3B+       | 🟡 Może być   | Działa, ale wolniejszy przy Fluidd   | <------------ ja posiadam 3b byly problemy z mcu i cpu sie przegrzewal dokupilem radiator do rpi na cpu i zobaczymy
| RPi Zero 2 W  | 🔥 Minimal    | Tylko dla splashowych ascetów        |
| Inne SBC      | ⚠️ Eksperymentalnie | Wymaga ręcznej konfiguracji     |

> 💡 **Rekomendacja**: RPi 4B 4GB lub 8GB — splashowy balans mocy i stabilności

---

## 💽 2. System operacyjny

- Pobierz: **Raspberry Pi OS Lite (64-bit)**
- **Rekomendowane narzędzie**: [Raspberry Pi Imager](https://www.raspberrypi.com/software/)
  - ✅ Pozwala ustawić nazwę hosta, użytkownika, hasło, Wi-Fi i SSH **przed wypaleniem**
  - ✅ Splashowo oszczędza czas i nerwy

> Alternatywa: Balena Etcher + ręczna konfiguracja `ssh` i `wpa_supplicant.conf` na partycji `boot`

---

## 🔌 3. Pierwsze uruchomienie

```bash
ssh pi@<adres IP>
passwd
sudo apt update && sudo apt upgrade -y
sudo apt install git -y


🧙‍♂️ 4. Instalacja KIAUH
bash
git clone https://github.com/th33xitus/kiauh.git
cd kiauh
./kiauh.sh

🔧 5. Instalacja komponentów przez KIAUH
W menu wybierz:

1) Install → Klipper
Podczas instalacji klippera wazna opcja zeby mozna wgrac klippera do drukarki

Your current user is not in group: tty
Add user 'userrpi' to group(s) now? (Y/n):  

Wybierz Y — użytkownik zostanie dodany do grupy tty
Wymagany jest relog lub restart, żeby zmiany zadziałały

1) Install → Moonraker

1) Install → Fluidd


