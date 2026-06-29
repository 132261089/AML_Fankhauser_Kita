Projektarbeit AML: Anomalieerkennung in SCADA-Windturbinen:

Dieses Repository enthält den Code zur Projektarbeit im Fach Applied Machine Learning. 
Das Ziel ist die frühzeitige Erkennung von Bauteilausfällen in Windkraftanlagen anhand von SCADA-Sensordaten.

Zwei Methoden werden gegenübergestellt:
	- Semi Supervised: Isolation Forest, One-Class SVM, Conv-Autoencoder.
	- Supervides: Random Forest, LightGBM, 1D-CNN, LSTM.

Das Projekt ist wie folgt strukturiert:
/AML_CARE_Projekt/
├── AML_CARE_Notebook.ipynb  		  # Zentrales Jupyter Notebook
├── README.md                         # Diese Dokumentation
├── requirements.txt                  # Benötigte Python-Bibliotheken
├── CARE_To_Compare/                  # Lokaler Datenordner (Voraussetzung für lokale Ausführung)
│   ├── Wind Farm A/
│   └── Wind Farm B/
├── artifacts/                        # Wird automatisch erstellt (Modell-Scores & Meta-Daten)
└── parquet/                          # Wird automatisch erstellt (Konvertierte Daten)

pip install -r requirements.txt

Um das Notebook lokal auszuführen, lade die Daten von Zenodo herunter und speichere sie in einem Ordner "CARE_To_Compare" im Hauptverzeichnis des Repositories. 
Das Notebook sucht dort automatisch nach den Rohdaten, sofern kein Kaggle-Input-Verzeichnis gefunden wird.

Schnelldurchlauf (empfohlen)
Mit RETRAIN = False (Standardeinstellung im Notebook) werden die bereits berechneten Scores aus dem artifacts-Ordner geladen. Das Notebook läuft in wenigen Minuten durch, ohne GPU und ohne TensorFlow.

Neuberechnung
Mit RETRAIN = True werden alle Modelle neu trainiert. Dafür wird TensorFlow und idealerweise eine GPU benötigt. Laufzeit: mehrere Stunden. Die Ergebnisse werden automatisch im artifacts-Ordner gespeichert.