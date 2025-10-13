# 🛠️ Konfiguracja Klippera dla Velleman K8800 — JanuszShark™ Edition

Splashowo dokumentowana konfiguracja Klippera dla drukarki 3D **Velleman Vertex Delta K8800**, z dodatkami dla Ender 3 V3 KE.  
Projekt opiera się na oryginalnej dokumentacji Klippera oraz pracy społeczności Vertex Delta, ale został gruntownie dostosowany do moich potrzeb, testów i lokalnych warunków.

---

## 🖨️ O mojej drukarce

- **Model:** Velleman Vertex Delta K8800  
- **Płyta główna:** Oryginalna  
- **Hotend:** Oryginalny  
- **Ekstruder:** Oryginalny  
- **Modyfikacje:**  
  > 🔹 **Brak** — drukarka w pełni oryginalna, bez zmian sprzętowych  
  > 🔹 Testy prowadzone na stockowym zestawie, by zapewnić kompatybilność z domyślnym hardwarem  
  > 🔹 Planowane: radiator na RPi, ewentualne dodatki (czujnik filamentu, ekran statusu)

---

## ⚙️ Główne funkcje tej konfiguracji

- Precyzyjna kalibracja geometrii Delty  
- Makra do wymiany filamentu (`LOAD_FILAMENT`, `UNLOAD_FILAMENT`)  
- Wsparcie dla LCD z enkoderem  
- Konfiguracja Moonraker + Fluidd  
- (W planach: stabilna siatka poziomowania stołu)

---

## 📁 Struktura plików

- `printer.cfg` — definicje sprzętu  
- `moje_makra.cfg` — makra użytkowe  
- `mesh.cfg` — konfiguracja siatki poziomowania (w trakcie testów)  
- `moonraker.conf` — konfiguracja interfejsu  
- `fluidd.cfg` — główny plik UI, zawiera makra i definicje przycisków  
- `README.md` — ten plik

> 🔥 Plik `ui_makra.cfg` zostanie usunięty — cała logika UI przeniesiona do `fluidd.cfg` zgodnie z aktualnymi standardami Fluidd.

---

## 🚧 Status projektu

> Obecnie większość funkcji działa poprawnie, z wyjątkiem poziomowania stołu.  
> Raspberry Pi zgłasza błąd `MCU throttle` — procesor się przegrzewa.  
> Zamówiony radiator — po montażu ruszam z dalszymi testami i pełną dokumentacją instalacji od podstaw.  
> Trwa migracja makr UI do `fluidd.cfg` — uproszczenie konfiguracji i pełna zgodność z interfejsem Fluidd.

---

## 🙏 Podziękowania / Źródła

Projekt opiera się na pracy zespołu Klippera oraz społeczności Vertex Delta K8800.

### 📦 Repozytoria źródłowe:

- [Klipper — oficjalna dokumentacja i kod](https://github.com/Klipper3d/klipper)  
  > Kluczowe źródło wiedzy i konfiguracji. Część ustawień została zaadaptowana i zmodyfikowana na potrzeby mojej drukarki.

- [Vertex-Delta-Mods by SusisStrolch](https://github.com/susisstrolch/Vertex-Delta-Mods)  
  > Inspiracje sprzętowe i konfiguracyjne dla K8800.  
  > Wszystkie pliki SusisStrolch są objęte licencją [Creative Commons Attribution 3.0](https://creativecommons.org/licenses/by/3.0/).  
  > Dla prac pochodnych należy zapoznać się z oryginalną licencją autora.
  
- [KIAUH (Klipper Installation And Update Helper)] (https://github.com/th33xitus/kiauh) 
  > Niezastąpione narzędzie do instalacji Klippera, Moonrakera, Fluidd i zarządzania instancjami. 

---

## 📄 Licencja

Wszystkie autorskie pliki w tym repozytorium są objęte licencją MIT (patrz plik `LICENSE`).  
Pliki pochodzące od innych autorów są objęte ich oryginalnymi licencjami.

---

## 📡 Webhook Alert

```json
{
  "klipper_status": "testy_trwają",
  "heat_sink": "zamówiony",
  "bed_mesh": "niestabilne",
  "ui_migration": "fluidd.cfg",
  "autor": "gacorek vel JanuszShark™"
}


