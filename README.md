# Spracherkennung

**Keyword Spotting** 

1.	Öffne [Edge Impulse](https://studio.edgeimpulse.com/) und erstelle ein neues Projekt.
2.	Verbinde ein neues device (bspw. Handy) um Audio Daten zu sammeln. Klicke auf „connect a device” und scanne den QR-Code mit dem Handy oder wähle eine der anderen Optionen:

<p align="center">
  <img src="https://raw.githubusercontent.com/Tarn017/Spracherkennung/main/assets/newdata.png" width="500">
</p>

3.	Lege das Label des Wortes fest auf das du das Modell trainieren willst. Wähle microphone, 16000Hz und die Länge der Aufnahme fest (bspw. 60000ms). Während dieser Aufnahme kannst du das Wort mehrfach einsprechen, achte nur darauf, dass du zwischen den Wörtern kurze Pausen machst:

<p align="center">
  <img src="https://github.com/Tarn017/Spracherkennung/blob/main/assets/collectdata.png" width="500">
</p>

4.	Nun müssen die einzelnen Wörter noch aus der langen Aufnahme herausgefiltert werden. Splitte das Sample in kleinere Abschnitte indem du auf die drei Punkte und „Split sample“ drückst:

<p align="center">
  <img src="https://github.com/Tarn017/Spracherkennung/blob/main/assets/splitsample.png" width="500">
</p>

5.	Wähle eine passende Länge (empfohlen 1000ms) und aktiviere shift samples (rechts unten) für eine bessere Generalisierung. Achte darauf, dass die Boxen wirklich über den einzelnen Wörtern liegen. Du kannst die Boxen verschieben, löschen oder weitere hinzufügen:

<p align="center">
  <img src="https://github.com/Tarn017/Spracherkennung/blob/main/assets/boxen.png" width="500">
</p>

6.	(Optional) Der Datensatz kann für eine bessere Generalisierung mit noise-, sowie unknown-daten aus dem Ordner [MP3-Data](https://github.com/Tarn017/Spracherkennung/tree/main/data/MP3_Data) erweitert werden. Klicke dafür zunächst auf Upload Data:

<p align="center">
  <img src="https://github.com/Tarn017/Spracherkennung/blob/main/assets/uploaddata.png" width="500">
</p>

7.	(Optional) Klicke anschließend auf Select a Folder und wähle den kompletten Ordner MP§_Daten aus. Es können theoretisch auch kleinere Unterordner oder nur einzelne Dateien hochgeladen werden:

<p align="center">
  <img src="https://github.com/Tarn017/Spracherkennung/blob/main/assets/traintestsplit.png" width="500">
</p>

8.	Wichtig ist, dass Trainings- und Testdaten vorhanden sind. Gehe dafür entweder vom Reiter Training auf Test und sammle mit derselben Methode weitere Daten oder sammle zunächst alle Daten nur in Training. Gehe dafür links unter "Dashboard" kann ganz unten auf "Perform Train / Test Split" um die gesammelte Daten im verhältnis 80/20 in Train- und Testdaten aufzuteilen. Für jede Klasse sollten mindestens 5 Minuten an Trainingsdaten existieren.

<p align="center">
  <img src="https://github.com/Tarn017/Spracherkennung/blob/main/assets/selectfolder.png" width="400">
</p>

9. Wähle als target device den Arduino Nano 33 Ble Sense aus und klicke save:

<p align="center">
  <img src="https://github.com/Tarn017/Spracherkennung/blob/main/assets/device.png" width="500">
</p>

10.	Wähle in „Create impulse“ die Blöcke “Audio MFCC” sowie “Clasification” und speichere den Impuls:

<p align="center">
  <img src="https://github.com/Tarn017/Spracherkennung/blob/main/assets/impulse.png" width="600">
</p>

11.	Gehe links auf MFCC: Autotune Parameters -> Save Parameters -> Generate Features
12.	Gehe links auf Classifier: Activate Augmentation -> Save & Train
13.	Gehe links auf Live Classification/Model Testing: Teste dein erzeugtes Modell
14.	Gehe links auf Deployment: Arduino Library auswählen und builden
15.	In der Arduino IDE: Die geladene Datei als Zip-Bibliothek in Arduino einbinden
16.	In der Arduino IDE:Installiere im Board-Manager: “Arduino Mbed OS Nano Boards” und wähle als Board den “Arduino Nano 33 Ble“.
17.	In der Arduino IDE: File -> Examples -> <name>_inferencing -> nano_ble33_sense -> nano_ble33_sense_microphone_continuous
18.	Alternativ: File -> Examples -> <name>_inferencing -> nano_ble33_sense -> nano_ble33_sense_microphone (nimmt nicht durchgehend auf, sondern nur wenn “Recording…” ausgegeben wird)

**Weiterführende Links**

- Weiterführende Informationen zur Anwendung von Edge Impulse auf dem Arduino: [Arduino](https://docs.arduino.cc/tutorials/nano-33-ble-sense/edge-impulse/)
- Weiterführende Informationen zu Edge Impulse: [Edge Impulse](https://docs.edgeimpulse.com/tutorials/end-to-end/keyword-spotting)


Quelle der Audio-Daten:
Edge Impulse. (2024). Audio Classification – Keyword Spotting. Edge Impulse Studio. Verfügbar unter: https://studio.edgeimpulse.com/public/499022/latest
(Lizenz: Apache 2.0)
