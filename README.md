# 3D Gaussian Splatting — Transformation in ein lokales System

**Dieser Code wurde mit Claude Sonnet 4.6 generiert und funktioniert in diesem Beispiel. Es wird keine Garantie für Fehler übernommen**

Dieses Jupyter Notebook ermöglicht es die Transformation einer 3DGS Situation in LV95 Koordinaten in ein lokales System. Auch können 3DGS-Scenen rotiert und gemercht werden.

Die Transformation wird automatisch aus den COLMAP Exportfiles aus Agisoft Metashape berechnet.


---

## Voraussetzungen

- Google Account (für Google Drive & Colab)
- Postshot-exportierte `.ply`-Datei(en)
- COLMAP-Rekonstruktion der Originalaufnahmen (`images.txt`)

---

## Ordnerstruktur in Google Drive

Erstelle folgende Struktur in deinem Google Drive **vor** dem ersten Start:

```
MyDrive/
└── Transformation/
    │── 3mio.ply
    │── gebaeude_georef.glb
    │── gebaeude_splat.ply
    │── plaetze_splat.ply
    │── strassen_splat.ply
    │── ...
    │── images_georef.txt
    │── images_nongeoref.txt

```

### Wie erhalte ich images.txt?

https://www.agisoft.com/

Diese Dateien stammen aus der **COLMAP** Ordnerstruktur aus Agisoft Metashape (v.2.3):

1. Agisoft Metashape → (Aktiver Junk) File → `Export` → `Export Cameras` → `Dateityp = COLMAP.txt`
2. Unterordner `colmap/` oder `sparse/0/` suchen
3. `images.txt` kopieren nach `Transformation`


### Wie erhalte ich die Splats (.PLY) aus den .GLB Dateien?

(https://lichtfeld.io/)

1. **LichtFeld-Studio** öffnen
2. `File` → `Import Mesh`
3. über `File` → `Mesh to Splat` kann das Mesh in ein 3DGS umgewandelt werden
4. `File` → `Export` kann das PLY exportiert werden

---

## Notebook starten

1. [colab.research.google.com](https://colab.research.google.com) öffnen
2. `Datei` → `Notebook hochladen` → `gs_evaluation.ipynb` auswählen
3. `Laufzeit` → `Laufzeittyp ändern` → **CPU** aktivieren
4. Zellen der Reihe nach ausführen (`Shift+Enter`)

> **Wichtig:** Beim verbinden des (google)Drives wird eine Anmeldung bei Google erforderlich. Anschliessend werden die Ordner verfügbar sein.

