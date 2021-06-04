# Secret aus Datei anlegen und mit kubeseal verschlüsseln

```bash
echo xxx > secret.txt
kubectl -n <target-namespace> create secret   generic  secret-name --from-file=PAT_TOKEN=./secret.txt --dry-run=client -o json 
```
