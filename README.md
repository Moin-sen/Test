
# TafelCapture (Single-File Web App)

**Features**
- Kamera-Start (rear camera bevorzugt)
- Board/Beamer automatisch erkennen (Quadrilateral), entzerren & zuschneiden (OpenCV.js)
- Personenerkennung (MediaPipe Selfie Segmentation via TensorFlow.js)
- Folien-Änderung erkennen (Downscale + Pixel-Diff) → Auto-Foto nur bei Änderung & ohne Person
- Manuelle Auslösung jederzeit
- Speichern in gewählten Ordner (File System Access API) oder Downloads-Fallback

**Start (Variante A: Lokalserver)**
```bash
python -m http.server 8000
# Dann im Browser: http://localhost:8000/tafel-capture/index.html
```

**Start (Variante B: HTTPS Hosting)**
Lade die `index.html` auf z. B. Netlify, GitHub Pages, Vercel hoch.

**Android-Hinweise**
- Chrome (empfohlen). Kamera-Zugriff nur über HTTPS oder `http://localhost`.
- Ordnerwahl per File System Access API (Chrome M132+). Fallback Downloads aktivieren, falls nicht verfügbar.

**Bekannte Grenzen**
- Rechteck-Erkennung kann je nach Licht/Reflexionen fehlschlagen. Dann wird vorübergehend das volle Bild verwendet.
- Taschenlampe wird nicht auf allen Geräten unterstützt.
