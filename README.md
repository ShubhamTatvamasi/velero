# velero

Install Velero:
```bash
brew install velero
```

Create backup:
```bash
velero create backup backup-1
```

Take backup for only `monitoring` namespace and delete after 10 minutes.
```bash
velero backup create test-backup-1 --ttl 10m --include-namespaces monitoring
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

Filter errors:
```bash
velero backup logs backup-1 | grep level=error
```

Get list of all items inside backup:
```bash
velero backup describe backup-1 --details
```

Delete backup:
```bash
velero backup delete backup-1
```

Create a schedule:
```bash
velero create schedule daily-backup --schedule="0 8 * * 1-6"
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
