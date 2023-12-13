# Methoden einer Klasse testen

Nötige Schritte:
1. Testobjekt erzeugen
2. die zu testende Methode aus diesem aufrufen
3. Rückgabewert bzw. neuen Zustand überprüfen 

Wichtig: es sollten mindestens Getter-Methoden vorhanden sein, vielleicht auch Setter

Bsp. Testen von Folgender Klasse:

```java
class Bruch{
	Bruch(int z, int n){…}
	void kuerzen(){…}
	String toString(){…}
	boolean equals(Object o){...}
}
```

```java 
Static void testToString(){
	Bruch b1 = new Bruch(1, 2);                  // Vorbereitung
	String erg = b.toString();                   // Aufrufen
	annahmeGleich("1/2", erg, "toString 1/2");   // Vergleichen
}
Static void testEquals(){
	Bruch b1 = new Bruch(1, 2);                  // Vorbereitung
	Bruch b2 = new Bruch(1, 2);
	boolean erg = b1.equals(b2);                 // Aufrufen
	annahmeGleich(True, erg, ...);               // Vergleichen
}
Static void testKuerzen(){
	Bruch b1 = new Bruch(2, 4);                  // Vorbereitung
	Bruch b2 = new Bruch(1, 2);
	b1.kuerzen();                                // Aufrufen
	annahmeGleich(b2, b1, ...);                  // Vergleichen
}
// usw ...

// annahme Gleich für String, int, boolean und Object
Static void annahmeGleich(String soll, String ist, String info){
	System.out.println("Test: " + info);
	if(ist.equals(soll)) System.out.println("erfolgreich");
	else System.out.println("nicht erfolgreich");
}
Static void annahmeGleich(int soll, int ist, String info){
	System.out.println("Test: " + info);
	if(ist == soll) System.out.println("erfolgreich");
	else System.out.println("nicht erfolgreich");
}
Static void annahmeGleich(boolean soll, boolean ist, String info){
	System.out.println("Test: " + info);
	if(ist == soll) System.out.println("erfolgreich");
	else System.out.println("nicht erfolgreich");
}
Static void annahmeGleich(Object soll, Object ist, String info){
	System.out.println("Test: " + info);
	if(soll.equals(ist)) System.out.println("erfolgreich");
	else System.out.println("nicht erfolgreich");
}
```
