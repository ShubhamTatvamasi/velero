# velero server

### Minio Setup

Add Bitnami Repo:
```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
```

Install Minio:
```bash
helm upgrade -i minio bitnami/minio  \
  --namespace velero \
  --create-namespace \
  --version 14.1.7 \
  --set auth.rootPassword=rootpass123
```

User `admin` Pass `rootpass123`
