# Cronjob Charts

Helm chart for creating your cronjobs in ```kubernetes``` cluster. By using this
chart you can manage your cronjobs by editing only one file. This chart will reduce
your time to set or edit your cronjobs. It also gives you a versioning ability on your
cronjobs.

## values

In ```values.yml``` file you can set your cronjobs based on the following structure:

```yaml
jobs:
  - name: pull-codes
    cron: "* 1 * * * *"
    image: amirhossein21/gitPuller:v0.1.0
    env:
    - name: REPO
      valueFrom:
        configMapKeyRef:
          name: pull-codes-configmap
          key: repository.path
```
