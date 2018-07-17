# Content/Inhalt

* [Content/Inhalt](#contentinhalt)
   * [English README: Custom css file for the Seafile server](#english-readme-custom-css-file-for-the-seafile-server)
      * [Intro](#intro)
      * [Installation](#installation)
      * [Notes](#notes)
      * [Dark theme](#dark-theme)
   * [Deutsche README: Eigene css-Datei für den Seafile-Server](#deutsche-readme-eigene-css-datei-für-den-seafile-server)
      * [Intro](#intro-1)
      * [Installation](#installation-1)
      * [Sonstiges](#sonstiges)
      * [Dunkles Thema](#dunkles-thema)
   * [Screenshots](#screenshots)

# English README: Custom css file for the Seafile server

## Intro

The Seafile server comes with a standard template that does not look bad, but does not like everyone. This can be changed by overwriting desired parts of the template with own values.

With the ***custom.css*** from this repository, the default color **orange** of the elements is changed to **green**.

## Installation

Copy the file ***custom.css*** to ***seahub-data/custom*** and add the following line to ***conf/seahub-settings.py***:

    BRANDING_CSS = 'custom/custom.css'

To change the icon color for folder icons you have to copy the file folder-192.png from the img folder of this repo into the seahub folder (***seafile-server-latest/seahub/media/img***) on your server and rename it to folder-24.png. But before please create a backup of your original file. After an update of the Seafile server this change will be reverted and you have to copy it again.

If you want to use the green Favicon copy the ***favicon.png*** to ***seahub-data/custom*** and add the following line to your ***conf/seahub-settings.py***:
    
    FAVICON_PATH = 'custom/favicon.png'

Finally, the Seafile server (and Seahub) must be restarted. For example in Debian Jessie this can be done with:

```bash
sudo systemctl stop seahub.service
sudo systemctl stop seafile.service
sudo systemctl start seafile.service
sudo systemctl start seahub.service
```

## Notes

- the icons for folders are not changed and still have the color orange. I'm currently looking for a way to change the folder icon color so that the changes will be kept within a server update.
- ***custom.css*** tested with Seafile Server 6.3.2
- for Seafile Server 6.2.5 use the ***custom.css*** from the branch v6_2_5
- At the top of the custom.css you will find two variables which define the main colors (dark and light). Here you can change the color to the color you want to use:

```css
:root {
    --darkMain: #008a3b; /* dark green - Main color for elements */
    --lightMain: #e2f1e7;/* light green - Second color, e. g. for some selected items */
    --textLM: #000000;   /* black - Text color for elements with lightMain */
}
```

## Dark theme

There are two different versions of a dark theme (beta):

1. semi-dark, where only the left panel is dark (***custom.css_semidark***)
2. completely dark (***custom.css_fulldark***)

To try it out/apply, simply rename the corresponding css file to ***custom.css*** and copy it to the ***seahub-data/custom/*** directory. 

# Deutsche README: Eigene css-Datei für den Seafile-Server

## Intro

Der Seafile-Server mit mit einem Standard-Template ausgeliefert, das grundsätzlich nicht schlecht aussieht, aber doch nicht jedem gefällt. Das kann man ändern, in dem man gewünschte Teile des Templates mit eigenen Werten überschreibt.

Mit Hilfe der ***custom.css*** aus diesem Repository wird die Standardfarbe **orange** der Elemente in **grün** geändert.

## Installation

Dazu muss man die Datei namens ***custom.css*** in den Ordner ***seahub-data/custom*** kopieren und im conf-Ordner des Seafile-Servers die Datei seahub_settings.py angepassen, in dem folgender Eintrag hinzugefügt wird:

    BRANDING_CSS = 'custom/custom.css'

Zum Ändern der Farbe des Icons für Ordner (original orange) muss die Datei folder-192.png aus dem img-Ordner des Repos in den Seahub-Ordner ((***seafile-server-latest/seahub/media/img***)) auf dem Server kopiert und in folder-24.png umbenannt werden. Aber bitte vorher ein Backup der Originaldatei anlegen. Diese Änderung ist nicht persistent und ist nach einem Seafile Server Update verscheunden und muss dann neu durchgeführt werden.

Wenn man das Favicon auch im passenden grün haben möchte, dann muss die Datei  ***favicon.png*** nach ***seahub-data/custom*** kopiert und die folgende Zeile zur ***conf/seahub-settings.py*** hinzugefügt werden:
    
    FAVICON_PATH = 'custom/favicon.png'

Zuletzt muss noch der Seafile-Server (und Seahub) neugestartet werden. Das erfolgt zum Beispiel bei Debian Jessie mit:

```bash
sudo systemctl stop seahub.service
sudo systemctl stop seafile.service
sudo systemctl start seafile.service
sudo systemctl start seahub.service
```
## Sonstiges

- die Icons'für Ordner und ähnliches sind nich nicht geändert und haben noch die Farbe orange. Ich suche zur Zeit noch eine Möglichkeit, dass so zu ändern, dass die Änderung bei einem Server-Update erhalten bleibt.
- ***custom.css*** getestet mit Seafile Server 6.3.2
- Für Seafile Server 6.2.5 bitte die ***custom.css*** aus dem Branch v6_2_5 benutzen
- Am Anfang der custom.css sind die zwei Hauptfarben als Variable deklariert. Hier können die beiden Farben geändert werden, ohne sie im gesamten Dokument suchen zu müssen:

```css
:root {
    --darkMain: #008a3b; /*dark green*/
    --lightMain: #e2f1e7; /*light green*/
}
```

## Dunkles Thema

Es gibt zwei verschiedene Versionen eines dunklen Themas (beta):

1. halbdunkel, wobei nur das linke Panel dunkel ist (***custom.css_semidark***)
2. komplett dunkel (***custom.css_fulldark***)

Zum Ausprobieren/Anwenden muss lediglich die entsprechende css-Datei in ***custom.css*** umbenannt und in das Verzeichnis ***seahub-data/custom/*** kopiert werden. 

# Screenshots

## Normal

<img src="https://raw.githubusercontent.com/focmb/seafile_custom_css_green/master/screenshots/screenshot1.png" alt="Login" width="300"> <img src="https://raw.githubusercontent.com/focmb/seafile_custom_css_green/master/screenshots/screenshot2.png" alt="Navbar" width="300">
<img src="https://raw.githubusercontent.com/focmb/seafile_custom_css_green/master/screenshots/screenshot3.png" alt="Main" width="600">
<img src="https://raw.githubusercontent.com/focmb/seafile_custom_css_green/master/screenshots/screenshot4.png" alt="Folder" width="600">

---

## Semi dark

src="https://raw.githubusercontent.com/focmb/seafile_custom_css_green/master/screenshots/screenshot5.png" alt="Main dark" width="600">