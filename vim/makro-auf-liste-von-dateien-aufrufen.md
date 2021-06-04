# Makro auf Liste von Dateien aufrufen

## Macro definieren

Macros mit Vim kann man mit Hilfe von `@<char>`aufruft und dann die Befehlsfolge eingibt. Beenden und speichert man ebenfalls mit `q`.

## Betreffende Dateien öffnen

Beispielsweise alle Dateien, die mit fuubar beginnen öffnen.
`vim fuubar*`

Oder, wenn vim schon geöffnet ist, mit `:args fuubar*` alle Dateien öffnen.

## Liste der Dateien ansehen
`:ls` zeigt eine Liste der Dateien an.

## Hidden Modus aktivieren
Um mehrere Dateien in einem Rutsch zu bearbeiten, muss man erlauben, dass Dateien _abandon_ed werden können.

> Vim remembers whether you have changed the buffer.  You are protected from       
> losing the changes you made.  If you try to quit without writing, or want to     
> start editing another file, Vim will refuse this.  In order to overrule this     
> protection, add a '!' to the command.  The changes will then be lost.  For       
> example: ":q" will not work if the buffer was changed, but ":q!" will.  To see   
> whether the buffer was changed use the "CTRL-G" command.  The message includes   
> the string "[Modified]" if the buffer has been changed, or "+" if the 'm' flag   
> is in 'shortmess'.                                                               
>                                                                                  
> If you want to automatically save the changes without asking, switch on the       
> 'autowriteall' option.  'autowrite' is the associated Vi-compatible option       
> that does not work for all commands.                                             
>                                                                                  
> If you want to keep the changed buffer without saving it, switch on the          
> 'hidden' option.  See hidden-buffer.  Some commands work like this even when     
> 'hidden' is not set, check the help for the command.

Dazu kann man `:set hidden` setzen.

## Einen Befehl auf alle Dateien in der arglist anwenden

Man kann auch ein Makro auf allen Dateien in der Arglist aufrufen:
```bash
:argdo normal @q
```