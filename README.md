# Spracherkennung

**Keyword Spotting** 

1.	Öffne [Edge Impulse](https://studio.edgeimpulse.com/) understelle ein neues Projekt.
2.	Verbinde ein device (bspw. Handy) um Audio Daten zu sammeln. Klicke auf „connect a device” und scanne den QR-Code.
3.	Lege das Label des Wortes fest auf das du das Modell trainieren willst und spreche das Wort mehrfach ein. Wähle microphone, 16000Hz und die Länge der Aufnahme fest (bspw. 60000ms).
4.	Splitte das Sample in kleinere Abschnitte indem du auf die drei Punkte und „Split sample“ drückst. Wähle eine passende Länge (empfohlen 1000ms) und aktiviere shift samples für eine bessere Generalisierung.
5.	Optional kann der Datensatz mit noise-, sowie unknown-daten aus dem Ordner [MP3-Data](https://github.com/Tarn017/Spracherkennung/tree/main/MP3_Data) erweitert werden.
6.	Links unter "Dashboard" kann ganz unten optional "Perform Train / Test Split" durchgeführt werden um die gesammelte Daten 80/20 in Train- und Testdaten aufzuteilen.
7.	Wähle in „Create impulse“ die Blöcke “Audio MFCC” sowie “Clasification” und speichere den Impuls.
8.	MFCC: Autotune Parameters -> Save Parameters -> Generate Features
9.	Classifier: Activate Augmentation -> Save & Train
10.	Live Classification/Model Testing: Teste dein erzeugtes Modell
11.	Deployment: Arduino Library auswählen und builden
12.	Die geladene Datei als Zip-Bibliothek in Arduino einbinden
13.	Installiere im Board-Manager: “Arduino Mbed OS Nano Boards” und wähle als Board den “Arduino Nano 33 Ble“.
14.	In Arduino: File -> Examples -> <name>_inferencing -> nano_ble33_sense -> nano_ble33_sense_microphone_continuous
15.	Alternativ: File -> Examples -> <name>_inferencing -> nano_ble33_sense -> nano_ble33_sense_microphone (nimmt nicht durchgehend auf, sondern nur wenn “Recording…” ausgegeben wird)
16.	Weiterführende Informationen zur Anwendung von Edge Impulse auf dem Arduino: [Arduino](https://docs.arduino.cc/tutorials/nano-33-ble-sense/edge-impulse/)
17.	Weiterführende Informationen zu Edge Impulse: [Edge Impulse](https://docs.edgeimpulse.com/tutorials/end-to-end/keyword-spotting)

Quelle der Audio-Daten:
Edge Impulse. (2024). Audio Classification – Keyword Spotting. Edge Impulse Studio. Verfügbar unter: https://studio.edgeimpulse.com/public/499022/latest
(Lizenz: Apache 2.0)
