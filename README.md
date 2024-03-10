# Lokaler multimodaler KI-Chat
## Übersicht

Local Multimodal AI Chat ist ein praktisches Projekt, das darauf abzielt, zu lernen, wie man eine multimodale Chat-Anwendung erstellt. Bei diesem Projekt geht es darum, verschiedene KI-Modelle zu integrieren, um Audio, Bilder und PDFs in einer einzigen Chat-Oberfläche zu verarbeiten. Es ist eine großartige Möglichkeit für alle, die sich für KI und Softwareentwicklung interessieren, praktische Erfahrungen mit diesen Technologien zu sammeln.

Der Hauptzweck hier ist das Lernen durch Handeln. Sie werden sehen, wie verschiedene Teile wie Whisper AI für Audio, LLaVA für die Bildverarbeitung und Chroma DB für PDFs in einer Chat-Anwendung zusammenkommen. Eine vollständige Anleitung, wie ich dieses Repository erstellt habe, finden Sie auf meinem [Youtube-Kanal](https://youtu.be/CUjO8b6_ZuM).
Aber das ist noch in Arbeit. Es gibt viel Raum für Verbesserungen, und hier kommen Sie ins Spiel.

Ich bin sehr offen für Pull Requests. Egal, ob Sie Ideen für neue Funktionen haben, Möglichkeiten zur Verbesserung des Codes oder einfach nur einen Fehler beheben möchten, Ihre Beiträge sind willkommen. Bei diesem Projekt geht es nicht nur darum, voneinander zu lernen, sondern auch darum, etwas Cooles zu bauen.

Wenn Sie sich also für KI-Chat-Anwendungen interessieren und in deren Aufbau eintauchen möchten, machen Sie mit. Ihr Code und Ihre Ideen können dazu beitragen, dieses Projekt für alle zu verbessern, die mehr über das Bauen mit KI erfahren möchten.

## Eigenschaften

- **Quantisierte Modellintegration**: Diese App verwendet sogenannte "quantisierte Modelle". Diese sind etwas Besonderes, weil sie so konzipiert sind, dass sie gut auf normaler Consumer-Hardware funktionieren, wie sie die meisten von uns zu Hause oder in unseren Büros haben. Normalerweise sind die Originalversionen dieser Modelle sehr groß und benötigen leistungsfähigere Computer, um sie auszuführen. Quantisierte Modelle sind jedoch so optimiert, dass sie kleiner und effizienter sind, ohne viel Leistung zu verlieren. Das bedeutet, dass Sie diese App und ihre Funktionen nutzen können, ohne einen superleistungsstarken Computer zu benötigen. [Quantisierte Modelle von TheBloke] (https://huggingface.co/TheBloke)

- **Audio-Chat mit Whisper AI**: Diese App nutzt die robusten Transkriptionsfunktionen von Whisper AI und bietet ein ausgeklügeltes Audio-Messaging-Erlebnis. Die Integration von Whisper AI ermöglicht eine genaue Interpretation und Reaktion auf Spracheingaben, wodurch der natürliche Gesprächsfluss verbessert wird.
[Flüstermodelle] (https://huggingface.co/collections/openai/whisper-release-6501bba2cf999715fd953013)

- **Bild-Chat mit LLaVA**: Die App integriert LLaVA für die Bildverarbeitung, bei dem es sich im Wesentlichen um ein fein abgestimmtes LLaMA-Modell handelt, das für das Verständnis von Bildeinbettungen geeignet ist. Diese Einbettungen werden mithilfe eines CLIP-Modells generiert, wodurch LLaVA wie eine Pipeline funktioniert, die erweitertes Text- und Bildverständnis zusammenführt. Mit LLaVA wird das Chat-Erlebnis interaktiver und ansprechender, insbesondere wenn es um den Umgang mit und die Konversation über visuelle Inhalte geht. [llama-cpp-python repo zum Laden von Llava] (https://github.com/abetlen/llama-cpp-python)

- **PDF-Chat mit Chroma DB**: Die App ist sowohl für den professionellen als auch für den akademischen Einsatz zugeschnitten und integriert Chroma DB als Vektordatenbank für effiziente PDF-Interaktionen. Diese Funktion ermöglicht es Benutzern, mit ihren eigenen PDF-Dateien lokal auf ihrem Gerät zu interagieren. Egal, ob es sich um die Überprüfung von Geschäftsberichten, wissenschaftlichen Arbeiten oder anderen PDF-Dokumenten handelt, die App bietet ein nahtloses Erlebnis. Es bietet Benutzern eine effektive Möglichkeit, mit ihren PDFs zu interagieren und die Leistungsfähigkeit der KI zu nutzen, um Inhalte in diesen Dokumenten zu verstehen und darauf zu reagieren. Dies macht es zu einem wertvollen Werkzeug für den persönlichen Gebrauch, bei dem man Erkenntnisse und Zusammenfassungen extrahieren und eine einzigartige Form des Dialogs mit dem Text in seinen PDF-Dateien führen kann. [Chroma-Webseite] (https://docs.trychroma.com/)


## Erste Schritte

Um mit dem lokalen multimodalen KI-Chat zu beginnen, klonen Sie das Repository und führen Sie die folgenden einfachen Schritte aus:

1. **Erstellen Sie eine virtuelle Umgebung**: Ich verwende derzeit Python 3.10.12

2. **Upgrade-Pip**: '''pip install --upgrade pip'''

3. **Installationsanforderungen**: '''pip install -r requirements.txt'''
   
   **Windows-Benutzer:** Die Installation kann für Sie etwas anders sein, wenn Sie auf Fehler stoßen, die Sie nicht beheben können, öffnen Sie bitte ein Problem hier auf Github.

4. **Einrichten lokaler Modelle**: Laden Sie die Modelle herunter, die Sie implementieren möchten. [Hier] (https://huggingface.co/mys/ggml_llava-v1.5-7b/tree/main) ist das Llava-Modell, das ich für den Bild-Chat verwendet habe (ggml-model-q5_k.gguf und mmproj-model-f16.gguf). 
Und das [quantisierte Mistral Modell](https://huggingface.co/TheBloke/Mistral-7B-Instruct-v0.1-GGUF) von TheBloke (mistral-7b-instruct-v0.1.Q5_K_M.gguf).

5. **Konfigurationsdatei anpassen**: Überprüfen Sie die Konfigurationsdatei und ändern Sie sie entsprechend zu den heruntergeladenen Modellen.

6. **Optional - Profilbilder ändern**: Legen Sie Ihre user_image.pnd und/oder bot_image.png im chat_icons Ordner ab. 

7. **Geben Sie Befehle in das Terminal ein**: 
   1. '''python3 database_operations.py''' Dadurch wird die SQLite-Datenbank für die Chat-Sitzungen initialisiert.
   2. '''Stromlinienförmiger Lauf app.py'''


## Changelog
### 17.02.2024:
- **Eingabe-Widget-Update**: st.text_input wurde durch st.chat_input ersetzt, um die Interaktion zu verbessern, indem eine Chat-orientierte Benutzeroberfläche genutzt wird, die die Benutzerinteraktion erleichtert.
- **Sidebar-Anpassung**: Die Audioaufnahme-Taste wurde in die Seitenleiste verlegt, um eine übersichtlichere und übersichtlichere Benutzeroberfläche zu schaffen und die Zugänglichkeit und Benutzerfreundlichkeit zu verbessern.

### 10.02.2024:
- **Lizenz hinzugefügt**: Die GNU General Public License v3.0 wurde implementiert, um sicherzustellen, dass das Projekt unter den Bedingungen dieser Lizenz frei zur Nutzung, Änderung und Verbreitung verfügbar ist. Ein umfassender Urheberrechts- und Lizenzhinweis wurde in die Hauptdatei (app.py) aufgenommen, um die Bedingungen, unter denen das Projekt angeboten wird, klar zu kommunizieren. Diese Ergänzung zielt darauf ab, sowohl die Rechte der Mitwirkenden als auch die der Benutzer zu schützen und eine offene und kollaborative Entwicklungsumgebung zu fördern. Vollständige Lizenzdetails finden Sie in der LICENSE-Datei im Projekt-Repository.
- **Caching für Chat-Modell**: Caching für das Chat-Modell eingeführt, um zu verhindern, dass es bei jeder Skriptausführung neu geladen wird. Diese Optimierung verbessert die Leistung erheblich, indem die Ladezeiten verkürzt werden 
- **Erweiterung der Konfigurationsdatei**: Die Konfigurationsdatei wurde erweitert, um neue Einstellungen und Funktionen aufzunehmen und so mehr Flexibilität und Anpassungsoptionen für die Chat-Anwendung zu bieten.


### 09.02.2024:

- SQLite-Datenbank für den Chatverlauf**: Es wurde eine SQLite-Datenbank zum Speichern des Chatverlaufs implementiert.
- **Anzeigen von Bildern und Audiodateien im Chat**: Der Chatverlauf unterstützt jetzt die Anzeige von Bildern und Audiodateien.
- **Schaltfläche zum Löschen des Chatverlaufs hinzugefügt**
- **Aktualisierte Langchain**: Läuft jetzt mit der aktuellen Langchain-Version 0.1.6

### 16.01.2024:
- **Problem mit dem DateTime-Format des Windows-Benutzers:** Windows-Benutzer schienen Probleme mit dem datetime-Format der gespeicherten JSON-Chatverläufe zu haben. Ich habe das Format in der 'ultis.py'-Datei in '"%Y_%m_%d_%H_%M_%S" geändert, was das Problem lösen sollte. Fühlen Sie sich frei, es nach Ihren Wünschen zu ändern.
- **UI-Anpassung für Chat-Scrolling:** Das Herunterscrollen im Chat hat mich genervt, daher sind das Texteingabefeld und die letzte Nachricht jetzt ganz oben.

### 12.01.2024:
- **Problem mit dem Senden von Nachrichten:** Nach dem Schreiben in das Textfeld und dem Drücken der Schaltfläche "Senden" generierte der LLM keine Antwort. 
- **Ursache des Problems:** Dies ist passiert, weil der Rückruf "clear_input_field" von der Schaltfläche den Wert des Textfelds nach dem Speichern der Benutzerfrage in eine leere Zeichenfolge ändert. Wenn Sie jedoch den Wert des Textfelds ändern, wird der Rückruf vom Textfeld-Widget ausgelöst, wobei der user_question erneut auf eine leere Zeichenfolge gesetzt wird. Infolgedessen wird der LLM nicht aufgerufen.
- **Implementierte Problemumgehung:** Um dieses Problem zu umgehen, habe ich eine Prüfung hinzugefügt, bevor ich den Wert "user_question" geändert habe.

## Mögliche Verbesserungen
- ~~Modell-Caching hinzugefügt.~~
- ~~Füge Bilder und Audio zum Speichern und Laden des Chatverlaufs hinzu.~~
- ~~Verwende eine Datenbank, um den Chatverlauf zu speichern.~~
- Integrieren Sie Ollama, OpenAI, Gemini oder andere Modellanbieter.
- Bildgenerator-Modell hinzugefügt.
- Authentifizierungsmechanismus.
- Ändern Sie das Thema.
- Trennen Sie Frontend- und Backend-Code für eine bessere Bereitstellung.

## Kontaktinformationen
