# velero server

### Minio Setup

Add Bitnami Repo:
```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
```

Install Minio:
```bash
helm upgrade -i minio bitnami/minio  \
  --namespace minio \
  --create-namespace \
  --version 14.1.7 \
  --set auth.rootPassword=rootpass123
```

User `admin` Pass `rootpass123`

### Velero Setup

Create credentials file:
```bash
cat << EOF >> credentials-velero
[default]
aws_access_key_id = admin
aws_secret_access_key = rootpass123
EOF
```

Install Velero:
```bash
velero install \
    --provider aws \
    --plugins velero/velero-plugin-for-aws:v1.9.1 \
    --bucket velero \
    --secret-file ./credentials-velero \
    --use-volume-snapshots=false \
    --backup-location-config region=minio,s3ForcePathStyle="true",s3Url=http://minio.minio.svc:9000
```



