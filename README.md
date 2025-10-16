# Spracherkennung

**Keyword Spotting – [Edge impulse](https://studio.edgeimpulse.com/)** 

1.	Verbinde ein device (bspw. Handy) um Audio Daten zu sammeln. Klicke auf „connect a device” und scanne den QR-Code.
2.	Lege das Label des Wortes fest auf das du das Modell trainieren willst und spreche das Wort mehrfach ein. Wähle microphone, 16000Hz und die Länge der Aufnahme fest (bspw. 60000ms).
3.	Splitte das Sample in kleinere Abschnitte indem du auf die drei Punkte und „Split sample“ drückst. Wähle eine passende Länge (empfohlen 1000ms) und aktiviere shift samples für eine bessere Generalisierung.
4.	Optional kann der Datensatz mit noise-, sowie unknown-daten aus dem Ordner MP3-Data erweitert werden.
5.	Wähle in „Create impulse“ die Blöcke “Audio MFCC” sowie “Clasification” und speichere den Impuls.
6.	MFCC: Autotune Parameters -> Save Parameters -> Generate Features
7.	Classifier: Activate Augmentation -> Save & Train
8.	Live Classification/Model Testing: Teste dein erzeugtes Modell
9.	Deployment: Arduino Library auswählen und builden
10.	Die geladene Datei als Zip-Bibliothek in Arduino einbinden
11.	Installiere im Board-Manager: “Arduino Mbed OS Nano Boards” und wähle als Board den “Arduino Nano 33 Ble“.
12.	In Arduino: File -> Examples -> <name>_inferencing -> nano_ble33_sense -> nano_ble33_sense_microphone_continuous
13.	Alternativ: File -> Examples -> <name>_inferencing -> nano_ble33_sense -> nano_ble33_sense_microphone (nimmt nicht durchgehend auf, sondern nur wenn “Recording…” ausgegeben wird)
14.	Weiterführende Informationen zur Anwendung von Edge Impulse auf dem Arduino: https://docs.arduino.cc/tutorials/nano-33-ble-sense/edge-impulse/
15.	Weiterführende Informationen zu Edge Impulse: https://docs.edgeimpulse.com/tutorials/end-to-end/keyword-spotting

Quelle der Audio-Daten:
Edge Impulse. (2024). Audio Classification – Keyword Spotting. Edge Impulse Studio. Verfügbar unter: https://studio.edgeimpulse.com/public/499022/latest
(Lizenz: Apache 2.0)
