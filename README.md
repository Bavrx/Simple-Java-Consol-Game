# ⚔️ Java Terminal RPG

[![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white)](https://www.java.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
[![Contributions Welcome](https://img.shields.io/badge/Contributions-Welcome-brightgreen.svg?style=for-the-badge)](#-mitwirken)

Ein rundenbasiertes Text-Adventure (TUI - Terminal User Interface), geschrieben in Java. Spieler können eine von drei Klassen wählen, gegen verschiedene Monster antreten, im Level aufsteigen, Loot sammeln und ihre Ausrüstung in einem Shop verbessern.

## ✨ Features

* **3 Spielbare Klassen:** Wähle zwischen Warrior, Mage und Archer mit individuellen Lebenspunkten (HP) und Angriffsschaden (AD).
* **Rundenbasiertes Kampfsystem:** Kämpfe gegen Feinde wie Zombies, Goblins und Drachen. Wähle taktisch zwischen Angriff, Heilung, Inventarnutzung oder Flucht.
* **Loot- & Inventar-System:** Besiegte Gegner lassen Münzen, Erfahrungspunkte (EP) und gelegentlich Schatztruhen mit Items (z.B. Heiltränke, Schwerter) fallen.
* **Shop-System:** Nach Kämpfen kann zufällig ein Shop erscheinen. Kaufe Items mit gesammelten Münzen.
* **Leveling-System:** Sammle Erfahrungspunkte, steige im Level auf und erhalte verbesserte Statuswerte sowie Münz-Boni.
* **DevTools (Cheats):** Integrierte Methoden für Gottmodus, One-Hit-Kills und alle Items (für Testzwecke direkt im Code anpassbar).

## 🚀 Installation & Start

### Voraussetzungen
* [Java Development Kit (JDK)](https://www.oracle.com/java/technologies/downloads/) (Version 8 oder neuer empfohlen)
* Eine Kommandozeile (Terminal, CMD, PowerShell) oder eine Java-IDE (z. B. IntelliJ IDEA, Eclipse).

### Lokales Setup (Terminal)

1. **Repository klonen**
   ```bash
   git clone [https://github.com/DEIN_USERNAME/DEIN_REPOSITORY_NAME.git](https://github.com/DEIN_USERNAME/DEIN_REPOSITORY_NAME.git)
   cd DEIN_REPOSITORY_NAME

2. **Code kompilieren**
Da das Skript das Package org.example verwendet, generiert der Parameter -d . die korrekte Ordnerstruktur für die kompilierten Klassen.

```javac -d . Main.java```

3. **Spiel ausführen**
   
```java org.example.Main```
 
### 🎮 Spielanleitung

1. Klasse wählen: Das Spiel startet im Terminal. Gib 1, 2 oder 3 ein, um deinen Charakter (Warrior, Mage oder Archer) zu wählen.

2. Der Kampf: Sobald ein Gegner auftaucht, tippst du eine Zahl (1-4), um deine Aktion auszuführen:

- 1.ANGREIFEN - Fügt dem Gegner sofortigen Schaden zu.

- 2.HEILEN - Heilt den eigenen Charakter um festgelegte Lebenspunkte.

- 3.INVENTAR - Öffnet das Inventar, um gesammelte Waffen oder Tränke auszuwählen.

- 4.FLIEHEN - Bricht den Kampf ab und beendet den Durchlauf.

3. Nach dem Kampf: Wenn du gewinnst, erhältst du EP und Münzen. Achte auf auftauchende Truhen oder den Händler, um dich für immer stärkere Gegner auszurüsten!


### 📂 Projektstruktur

Die Kernlogik befindet sich in der Datei Main.java im Package org.example. Das Projekt ist in folgende Hauptkomponenten unterteilt:

- ``Game`` & ``Main``: Steuern die Hauptschleife und den allgemeinen Spielablauf.

- ``TUI`` (Terminal User Interface): Behandelt Konsolenausgaben und Menüs.

- ``Player``, ``Enemy``, ``Boss``: Lebewesen-Klassen, die von der Superklasse ``Entety`` erben. Verwalten Lebenspunkte, Schaden und Level.

- ``Inventory`` & ``Item``: Speichern Gegenstände, wickeln den Gebrauch (Heilung/Schaden) sowie den Kauf/Verkauf ab.

- ``ShopCreater`` & ``Loot``: Generieren zufällige Belohnungen und Händler-Angebote.

### 🤝 Mitwirken

Contributions sind jederzeit willkommen! Wenn du das Spiel erweitern möchtest (z. B. neue Gegner, ein Speichersystem oder neue Items):

1. Forke das Repository.

2. Erstelle einen neuen Branch (git checkout -b feature/NeueIdee).

3. Committe deine Änderungen (git commit -m 'Füge neuen Boss hinzu').

4. Pushe in deinen Branch (git push origin feature/NeueIdee).

5. Öffne einen Pull Request.

📝 Lizenz

Dieses Projekt ist unter der MIT-Lizenz lizenziert. Du kannst es frei verwenden, modifizieren und verbreiten.


### Projekt- und Code-Prüfung 

Die obige README erfüllt alle Best Practices, die auf GitHub für professionelle Open-Source-Kommandozeilentools und -spiele gelten: Sie bietet klare Badges, erklärt den Mehrwert (Features), liefert genaue Kompilierungsbefehle und definiert Richtlinien für Open-Source-Beiträge.

Vor dem Hochladen des Codes auf GitHub solltest du noch folgende Optimierungen am Java-Quellcode in Betracht ziehen, um einen professionelleren Eindruck bei anderen Entwicklern zu hinterlassen:

* **Tippfehler bei Klassennamen korrigieren:** Deine Basisklasse heißt aktuell `Entety` (korrekt wäre `Entity`). Auch `ShopCreater` sollte zu `ShopCreator` umbenannt werden.
* **Variablennamen optimieren:** Die Variable `plchoise` ist ein Tippfehler und sollte `plChoice` oder `playerChoice` heißen.
* **Klassen auslagern:** Aktuell befinden sich über ein Dutzend Klassen in einer einzigen `Main.java` Datei. Für eine saubere Projektstruktur auf GitHub ist es Best Practice, für jede Klasse (wie `Player.java`, `Item.java`, `Inventory.java`) eine separate Datei im Ordner `src/main/java/org/example/` anzulegen.
* **Konsolen-Bereinigung (`Console bereinigen`):** Du verwendest eine Schleife, die 50 leere Zeilen ausgibt. Für plattformübergreifende Java-CLI-Anwendungen nutzen erfahrene GitHub-Projekte stattdessen oft echte Clear-Commands wie `System.out.print("\033[H\033[2J"); System.out.flush();` (funktioniert auf fast allen modernen Terminals) anstelle von Zeilenumbrüchen.
