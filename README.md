# hvoigt NeoVim Start

This is my NeoVim configuration. It is currently cobbled together from
[kickstart.vim](https://github.com/nvim-lua/kickstart.nvim), and my good old
personal [.vimrc](https://www.hvoigt.net/.vimrc) preferences.

Use `:Mason` to install all language server support needed.

## Usage

This is a highly opinionated list of the additional features:

- `gr` - Show references of symbol in Telescope
- `,sf` - Fuzzy open filename in Telescope
- `,ws` - Fuzzy search all workspace symbols
- `,o` - Open location on GitHub
- `zg` - Add word to spellchecker
- `<ctrl>-i` / `m-backspace` - Incremental / Decremental Scoped selection
- `<ctrl>-k` - signature help
- `]m` / `[m` - Next/Previous function
- `<ctrl>-q` - Send Telescope result to quick-fix list
- `:Telescope keymaps` - Show/Search keybindings
- `:Telescope builtin` - Search through built-in functions
- `:Mason` - add language servers
- `:Lazy` - Install/Update

## Navigation Customizations

Additional to default Vim navigation these are some customizations

- `<tab>` - Next open buffer
- `<shift>-<tab>` - Previous open buffer
- `<space>` - Page down
- `b` - Page up

## My personal list of the most important Vim commands

### 10 most important Commands:
- `i` - Insertmodus (Editiermodus) starten (jetzt kannst du Text eingeben)
- `ESC` - Insertmodus beenden und zurück zum Kommandomodus
- `:q!` - Beenden ohne zu speichern
- `:wq` - Speichern und beenden
- `u` - Undo
- `C-r` - Redo
- `v` - Selektiert Zeichenweise
- `y` - Den selektierten Text kopieren (yank)
- `d` - Den selektierten Text ausschneiden (wird ins Copy Register gespeichert)
- `P` - Den kopierten Text im aktuellen Copy Register vor der aktuellen Position einfügen

Das ganze nochmal in ausführlich, sind wie gesagt nur die *wichtigsten* Kommandos die mir aus dem Kopf gerade einfallen :-)

### Laden, Speichern, Beenden
- `:w` - Speichert die Datei
- `:wq` - Speichert die Datei und beendet Vim
- `:q` - Beendet
- `:q!` - Beendet auch wenn noch nicht alles gespeichert ist
- `:w!` - versucht zu speichern auch wenn schreibgeschützt
- `:e <Datei>` - Öffnet `<Datei>` zum Editieren

### Editiermodus
- `o` - Springt unter die aktuelle Zeile zum editieren
- `O` - Springt über die aktuelle Zeile zum editieren
- `i` - Editiermodus an der aktuellen Position
- `a` - Editiermodus hinter dem aktuellen Zeichen
- `A` - Editiermodus am Ende der Zeile
- `cw` - Löscht von Cursorposition zum Ende des Wortes und wechselt in den Editiermodus

### Im Insertmodus (Editiermodus)
- `C-n` - Autovervollständigung vorwärts (öfters drücken um zum nächsten Begriff zu springen)
- `C-p` - Autovervollständigung rückwärts (öfters drücken um zum nächsten Begriff zu springen)
- `ESC` - Insertmodus beenden und zurück zum Kommandomodus

### Selektieren
- `v` - Selektiert Zeichenweise
- `V` - Selektiert Zeilenweise
- `C-v` - Selektiert Blockweise

Auf Selektionen kann man viele Kommandos anwenden
Mit Selektion folgende Kommandos ausgeführt kannst du:

- `d` - Den selektierten Text ausschneiden (wird ins Copy Register gespeichert)
- `y` - Den selektierten Text kopieren (yank)
- `:` - Ein Kommando auf die Selektion anwenden (z.b. :s/bla/blub/ um alle Vorkommen von bla durch blub zu ersetzen)
- `:w` - Die Selektion in einer Datei speichern
- `:sort` - Die Zeilen in der Selektion alphabetisch sortieren
- `=` - Selektion automatisch Formatieren (Einrückungen)
- `gq` - Selektion neu umbrechen (Textenbeschreibungen ganz nützlich wenn du zwischendrin was eingefügt hast)

### Editieren (Kommandomodus)
_Achtung: wenn Zeilenweise kopiert/gelöscht dann wird auch zeilenweise eingefügt)_
- `dd` - Eine Zeile löschen
- `.` - Letzte Aktion wiederholen
- `u` - Undo
- `C-r` - Redo
- `D` - Zeichen von aktueller Position bis Ende der Zeile löschen
- `p` - Den Text im aktuellen Copy Register nach der aktuellen Position einfügen
- `P` - Den Text im aktuellen Copy Register vor der aktuellen Position einfügen
- `==` - Zeile automatisch formatieren

### Bewegen
- `0,$` - Springe zum Anfang, Ende der Zeile
- `:0,:$` - Springe zum Anfang, Ende der Datei
- `:<Nummer>` - Springt zur Zeile <Nummer>
- `h,j,k,l` - Cursor nach links, runter, hoch, rechts bewegen
- `C-u` - Seite nach oben
- `C-d` - Seite nach unten
- Suchen: _Suchbegriffe können mit den Cursortasten aus der History geholt werden_
  - `/<Begriff>` - Nach unten nach Begriff suchen
  - `?<Begriff>` - Nach oben nach Begriff suchen
- `n` - Mit der letzten Suche weiter springen
- `N` - Mit der letzten Suche zurück springen
- `*` - Wort unter dem Cursor vorwärts suchen und hinspringen
- `#` - Wort unter dem Cursor rückwärts suchen und hinspringen
- `E` - Bis zum nächsten Space weiterspringen
- `B` - Bis zum nächsten Space zurückspringen
- `%` - Bracketmatching: Spring von öffnender Klammer zur schließenden bzw. zurück.

### Compilieren
- `:make` - make im aktuellen Verzeichnis ausführen
- `:copen` - öffnet ein neues Window mit der Compilerausgabe. Bei Enter auf einer Warnung/Error springst du automatisch zur Stelle

### Windows
- `C-w <left>,<up>,<down>,<right>` - Ein Window nach links,unten,oben,rechts vom aktuellen springen
- `C-w` - Ein Window nach oben springen
- `C-w n` - Ein neues Window oben anlegen
- `C-w v` - Ein neues Window daneben anlegen
- `C-w c` - Aktuelles Window schliessen

### Buffer
- `:bnext` - Nächsten Buffer (mit meiner .vimrc auf <Tab> gemappt)
- `:bprevious` - Vorherigen Buffer (mit meiner .vimrc auf <Shift>-<Tab> gemappt)
- `:bdelete` - Buffer schliessen

## Tips

### Debugging Language Server Configuration

- `:lua vim.cmd('e'..vim.lsp.get_log_path())` - LSP logs

### C/C++ Code

- `bear -- make` - generates a `compile-commands.json`  for `clangd` so `gI` (go to Implementation works)
