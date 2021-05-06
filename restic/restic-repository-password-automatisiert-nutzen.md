# Restic - Repository-Passwort automatisiert nutzen

Um das Passwort in Skripten automatisch zu verwenden, kann man es in eine Datei schreiben und dann diese Datei als Umgebungsvariable angeben.

```bash
export RESTIC_PASSWORD_FILE=./restic-password
```
Das ist für ein Backupskript hilfreich..
