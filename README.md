# Strom Spot-Marktpreis in Home Assistant (aWATTar)

Zeigt den aktuellen EPEX Spot-Preis für Strom in ct/kWh an, inkl. Prognose für die nächsten Stunden.

## 1. HACS installieren

### HACS herunterladen

**Option A — Proxmox Terminal (einfacher):**
Direkt in der Proxmox VM-Konsole von Home Assistant:
```bash
wget -O - https://get.hacs.xyz | bash -
```

**Option B — SSH Add-on in Home Assistant:**
- **Settings → Add-ons → Add-on Store** → "Advanced SSH & Web Terminal" installieren
- **Configuration** Tab: Passwort setzen
- **Info** Tab: "Protection mode" ausschalten → **Start**
- Terminal öffnen und ausführen:
```bash
wget -O - https://get.hacs.xyz | bash -
```

### Home Assistant neustarten
- **Settings → System → Restart**

### HACS aktivieren
- **Settings → Devices & Services → Add Integration**
- Nach "HACS" suchen
- Checkboxen akzeptieren
- Code auf **github.com/login/device** eingeben und mit GitHub Account autorisieren
- HACS erscheint in der Seitenleiste

## 2. aWATTar installieren

- **HACS → Integrations → Explore & Download Repositories**
- Nach "aWATTar" suchen → Download
- **Home Assistant neustarten** (Settings → System → Restart)
- **Settings → Devices & Services → Add Integration**
- Nach "aWATTar" suchen → **Germany** auswählen
- Fertig

## Ergebnis

Sensor `sensor.awattar` zeigt den aktuellen Spot-Preis in ct/kWh. Attribute enthalten die stündlichen Preise für die nächsten 24h.

Optional: `apexcharts-card` (via HACS → Frontend) für eine grafische Preiskurve im Dashboard.
