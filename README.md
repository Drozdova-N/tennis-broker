## Install postgres-operator zalando
```bash
helm install postgres-operator ./postgres-operator
```

## Install postgresql db 
```bash
helm install postgres-db ./postgres-db
```
### Test connect 
```bash
helm test postgres-db
```

### get host-port db (TODO: add ingress)
```bash
minikube service postgres-db  --url | sed 's,.*/,,'
```
### get password for user `postgres` (TODO add custom user/password)
```bash
kubectl get secret postgres.postgres-db.credentials.postgresql.acid.zalan.do  -o 'jsonpath={.data.password}' | base64 -d
```