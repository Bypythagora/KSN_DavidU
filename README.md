# KSN_DavidU
KSN_Projekt_David_Uzelac

## AM Modulation
(https://github.com/Bypythagora/KSN_DavidU/edit/main/AM Modulation img.png)
Das Bild oben präsentiert eine repräsentative AM-Modulation im Kontext von GNU Radio. Im Folgenden wird eine ausführliche Erläuterung der verschiedenen Komponenten zur Konstruktion der AM-Modulation präsentiert.

+ Die Variable (samp_rate) definiert die Abtastfrequenz, die in diesem Fall 48 kHz beträgt.

+ Die QT GUI Range-Blöcke stellen grafische Benutzeroberflächen (GUI) dar, die es dem Benutzer ermöglichen, Parameter wie Frequenzen, Volumen und Modulationstiefe in Echtzeit zu steuern.

+ Der Signal Source-Block erzeugt die Trägerwelle, die typischerweise als Kosinuswelle dargestellt wird. Sowohl die Frequenz als auch die Amplitude dieser Trägerwelle können über die GUI eingestellt werden. 

+ Der Add Const-Block fügt dem Signal eine Konstante hinzu. Dieser Schritt wird oft durchgeführt, um sicherzustellen, dass das modulierte Signal immer positive Amplituden aufweist, insbesondere wenn die Modulationstiefe sehr hoch ist. 

+ Der Multiply-Block ist der Kern der AM-Modulation, da er das Trägersignal mit dem Audiosignal multipliziert. Durch diese Multiplikation werden die Amplitudenänderungen des Audiosignals auf die Trägerwelle übertragen, wodurch das modulierte Signal entsteht.
  
+ Der Audio Sink-Block gibt das modulierte Signal an die Soundkarte des Computers aus, so dass es hörbar ist. Dies ermöglicht es dem Benutzer, das modulierte Signal zu überprüfen und zu bewerten, indem er es direkt hört.
  
+ Der QT GUI Sink-Block zeigt das Spektrum des Signals in einem Frequenzspektrum-Display an. Durch dieses visuelle Feedback kann der Benutzer die modulierten Signale überprüfen und bestätigen, dass die Amplitudenmodulation wie erwartet funktioniert.
