# Kubernetes Update

#kubernetes #aks

Kommt es zum Fehler bei einem Upgrade der AKS-Cluster, muss man den Prozess wieder starten, nachdem man die Fehler behoben hat.
```bash
az resource update --name <name> --namespace Microsoft.ContainerService --resource-group <resource group> --resource-type ManagedClusters
```

