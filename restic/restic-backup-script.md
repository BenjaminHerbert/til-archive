# Restic - Backup Script

```bash
#!/bin/bash
export RESTIC_PASSWORD_FILE=./restic-password
export RESTIC_REPOSITORY_FILE=./restic-repository
restic --exclude-file=restic-excludes.txt backup ~
restic check
restic prune
```

Dabei liegt sowohl Passwort als auch Repository-Location in einer Datei vor, damit diese automatisiert im Skript verwendet werden können.

Auch werden Excludes in der Datei restic-excludes.txt definert und nicht gesichert.

Im Anschluss folgt eine Überprüfung des Repositories durch `restic prune`.