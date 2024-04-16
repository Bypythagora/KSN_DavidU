# KSN_DavidU
KSN_Projekt_David_Uzelac

## AM Modulation
![alt text](https://github.com/Bypythagora/KSN_DavidU/blob/main/AM%20Modulation%20img.png)
Das Bild oben präsentiert eine repräsentative AM-Modulation im Kontext von GNU Radio. Im Folgenden wird eine ausführliche Erläuterung der verschiedenen Komponenten zur Konstruktion der AM-Modulation präsentiert.

+ Die Variable (samp_rate) definiert die Abtastfrequenz, die in diesem Fall 48 kHz beträgt.

+ Die QT GUI Range-Blöcke stellen grafische Benutzeroberflächen (GUI) dar, die es dem Benutzer ermöglichen, Parameter wie Frequenzen, Volumen und Modulationstiefe in Echtzeit zu steuern.

+ Der Signal Source-Block erzeugt die Trägerwelle, die typischerweise als Kosinuswelle dargestellt wird. Sowohl die Frequenz als auch die Amplitude dieser Trägerwelle können über die GUI eingestellt werden. 

+ Der Add Const-Block fügt dem Signal eine Konstante hinzu. Dieser Schritt wird oft durchgeführt, um sicherzustellen, dass das modulierte Signal immer positive Amplituden aufweist, insbesondere wenn die Modulationstiefe sehr hoch ist. 

+ Der Multiply-Block ist der Kern der AM-Modulation, da er das Trägersignal mit dem Audiosignal multipliziert. Durch diese Multiplikation werden die Amplitudenänderungen des Audiosignals auf die Trägerwelle übertragen, wodurch das modulierte Signal entsteht.
  
+ Der Audio Sink-Block gibt das modulierte Signal an die Soundkarte des Computers aus, so dass es hörbar ist. Dies ermöglicht es dem Benutzer, das modulierte Signal zu überprüfen und zu bewerten, indem er es direkt hört.
  
+ Der QT GUI Sink-Block zeigt das Spektrum des Signals in einem Frequenzspektrum-Display an. Durch dieses visuelle Feedback kann der Benutzer die modulierten Signale überprüfen und bestätigen, dass die Amplitudenmodulation wie erwartet funktioniert.


## FM Radio
![alt text](https://github.com/Bypythagora/KSN_DavidU/blob/main/FM%20Radio%20img.png)

+ Der PlutoSDR Source-Block fungiert als Quelle für das FM-Signal, das von einem Software Defined Radio (SDR) empfangen wird. Dieser Block spielt eine entscheidende Rolle bei der Definition verschiedener Parameter des empfangenen Signals, darunter die Abtastrate (beispielsweise 2 Millionen Samples pro Sekunde) und die Zentralfrequenz (zum Beispiel 107,5 MHz für einen typischen FM-Radiosender). Zusätzlich zu diesen grundlegenden Eigenschaften ermöglicht der PlutoSDR Source-Block auch die Anpassung anderer wichtiger Parameter, die die Qualität und Genauigkeit der Signalverarbeitung beeinflussen können.

+ Das QT GUI Range-Element stellt eine grafische Benutzeroberfläche dar, die es dem Benutzer ermöglicht, die Zentralfrequenz des Empfängers in Echtzeit einzustellen. Diese Funktion ist äußerst nützlich, da sie es dem Benutzer ermöglicht, nahtlos durch den FM-Bandbereich zu scrollen, um verschiedene Radiosender zu finden und auszuwählen.

+ Der Rational Resampler-Block ist für die Anpassung der Abtastrate des empfangenen Signals verantwortlich. Dieser Schritt ist erforderlich, um sicherzustellen, dass das Signal mit einer für die weitere Verarbeitung geeigneten Abtastrate vorliegt.

+ Der Low Pass Filter-Block spielt eine kritische Rolle bei der Signalverarbeitung, indem er unerwünschte Frequenzen aus dem Signal entfernt und nur das gewünschte Signal passieren lässt. Dies trägt dazu bei, die Bandbreite zu reduzieren und unerwünschtes Rauschen zu minimieren, was zu einer verbesserten Signalqualität führt.

+ Die QT GUI Frequency Sink und QT GUI Waterfall Sink sind GUI-Elemente, die eine visuelle Darstellung des empfangenen Signals sowohl im Frequenzbereich als auch als "Waterfall" Display bieten. Das Frequency Sink zeigt eine Momentaufnahme des Signals im Frequenzbereich an, während das Waterfall Display eine zeitliche Darstellung des Spektrums bietet, wodurch Veränderungen im Signal im Laufe der Zeit sichtbar werden.

+ Der WBFM Receive-Block ist speziell für den Empfang von Wideband FM-Signalen konzipiert. Dieser Block dekodiert das FM-Signal in ein Basisband-Audiosignal, das dann über den Audio Sink-Block ausgegeben wird. Auf diese Weise können Benutzer das empfangene Audiosignal über Lautsprecher oder Kopfhörer hören.
