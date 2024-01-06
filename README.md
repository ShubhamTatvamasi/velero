# velero

Install Velero:
```bash
brew install velero
```

Create backup:
```bash
velero create backup backup-1
```

List all the backups:
```bash
velero get backups
```

Describe the backup:
```bash
velero describe backups backup-1
```

Check the logs of a backup:
```bash
velero backup logs backup-1
```

Delete backup:
```bash
velero backup delete backup-1
```

Get the schedule backup list:
```bash
velero get schedules
```

Schedule a backup:
```bash
velero create backup --from-schedule daily-backup
```


Get the backup location:
```bash
velero get backup-location
```

Restore backup:
```bash
velero restore create restore-1 --from-backup backup-1
```
