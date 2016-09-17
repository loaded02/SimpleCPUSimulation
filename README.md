# SimpleCPUSimulation
Java Application created during studies at h_da. The Application simulates multiple CPUs with a fictive commandset.

1) HAL OS ermoeglicht es verschiedene HAL Prozessoren (eigene Threads) ueber EA Bausteine miteinander zu verbinden. Die Verbindungsstruktur wird ueber das configFile eingelesen.
2) Das von einem HAL Prozessor auszufuehrende Programm wird im configFile festgelegt. Es muss sich im working directory befinden.
3) Verbindung zwischen den Prozessoren ist die Klasse Buffer.
4) Ein HAL Prozessor verfuegt ueber zwei MMUs mit jeweiliger Seitengroesse 1k fuer Datenspeicher (Register) und Programmspeicher. Die Wortbreite von HAL ist 16 Bit. Programmspeichergroesse 2k Zellen, Anzahl der Register 4k.
5) Das HAL Programm schreibt in alle Register i=0 bis 2¹⁶-1 die Werte i/2. Danach gibt es den gesamten Speicher wieder aus und macht 2 Additionen und gibt Ergebnis aus.


## configFile Beispiel
HAL - Prozessoren :
1 Pfad zum Hal - Programm fuer HAL - Prozessor 1
2 Pfad zum Hal - Programm fuer HAL - Prozessor 2
...
n Pfad zum Hal - Programm fuer HAL - Prozessor n
HAL - Verbindungen :
1:3 > 2:2
E/A-3 von HAL-Prozessor 1 sendet an E/A-2 von HAL-Prozessor 2 (x:x -> stdin/stdout)
2:4 > 3:5
E/A-4 von HAL-Prozessor 2 sendet an E/A-5 von HAL-Prozessor 3
