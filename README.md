# AMPTemplate

Eigene Vorlagen (Generic Module) für [CubeCoders AMP](https://cubecoders.com/AMP).

| Vorlage | Dateien | Beschreibung |
|---|---|---|
| **WikingerBot** | `wikingerbot*` | Discord-Bot der Wikinger-Community – [Anleitung](https://github.com/Daywalker91/Wikingerbot/blob/main/AMP.md) |

## In AMP einbinden

*Configuration → Instance Deployment → Configuration Repository* → `Daywalker91/AMPTemplate:main`
hinzufügen → *Fetch Latest* → AMP (ADS) neu starten. Danach stehen die Vorlagen beim Anlegen einer Instanz zur Auswahl.

## Aufbau einer Vorlage

| Datei | Inhalt |
|---|---|
| `<name>.kvp` | Kernkonfiguration: Programm, Startargumente, Konsole, Bereit-Erkennung |
| `<name>config.json` | Eingabefelder in der AMP-Oberfläche |
| `<name>metaconfig.json` | welche Felder AMP in welche Datei schreibt (hier: die `.env` des Bots) |
| `<name>updates.json` | Schritte beim *Update*: Code laden, venv, Abhängigkeiten |
| `<name>ports.json` | Ports der Instanz |

Zusätzlich braucht das Repo eine `manifest.json` mit `"repotype": "AppTemplates"` – daran
erkennt AMP es als Vorlagen-Sammlung. Neue oder geänderte Vorlagen erscheinen nach
*Fetch Latest* erst nach einem **Neustart von AMP** (ADS) in der Liste.

Bearbeiten geht direkt hier oder bequem im
[Generic Config Generator](https://iceofwraith.github.io/GenericConfigGen/) (Import → ändern → Export).

Vorbild: die offizielle GatekeeperV2-Vorlage in
[CubeCoders/AMPTemplates](https://github.com/CubeCoders/AMPTemplates).

## Vorlage ändern

Bei jeder Änderung an Feldern oder Einstellungen `Meta.ConfigVersion` in der `.kvp`
hochzählen (und `Meta.ReleaseNotes` kurz füllen) – sonst übernimmt AMP die Änderung nicht
in bestehende Instanzen. Danach in ADS: *Fetch Latest* → bei der Instanz
*Refresh Configuration* (oder ADS neu starten).
