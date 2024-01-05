# velero

Install Velero:
```bash
brew install velero
```

Create backup:
```bash
velero create backup new-backup
```

List all the backups:
```bash
velero get backups
```

Describe the backup:
```bash
velero describe backups daily-backup-20231207000045
```

Get the backup location:
```bash
velero get backup-location
```
