# Passphrase zu bestehendem Key hinzufügen

Mit dem Befehl `ssh-keygen -p -f <keyfile>`kann man bestehende Keys mit neuen Passphrase versehen.

Details:
`ssh-keygen -p [-a rounds] [-f keyfile] [-m format] [-N new_passphrase] [-P old_passphrase]`

manpage-Auszug:
```
     -p      Requests changing the passphrase of a private key file instead of creating a new private key.  The program will prompt for the file containing the private key, for the old passphrase, and twice for the new passphrase.

```