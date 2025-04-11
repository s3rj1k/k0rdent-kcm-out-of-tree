# k0rdent/kcm (out-of-tree)

## Debug charts

### Pull

```bash
helm pull oci://ghcr.io/k0rdent/kcm/charts/kcm --version 0.2.0 --untar --untardir ./TEMP/.
helm pull oci://ghcr.io/k0rdent/kcm/charts/kcm-templates --version 0.2.0 --untar --untardir ./TEMP/.
helm pull oci://ghcr.io/k0rdent/kcm/charts/cluster-api-provider-openstack --version 0.2.0 --untar --untardir ./TEMP/.
helm pull oci://ghcr.io/k0rdent/kcm/charts/openstack-standalone-cp --version 0.2.0 --untar --untardir ./TEMP/.

helm pull oci://ghcr.io/k0rdent-oot/oot/charts/cluster-api-provider-kubevirt --version 0.2.1 --untar --untardir ./TEMP/.
helm pull oci://ghcr.io/k0rdent-oot/oot/charts/kubevirt-standalone-cp --version 0.2.0 --untar --untardir ./TEMP/.

helm pull oci://ghcr.io/k0rdent-oot/oot/charts/kubevirt --version 0.1.0 --untar --untardir ./TEMP/.
```

### Render

```bash
helm template test oci://ghcr.io/k0rdent/kcm/charts/kcm --version 0.2.0 -n kcm-system --output-dir ./TEMP/.
helm template test oci://ghcr.io/k0rdent/kcm/charts/kcm-templates --version 0.2.0 -n kcm-system --output-dir ./TEMP/.
helm template test oci://ghcr.io/k0rdent/kcm/charts/cluster-api-provider-openstack --version 0.2.0 -n kcm-system --output-dir ./TEMP/.
helm template test oci://ghcr.io/k0rdent/kcm/charts/openstack-standalone-cp --version 0.2.0 -n kcm-system --output-dir ./TEMP/.

helm template test oci://ghcr.io/k0rdent-oot/oot/charts/cluster-api-provider-kubevirt --version 0.2.1 -n kcm-system --output-dir ./TEMP/.
helm template test oci://ghcr.io/k0rdent-oot/oot/charts/kubevirt-standalone-cp --version 0.2.0 -n kcm-system --output-dir ./TEMP/.

helm template test oci://ghcr.io/k0rdent-oot/oot/charts/kubevirt --version 0.1.0 -n kcm-system --output-dir ./TEMP/.
helm template test oci://ghcr.io/k0rdent-oot/oot/charts/kubevirt --version 0.1.0 \
  -n kcm-system \
  --set kubevirt.configuration.developerConfiguration.featureGates="{useEmulation=true}" \
  --output-dir ./TEMP/.
```

### Generate `values.schema.json`:

Use `https://github.com/losisin/helm-values-schema-json` to (re)generate schemas manually.

Inside chart folder run `helm schema -input values.yaml`, see example [valules.yaml](https://github.com/k0rdent/kcm/blob/main/templates/cluster/gcp-standalone-cp/values.yaml)
