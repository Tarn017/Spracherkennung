# Spracherkennung

**Keyword Spotting** 

1.	Öffne [Edge Impulse](https://studio.edgeimpulse.com/) und erstelle ein neues Projekt.
2.	Verbinde ein neues device (bspw. Handy) um Audio Daten zu sammeln. Klicke auf „connect a device” und scanne den QR-Code mit dem Handy oder wähle eine der anderen Optionen.

![requirements Screenshot](https://raw.githubusercontent.com/Tarn017/Object-Detection/main/assets/requirements.png)

4.	Lege das Label des Wortes fest auf das du das Modell trainieren willst. Wähle microphone, 16000Hz und die Länge der Aufnahme fest (bspw. 60000ms). Während dieser Aufnahme kannst du das Wort mehrfach einsprechen, achte nur darauf, dass du zwischen den Wörtern kurze Pausen machst:
5.	Nun müssen die einzelnen Wörter noch aus der langen Aufnahme herausgefiltert werden. Splitte das Sample in kleinere Abschnitte indem du auf die drei Punkte und „Split sample“ drückst:
6.
7.	Wähle eine passende Länge (empfohlen 1000ms) und aktiviere shift samples (rechts unten) für eine bessere Generalisierung. Achte darauf, dass die Boxen wirklich über den einzelnen Wörtern liegen. Du kannst die Boxen verschieben, löschen oder weitere hinzufügen:
8.	(Optional) Der Datensatz kann für eine bessere Generalisierung mit noise-, sowie unknown-daten aus dem Ordner [MP3-Data](https://github.com/Tarn017/Spracherkennung/tree/main/MP3_Data) erweitert werden. Klicke dafür zunächst auf Upload Data:
9.	(Optional) Klicke anschließend auf Select a Folder und wähle den kompletten Ordner MP§_Daten aus. Es können theoretisch auch kleinere Unterordner oder nur einzelne Dateien hochgeladen werden:
10.	Wichtig ist, dass Trainings- und Testdaten vorhanden sind. Gehe dafür entweder vom Reiter Training auf Test und sammle mit derselben Methode weitere Daten oder sammle zunächst alle Daten nur in Training. Gehe dafür links unter "Dashboard" kann ganz unten auf "Perform Train / Test Split" um die gesammelte Daten im verhältnis 80/20 in Train- und Testdaten aufzuteilen.
11.	Wähle in „Create impulse“ die Blöcke “Audio MFCC” sowie “Clasification” und speichere den Impuls.
12.	MFCC: Autotune Parameters -> Save Parameters -> Generate Features
13.	Classifier: Activate Augmentation -> Save & Train
14.	Live Classification/Model Testing: Teste dein erzeugtes Modell
15.	Deployment: Arduino Library auswählen und builden
16.	Die geladene Datei als Zip-Bibliothek in Arduino einbinden
17.	Installiere im Board-Manager: “Arduino Mbed OS Nano Boards” und wähle als Board den “Arduino Nano 33 Ble“.
18.	In Arduino: File -> Examples -> <name>_inferencing -> nano_ble33_sense -> nano_ble33_sense_microphone_continuous
19.	Alternativ: File -> Examples -> <name>_inferencing -> nano_ble33_sense -> nano_ble33_sense_microphone (nimmt nicht durchgehend auf, sondern nur wenn “Recording…” ausgegeben wird)

**Weiterführende Links**

- Weiterführende Informationen zur Anwendung von Edge Impulse auf dem Arduino: [Arduino](https://docs.arduino.cc/tutorials/nano-33-ble-sense/edge-impulse/)
- Weiterführende Informationen zu Edge Impulse: [Edge Impulse](https://docs.edgeimpulse.com/tutorials/end-to-end/keyword-spotting)


Quelle der Audio-Daten:
Edge Impulse. (2024). Audio Classification – Keyword Spotting. Edge Impulse Studio. Verfügbar unter: https://studio.edgeimpulse.com/public/499022/latest
(Lizenz: Apache 2.0)
