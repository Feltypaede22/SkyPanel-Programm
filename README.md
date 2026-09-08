# SkyPanel-Programm

Nur **SkyPanel** und **SkyPanel Firmware Updater** App-Updates (Manifeste + Release-ZIPs).

## Struktur (nicht ändern)

```
updates/latest.json                      # SkyPanel Hauptprogramm
updates/firmware-updater/latest.json     # SkyPanel Firmware Updater
```

Apps prüfen:

- SkyPanel → `updates/latest.json` (+ Release-Assets `SkyPanel_*.zip`)
- Firmware Updater → `updates/firmware-updater/latest.json` (+ `SkyPanelFirmwareUpdater_*.zip`)

## Version erhöhen (Pflicht bei jedem Release)

Jede neue Version muss **überall** gleich sein:

| App | Lokale Datei | Manifest | GitHub Release Tag | ZIP-Name |
|-----|--------------|----------|--------------------|----------|
| SkyPanel | `ped software/version.json` | `updates/latest.json` | `vX.Y.Z` | `SkyPanel_X.Y.Z.zip` |
| Firmware Updater | `ped software/firmware_updater_version.json` | `updates/firmware-updater/latest.json` | `fw-app-vX.Y.Z` | `SkyPanelFirmwareUpdater_X.Y.Z.zip` |

Skript aus dem Shop-Repo:

```bash
python "ped software/scripts/publish_skypanel_update.py" --app skypanel --version 0.5.3 --zip Pfad\SkyPanel_0.5.3.zip
python "ped software/scripts/publish_skypanel_update.py" --app firmware-updater --version 1.0.5 --zip Pfad\SkyPanelFirmwareUpdater_1.0.5.zip
```

## Repo

https://github.com/Feltypaede22/SkyPanel-Programm
