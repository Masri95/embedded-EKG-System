Embedded EKG-Messung (Raspberry Pi):
Dieses Repository enthält den Quellcode eines Python-basierten EKG-Messsystems zur kontinuierlichen Erfassung und Verarbeitung der elektrischen Herzaktivität auf einem Raspberry Pi.

Ziel des Projekts ist die technische Realisierung eines einfachen Embedded-Systems zur:
Datenerfassung eines EKG-Signals.
digitalen Signalfilterung.
R-Zacken-Detektion.
Berechnung der Herzfrequenz.
nahezu echtzeitnahen Darstellung.
Der Fokus liegt auf der Stabilität der Abtastrate sowie der Analyse des Systemverhaltens unter ressourcenbegrenzten Bedingungen.

Implementierung, Das System umfasst:
Thread-basierte Datenerfassung
Hochpass, Notch und Tiefpassfilter
R-Peak-Erkennung
Herzfrequenzberechnung
optionale CSV-Speicherung

Die Umsetzung erfolgt in Python unter Linux im Konsolenbetrieb.
Beispielhafte Signalvisualisierung

Hinweis:
Das System dient ausschließlich technischen und wissenschaftlichen Zwecken und ist kein medizinisches Diagnosegerät.
